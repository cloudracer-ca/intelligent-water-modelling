# Choosing tools without losing the model

*Optional. About 7 minutes.*

Sooner or later someone will propose a product. This page helps you judge one against the approach in this
repository. It names no products. The same questions apply to all of them.

## The jobs to be done

Every architecture of this kind has the same few jobs. A product may do one of them or several.

| Job | What it does |
|---|---|
| **Collect at the edge** | Reads equipment and older systems, and shapes the data before it travels |
| **Broker** | Receives published data, enforces the rules, and passes it to whoever subscribes |
| **Historian** | Stores values over time and answers questions about the past |
| **Graph or modelling tool** | Holds the types and relationships so software can follow them |
| **Open API** | Lets any application ask what exists, how it connects, and what the values are |
| **Analysis and screens** | Turns data into answers, and shows them to people |

Three more things sit above these and are yours, not a product's: the model, the checks on it, and the small
program that turns it into settings for each tool. [Build or buy?](build-or-buy.md) covers all nine.

Write down which job you are buying for before you look at a product. Most disappointments start with a tool
bought for one job that quietly took over two more.

## The one rule

**The model lives in your files. Each tool is configured from it. No tool is the master.**

A tool that is set up from your model strengthens the design: there is still one place to change and one
review. A tool where people start modelling inside it weakens the design, however good it is, because you
now have two sources, and they will drift apart.

## Four kinds of product you will meet

Products in this space tend to fall into four shapes. None is wrong. Each changes your architecture in a
different way.

| Shape | What it brings | What to watch |
|---|---|---|
| **A platform you already own, with add-on modules** | Your SCADA or historian supplier offers a broker, a store or a modelling module. It is already bought and already supported | It is convenient, and it ties more jobs to one supplier. Ask the same questions of it as of anything new |
| **A narrow integration hub** | Collects, shapes and publishes to *your* broker. Leaves everything else alone | It has its own models of what a message looks like. Those can become a second place where modelling happens |
| **An edge platform with its own broker** | Strong at reading many kinds of equipment, and brings a broker and namespace of its own | It overlaps with a broker you already have. Your rules must be produced in its format, or enforced twice |
| **A context platform** | One runtime for the namespace, schemas, units and quality, and often a graph as well | It overlaps with the most. The more it does, the more there is to replace if you change your mind |

The trade is always the same: the more a product does, the less you assemble, and the more of your design
it decides for you. For a small team, less to assemble can be exactly the right choice.

## What a tool can add, and what it can cost

| It can add | It can cost |
|---|---|
| Connections to equipment you could not otherwise reach | A second place where models are defined |
| Cleaning and shaping data close to the source | Rules held only in its memory, lost on a restart |
| Configuration kept in version control | Configuration that can also be changed on screen, with no record |
| An assistant that drafts types and mappings | Content the assistant invented, accepted without review |
| One supplier for several jobs | One supplier to depend on for several jobs |

## Fifteen questions to ask

Ask these of any product. Not every question applies to every job: a historian does not collect at the edge.
A [one-page sheet](../../examples/workshop-kit/tool-evaluation-sheet.md) with the same questions is in the
workshop kit.

| # | Question | A good answer |
|---|---|---|
| 1 | Which of the six jobs does it do, and which do we already have covered? | It is clear, and the overlap is small or deliberate |
| 2 | Can it be configured entirely from files we generate? | Yes, and we were shown it with our own model |
| 3 | If someone changes it on screen, can we tell? | Changes are logged, or on-screen editing can be switched off |
| 4 | Does it publish to our broker, or must it be the broker? | It works with ours |
| 5 | What happens to relationships? | It carries them, or leaves them alone. It does not need to own them |
| 6 | Does it accept types from a published standard? | Yes, and we imported one |
| 7 | When a type changes, do existing assets follow? | Automatically, or with one reviewed step |
| 8 | What does it keep when the link drops, and whose timestamp does it use? | It stores and forwards, with the time the value was measured |
| 9 | Does it send a value when it changes, or only on a timer? | When it changes by more than a set amount (a deadband), plus a periodic refresh so that silence is never mistaken for a steady value |
| 10 | How do people and systems sign in, how is it patched, and how are its flaws made known? | Our own sign-in system, a stated patch schedule, and a public record of fixed flaws |
| 11 | If it has an assistant, what leaves our network when it is used? | Stated exactly, and the assistant can be switched off |
| 12 | Can everything we put in come back out in an open format? | Yes, complete, and we tested rebuilding from it |
| 13 | Who owns the model and data we put in, and may the supplier use them? | We do. The supplier may not use them, including to train its own systems, without our written consent |
| 14 | What does it cost at our size, and at renewal? | Stated in writing |
| 15 | Who supports it, for how long, and what happens to us if the product ends? | Named, with a term, and our export still works |

**Ask to be shown, not told.** Anything claimed in a meeting should be demonstrated before you rely on it.
Questions 2, 6 and 12 you should test yourself, with your own model.

## Test with your own model

Do not judge a tool on its demonstration data. Take a small model of your own, about ten assets, and try
three things:

1. **Load it.** Did the tool accept your types, your assets and your relationships, or only some of them?
2. **Change it.** Rename one asset in your files and load again. Did everything that depends on it follow?
3. **Take it out.** Export what the tool holds and compare it with what you put in.

Half a day of this tells you more than a month of meetings. Keep a note of what failed. A tool that fails a
test is not necessarily the wrong tool, but you should know before you depend on it.

A small model proves the fit. It does not prove the size. Before you commit, ask to see the tool running at
your real number of values, or test it at that rate yourself.

## Four cautions

- **The tool you already own has a head start.** The cost of changing usually outweighs differences in
  features. Test what you have against these questions before looking elsewhere.
- **An assistant inside a tool is still an assistant.** It will sometimes invent things. Review what it
  proposes exactly as you would review a person's change.
- **Ask someone who already runs it.** Another utility that has used the product for a year will tell you
  things no demonstration will.
- **Follow your organisation's purchasing rules.** This page is about fit with an approach. It is not
  purchasing advice.

The [four tests for any tool](../4-how-to-get-started.md#four-tests-for-any-tool) on the getting-started page
are the short version of this page.

Next: [Build or buy?](build-or-buy.md)
