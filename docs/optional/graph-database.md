# Do you need a graph database?

*Optional. About 2 minutes.*

When people hear "knowledge graph" they often assume they must buy and run a graph database. That is one
option, and not the only one.

A knowledge graph is the **information**: the types, the equipment and the relationships between them. It can
be held in several ways.

| Held in | What that means | Good when |
|---|---|---|
| **A graph library** | The graph is built in memory by a program, from your model, each time it starts | The model is small, and a few programs use it |
| **A graph database** | A separate server stores the graph and answers queries | Many people or tools need to explore a large graph with their own questions |
| **A product with a graph built in** | A historian or data platform holds the graph alongside the data | You already use, or plan to use, that product |

The first is the simplest: a graph library, with the graph rebuilt from the model at every start. Two things
follow from that choice.

- **There is no extra server to run.**
- **The graph always matches the model**, because it is rebuilt from it. Nobody can edit one without the other.

For a first model of a few hundred pieces of equipment, the graph is small, and any of the three will work.
What matters most at the start is that the graph is **correct and can be rebuilt**.

A graph database earns its place as the graph grows and more people need to query it. For most teams that is a
later decision. It does not have to be the first one.

See also: [Root cause and anomaly detection, without guessing](root-cause-and-anomaly-detection.md), which sets out three ways to build that use.

Next: [References](references.md).
