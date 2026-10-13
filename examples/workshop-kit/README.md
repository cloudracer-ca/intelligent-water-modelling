# Workshop kit

Five things to help a team build its first model and judge the tools around it. Nothing here needs installing.

| File | What it is |
|---|---|
| [model-template.xlsx](model-template.xlsx) | A spreadsheet with the same three parts as the example models: types, plant and bindings, filled in with the invented wastewater example. It checks itself as you type |
| [model-template-blank.xlsx](model-template-blank.xlsx) | The same spreadsheet with the plant and bindings sheets empty, ready for your own model. The type sheets are kept as a start |
| [first-session-agenda.md](first-session-agenda.md) | A 90-minute agenda for a first modelling session |
| [ownership-worksheet.md](ownership-worksheet.md) | A one-page worksheet for deciding who owns each part |
| [tool-evaluation-sheet.md](tool-evaluation-sheet.md) | Fifteen questions to score any product against, build-or-buy questions, and tests to run with your own model |

## About the template

- The example copy opens filled in with the invented [wastewater example](../example-wastewater/). Read it,
  then start your own in the blank copy.
- Yellow cells are yours. The grey "Check" column on each sheet says "ok" or says what is wrong with that row.
- The first sheet counts the problems across all sheets, and the measurements that have no address yet.
- Topics are built for you from a prefix, the asset's place in the tree and a short name. Nothing is typed
  twice. For the example, they match the topics in the example's bindings file exactly.
- The checks catch: names that do not match (capitals count), duplicates, a type or measurement type that is
  not defined, a unit that does not match its measurement type, a missing parent, a parent loop or a tree
  more than five levels deep, and a measurement with no topic. They do not check everything a compiler would
  (for example, which types a relationship may connect), and they cannot tell you whether a relationship is
  true. Only people who know the plant can.
- It leaves out records, quality limits and derived values to stay small. The example files show how those
  are added once the basics are agreed.

**The spreadsheet is a starting point, not the model's permanent home.** Once the model is kept as files or
in a tool, name that copy as the source and stop editing this one. Two copies that are both edited will
drift apart.

**If you fill it in with real data, keep it inside your organisation.** See
[what not to put in a model you share](../../docs/4-how-to-get-started.md#what-not-to-put-in-a-model-you-share).

The template was checked three ways: every row of the example shows "ok"; the topics it builds match the
example's bindings file; and copies with deliberate mistakes (a missing parent, a misspelt measurement type
or kind, "feeds" in lower case, a parent loop, a wrong unit, a duplicate relationship, an unknown asset)
reported each of them.
