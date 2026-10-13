# 4. How to get started

*About 6 minutes. Unfamiliar terms are explained in the [glossary](optional/references.md#glossary).*

"How do I start?" is the most common question on this subject. The honest answer is: small, and with your own
words for your own equipment.

## Seven first steps

1. **Check that your data is stored and trusted.** A model on top of data nobody believes helps no one.
2. **Pick one question worth answering.** For example: "When a transmission main loses pressure, what is the
   likely cause?" One question keeps the first model small.
3. **Name your types.** What is a pump? What is a reservoir? What is a main? Use the standards and documents you
   already have. Five to ten types is enough. The [starter model](../examples/starter-model.yaml) is a template.
4. **List about ten assets** that matter to your question, and give each one a type and a parent.
5. **Add three kinds of relationship.** *Feeds*, *protects* and *monitors* go a long way.
6. **Review it with the people who run the plant,** then put the file in version control. An operator will spot a
   wrong connection in seconds.
7. **Generate one thing from it.** A topic list for the broker is a good first output: the workshop template's
   Topic column builds one for you. Then grow the model one question at a time.

The [workshop kit](../examples/workshop-kit/) has a spreadsheet template for steps 3 to 5 and an agenda for
doing them in one 90-minute session.

An AI assistant is a good partner for steps 3 to 5. Work *with* it, and check what it proposes. It does not know
your plant.

Some modelling products now include an assistant for this
([two examples](optional/one-value-followed-through.md#products-as-examples-only)).

## What the first three months can look like

This is an illustration, not a case study.

A small team picks one question: "when a transmission main loses pressure, what should we look at first?"
In the first month they agree on six types and list the dozen pieces of equipment involved. In the second,
an operator and an engineer review the relationships and correct two of them. In the third, the model is
used to produce one thing: a list, for each main, of what protects it and what that protection depends on.

Nothing has been bought and nothing has been connected. The team now has a model people trust, an owner for
it, and one answer that used to live in someone's head.

You do not need a complete model of everything. Start small and extend it as each new question needs. The
common trap is trying to model the whole plant before answering one question; that work rarely finishes.

## Which data first

This is about all your operations data, not only SCADA. Most teams start with what they already trust: SCADA
values and the historian. The lab system, maintenance and GIS join later, one at a time. Each connects once to
the same namespace and reuses the same types, so adding one does not mean redoing the others.

## People and ownership

The technology is the smaller part.

- **Name an owner.** One role or small group is responsible for the model and approves changes to it.
- **Involve operations early.** The people who run the plant know how it really connects.
- **Bring IT, OT and security together** before anything is connected, not after.
- **Show people how to use it.** Teach users to find a value and read what it means. A model nobody can use
  changes nothing.
- **Treat every connection as a security decision.** A water system is critical infrastructure. This repository
  is not security guidance; involve your security team before plant data is connected to anything else.
- **Expect it to take time.** This is a change measured in years. Aim for one useful answer in the first few
  months, and build from there.

## What not to put in a model you share

- Real addresses or locations of critical equipment.
- Network details: host names, IP addresses, ports, user names.
- Passwords, keys or tokens of any kind.
- Links and file paths to documents and drawings.
- Setpoints, capacities and control logic, if the file will leave your organisation.

The example in this repository is wholly invented for that reason. There is a short
[note on security](optional/an-incident-followed-through.md#a-note-on-security) in the optional reading.

## The challenges you will meet, and what helps

| Challenge | What helps |
|---|---|
| **The plant changes and the model does not** (schema drift) | Compare what the plant publishes with what the model declares, and have a person approve every change. See [Schema drift](optional/schema-drift.md). |
| **The model ends up inside one product** | Keep the model in your own file, and prefer tools that can import it and that offer an open API. |
| **A tool does not accept your model as expected** | Test each tool with your own model early, before you depend on it. |
| **Calculations are hidden inside reports** | Give each calculated value a name, a unit, an owner and its inputs, in one place. Every report then uses the same one. |
| **Nobody trusts the answer** | Show the working. Every number should trace back to a stored value and a relationship in the model. See [Trusting the data](optional/trusting-the-data.md). |

## Four tests for any tool

These four are often given as the minimum technical requirements for a UNS
([one summary](https://www.sirris.be/en/inspiration/unified-namespace-next-step-industry-40-standardisation)), and
they make a good minimum to ask of anything you add.

| Test | In plain words |
|---|---|
| **Edge driven** | Data is pushed from where it originates. Nothing reaches in to fetch it. |
| **Report by exception** | A value is sent when it changes, not on a timer. |
| **Lightweight** | Small messages that cope with slow or unreliable links. |
| **Open architecture** | Published interfaces, so one part can be replaced without rebuilding the rest. |

Open architecture is about avoiding lock-in and keeping parts interchangeable. It does not mean the software
must be open source: a commercial product with published interfaces passes, and an open-source one that only
talks to itself does not.

When someone proposes a product, [Choosing tools without losing the model](optional/choosing-tools.md) has
fifteen questions to ask and a sheet to fill in, and [Build or buy?](optional/build-or-buy.md) covers which
parts are worth writing yourselves.

## The first sign it is working

Someone asks, "what protects this main?", and the answer comes from the model instead of from the one person
who remembers.

---

That is the short read. If you want more, continue with [Choosing tools without losing the model](optional/choosing-tools.md),
or go back to the [start page](../README.md).
