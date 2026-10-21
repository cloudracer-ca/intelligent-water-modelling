# Moving the data: the edge, and five terms to know

*Optional. About 6 minutes.*

Most Unified Namespaces use MQTT to carry data from the plant to the tools that use it. When you talk to a
vendor or an integrator, a handful of terms will come up. This page explains them so you can ask good questions. It
does not tell you which options to choose: that depends on your systems, and on advice from the people who
build them.

**Scope:** sharing data with historians, dashboards, analytics and AI. Not SCADA control.

**MQTT is one common choice, not the only one.** Data also moves by DNP3 and Modbus, OPC UA, streaming
platforms such as Kafka, and ordinary web APIs. A Unified Namespace is not tied to one protocol.

## Before the data moves: the edge

The **edge** is the place nearest the equipment where data is first collected. The model is written once,
centrally, but it is best applied there: a value is given its name, unit and context before it travels, so
every system downstream receives the same thing.

Older equipment often cannot do this itself. A gateway placed in front of it reads the equipment's own
protocol and publishes the data in the modelled form.

## 1. Quality of Service

Each message can say how carefully it should be delivered.

| Level | The promise |
|---|---|
| **QoS 0** | Sent once. It may be lost |
| **QoS 1** | Delivered at least once. It may arrive twice |
| **QoS 2** | Delivered exactly once, at a higher cost |

Each promise holds for one hop only: from the publisher to the broker, or from the broker to one subscriber.
A message is only as safe as the weakest hop on its way.

There is a trade-off between speed and certainty, and different data can use different levels.

**A question to ask:** which of our data must never be missed, and how will we know if some of it was?

## 2. Retained messages

Normally a broker passes a message on and forgets it. A **retained** message is kept, one per topic, and given
to each client when it subscribes to that topic (subject to the subscription's options).

This is how a UNS can show the current state of the plant to a tool that has only just connected.

Two things worth knowing:

- **A retained value can be old.** It is the last *retained* value, not necessarily the last one published: a
  message sent without the retain flag does not replace it.
- **It is one value, not a history.** Storing the past is a separate job
  ([Where the history goes](where-the-history-goes.md)).

**A question to ask:** how will a user know that a value on the screen is stale?

## 3. Store and forward

Links fail. **Store and forward** means that when the connection to the broker is lost, the edge keeps the
data and sends it once the connection returns.

It only works if every value carries the time it was **measured**, not the time it arrived. Otherwise an hour
of forwarded data lands in the wrong place in the history.

**Questions to ask:**

- How much can the edge hold, and for how long?
- Does the historian accept late data and fill the gap?
- Could a screen show a forwarded, hour-old value as if it were current?

**Plan for the data system itself being down.** List what would stop working if the broker, the historian or
the network between them failed, and what people would do instead. Test the recovery on a schedule, once a
year for example.

## 4. Reading from OPC UA: polling or subscription

There are two ways to read a value from an OPC UA server.

| | Polling | Subscription |
|---|---|---|
| **How it works** | Ask for every value on a timer, changed or not | The server watches the value and reports when it changes |
| **Timestamp** | Both can return the source timestamp: request it and keep it, and record the time of the read or receipt separately | The same |
| **Short events** | Can be missed between two reads | Reported, if the sampling interval is short enough and the queue holds every change |
| **Load** | The same whether anything changed or not | Lower when little is changing |

Subscription is usually the better fit for sharing data, and it is what "report by exception" means in
practice. Some tools only poll.

If one message carries several values, say which time it carries, and keep the time measured at the source.

**A question to ask:** does each tool in the path subscribe, or does it poll, and whose timestamp does it keep?

## 5. The message format: Sparkplug B or JSON

MQTT moves messages. It does not say what is inside them or how topics are named. Two approaches are common.

| | Sparkplug B | JSON over MQTT |
|---|---|---|
| **What it is** | An [open specification](https://sparkplug.eclipse.org/) on top of MQTT | Readable text in a structure you define |
| **Topic names** | Set by the specification | Yours to design |
| **Message contents** | A compact format with data types built in | Human-readable; you define the fields |
| **Who can read it** | Software that understands Sparkplug | Almost any tool |
| **Is the device online?** | Built in: birth and death messages, part of Sparkplug B (current version 3.0) | Yours to design, for example with a last-will message and a retained status |

Both are widely used, and many sites use both in different places. Neither is the right answer everywhere.

The examples in this repository use JSON, with the topic names and the shape of every message generated from
the model and enforced by the broker ([how that works](keeping-the-model-honest.md)). That is a choice for an
example, not a
recommendation.

Whichever format you choose, put the asset's identifier inside the message as well as in the topic. A tool
that stores the message without its topic then still knows what the value belongs to.

**A question to ask:** which of our tools need to read this data, and can they all read the format we choose?

Next: [Do you need a graph database?](graph-database.md).
