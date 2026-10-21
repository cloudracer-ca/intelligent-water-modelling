# Intelligent Water modelling

A short learning resource for water and wastewater utilities that want their data to be ready for analytics and AI.

**The idea in one line:** write down what your equipment *is* and how it *connects*, once, in files you own.
Every tool, and every AI assistant, then reads the same meaning.

Everything here is synthetic. The example plant is invented. This is learning material, not a product.

**Start here by role.** Everyone: the short read below. Then:

- If you lead a team: [how to get started](docs/4-how-to-get-started.md), then
  [Build or buy?](docs/optional/build-or-buy.md).
- Operations: [an incident, followed through](docs/optional/an-incident-followed-through.md).
- Engineering and automation: [one value, followed through](docs/optional/one-value-followed-through.md) and the
  [example models](#the-example-models).
- GIS, asset management and hydraulic modelling:
  [Digital Twin 3.0](docs/optional/digital-twin-3-0-gis-and-maintenance.md).
- OT data and SCADA: [moving the data](docs/optional/moving-the-data.md).
- Compliance and water quality: [trusting the data](docs/optional/trusting-the-data.md).
- To run a first session: the [workshop kit](examples/workshop-kit/).

## The short read (about 17 minutes)

Four short pages, in order.

| # | Page | You will be able to | Time |
|---|---|---|---|
| 1 | [The ideas](docs/1-the-ideas.md) | say why a Unified Namespace alone is not enough, and what a knowledge graph adds | 3 min |
| 2 | [What a model looks like](docs/2-what-a-model-looks-like.md) | read a small YAML model, see why it is split into three files, who owns each part, and what is generated from it | 5 min |
| 3 | [An open API](docs/3-an-open-api.md) | explain why an open API matters, with i3X as the example | 3 min |
| 4 | [How to get started](docs/4-how-to-get-started.md) | take seven first steps, test any tool four ways, and avoid the problems most teams meet | 6 min |

## Optional reading

Read these only if you want more.

- [Choosing tools without losing the model](docs/optional/choosing-tools.md): the jobs a tool can do, four kinds of product, and fifteen questions to ask of any of them. No products are named.
- [Build or buy?](docs/optional/build-or-buy.md): a starting position for each part, what to agree when someone builds it for you, and four questions that settle most cases.
- [An incident, followed through the graph](docs/optional/an-incident-followed-through.md): one invented incident, how the relationships lead to its cause, where AI fits, and a note on security.
- [Root cause and anomaly detection, without guessing](docs/optional/root-cause-and-anomaly-detection.md): how to build the deterministic detection and root-cause analysis behind that incident, with an architecture diagram, short code sketches, and open-source and commercial products listed by role as dated examples.
- [One value, followed through](docs/optional/one-value-followed-through.md): one measurement shown as a model entry, a topic, a message, its rules, an OPC UA node and a historian tag, with what was tested and the standards those outputs follow.
- [Keeping the model honest](docs/optional/keeping-the-model-honest.md): how the broker enforces the model, reviewing changes, versions, ownership and the life of a model entry.
- [Schema drift](docs/optional/schema-drift.md): four ways the model and the real system stop matching, and how each is caught.
- [Trusting the data](docs/optional/trusting-the-data.md): data quality checks including units, derived data, data lineage, and what may be given to an AI tool.
- [Where the history goes](docs/optional/where-the-history-goes.md): what a historian must still do, open formats, and time-series databases.
- [Moving the data](docs/optional/moving-the-data.md): applying the model at the edge, store and forward, polling or subscription, and three MQTT terms, with questions to ask.
- [Do you need a graph database?](docs/optional/graph-database.md): what a knowledge graph needs to run on.
- [Digital Twin 3.0: where a data model sits beside a GIS and a maintenance system](docs/optional/digital-twin-3-0-gis-and-maintenance.md): an informal three-stage framework, what Esri means by a digital twin, and how a data model could sit beside ArcGIS, an optional ArcGIS Knowledge graph and a maintenance system such as Maximo. An illustration.
- [References](docs/optional/references.md): a glossary, where to find ready-made types, and links.

## The example models

All are invented. Nothing needs installing to read this resource; the root-cause page includes short, illustrative Python sketches.

- [examples/starter-model.yaml](examples/starter-model.yaml): about 40 lines. Start here: copy it and replace the
  names with your own.
- [examples/example-plant/](examples/example-plant/): a fuller drinking-water model of 18 assets (nine of them
  equipment), split into three commented files: the types, the plant, and where each value lives.
- [examples/example-wastewater/](examples/example-wastewater/): a wastewater model (a pumping station, a
  forcemain and part of a treatment plant). It reuses the types above and adds seven of its own.
- [examples/workshop-kit/](examples/workshop-kit/): a spreadsheet template that checks itself (a filled-in example and a blank copy), a 90-minute
  agenda for a first modelling session, an ownership worksheet and a tool evaluation sheet.

## What this does not cover

- **Control.** Commands to equipment, and anything safety-related, are out of scope.
- **Security design.** There is one short note, and it tells you to involve your security team.
- **Choosing products.** Products are named as examples, not recommendations.
- **Scale.** The examples are small. A system with hundreds of thousands of values raises design questions
  that are not covered here.
- **Cost and business cases.** These depend on your organisation.

## About this repository

- It is written in a **personal capacity**. It does not represent the views or opinions of the author's employer.
- It was **drafted with AI assistance** and reviewed by the author.
- Facts were checked in **October 2026**. There is no guarantee it will be updated to stay current.

## Licence

[CC BY 4.0](LICENSE) for the documentation; [MIT](examples/LICENSE) for the example models and workshop kit in `examples/`, and for the code samples in the documentation.
Read-only learning material: no support, contributions or contact channel.
