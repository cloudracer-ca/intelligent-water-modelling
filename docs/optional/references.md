# References

*Optional. Links were checked in October 2026.*

## Glossary

| Term | Meaning |
|---|---|
| **Asset** | A specific thing you own: this pump, that reservoir. |
| **Type** | A kind of thing: a pump, a reservoir. Defined once. |
| **Inheritance** | A type built on another type. It gets everything the parent has, and can add to it. |
| **Relationship** | A named, one-way connection between two assets: *feeds*, *supplies air to*, *protects*. |
| **Model** | The file that lists your types, assets, measurements and relationships. |
| **Edge** | The place nearest the equipment where data is first collected. |
| **Graph** | Things and the lines between them. |
| **Lineage** | The trail from a number back to the instrument that measured it. |
| **Store and forward** | Keeping data at the edge while a link is down, and sending it afterwards. |
| **Report by exception** | Sending a value when it changes, not on a timer. |
| **Knowledge graph** | A graph where every thing has a type and every line has a meaning. |
| **Knowledge model (ontology)** | The rule book that says what may exist and how it may connect. |
| **UNS** | Unified Namespace: one shared, structured place where current data is published. |
| **ISA-95** | A standard whose levels (site, area, equipment) are commonly used to structure a UNS. |
| **MQTT** | A widely used protocol for publishing and subscribing to messages. |
| **Broker** | The server that receives published messages and passes them to subscribers. |
| **OPC UA** | A standard way for controllers and SCADA systems to expose their data. |
| **Historian** | The system that stores values over time. |
| **i3X** | An open API for asking an industrial system about its types, objects, relationships and values. |
| **MCP** | Model Context Protocol: an open way for an AI assistant to use a tool or read a data source. |
| **Schema drift** | When the plant and the model stop matching. |

## Where the ideas come from

The core pages are the author's own summary of ideas that are widely used in industry. None of them is original here.

- The **Unified Namespace** was popularised by Walker Reynolds.
- **Knowledge graphs** and **ontologies** are long-established ideas in computing
  ([knowledge graph](https://en.wikipedia.org/wiki/Knowledge_graph),
  [ontology](https://en.wikipedia.org/wiki/Ontology_(information_science))).
- Keeping a model as reviewed files, with types, data sources and transport kept apart, is **"model as code"**
  practice. One public example is Tobias Lante's [osf-schemas](https://github.com/TobiasLante/osf-schemas).
  The three-file example in this repository adapts that idea; it is not a copy of it.
- The site, area, equipment structure comes from the
  [ISA-95](https://www.isa.org/standards-and-publications/isa-standards/isa-95-standard) standard.

## Where to find ready-made types

Before you invent a type, look here. Reusing a published definition of a pump is better than writing your own.

| Library or standard | What it gives you | Maintained by |
|---|---|---|
| [UA Cloud Library](https://uacloudlibrary.opcfoundation.org/) | An online store of OPC UA information models | The OPC Foundation |
| [OPC UA companion specifications](https://opcfoundation.org/about/opc-technologies/opc-ua/ua-companion-specifications/) | Types for particular kinds of equipment, such as [pumps](https://reference.opcfoundation.org/Pumps/v100/docs/) | The OPC Foundation, with industry groups such as VDMA |
| [SM Profiles](https://www.cesmii.org/technology-sm-profiles/) | Reusable definitions of equipment types, built on OPC UA | CESMII |
| [ISA-95](https://www.isa.org/standards-and-publications/isa-standards/isa-95-standard) | The site, area, equipment hierarchy and its models | ISA |
| [ISA-88](https://www.isa.org/standards-and-publications/isa-standards/list-of-all-isa-standards) | Models and terms for batch and process control | ISA |
| [ISA-5.1](https://www.isa.org/standards-and-publications/isa-standards/list-of-all-isa-standards) | How instruments are identified and drawn | ISA |
| [ISA-18.2](https://www.isa.org/standards-and-publications/isa-standards/list-of-all-isa-standards) | How alarms are managed, and the terms used | ISA |
| [QUDT](https://qudt.org/) | Standard names and codes for units of measure | QUDT.org |
| [ISO 15926](https://www.iso.org/standard/29556.html) | Life-cycle data for process plants | ISO |
| [Smart Data Models for water](https://github.com/smart-data-models/dataModel.WaterDistributionManagementEPANET) | Shared definitions of pumps, pipes, tanks, valves and reservoirs | The Smart Data Models initiative |
| [Asset Administration Shell](https://github.com/admin-shell-io/aas-specs) | A standard digital description of an asset | The Industrial Digital Twin Association |

Some standards are free to read and some are sold. Some modelling tools let you import them as libraries:
Timebase Atlas, for example, ships with an ISA-95 library (October 2026).

## Links

**Standards and specifications**
- [ISA/IEC 62443, security for industrial systems](https://www.isa.org/standards-and-publications/isa-standards/isa-iec-62443-series-of-standards)
- [MQTT version 5.0](https://docs.oasis-open.org/mqtt/mqtt/v5.0/mqtt-v5.0.html)
- [Sparkplug](https://sparkplug.eclipse.org/)
- [Apache Parquet](https://parquet.apache.org/)
- [OPC UA NodeSets](https://github.com/OPCFoundation/UA-Nodeset)
- [JSON Schema](https://json-schema.org/)
- [Model Context Protocol](https://modelcontextprotocol.io/)

**Concepts**
- [Knowledge graph](https://en.wikipedia.org/wiki/Knowledge_graph)
- [Ontology](https://en.wikipedia.org/wiki/Ontology_(information_science))

**An open API: i3X**
- [i3x.dev](https://www.i3x.dev/)
- [The specification](https://github.com/cesmii/i3X)
- [i3x2ua](https://github.com/AndreasHeine/i3x2ua), one open-source example that serves i3X from an OPC UA
  server (not tested here)
- [Announcement of version 1.0](https://www.automation.com/article/cesmii-i3x-1.0-open-api-specification-manufacturing-interoperability)
- [CESMII](https://www.cesmii.org/)

Back to the [start page](../../README.md).
