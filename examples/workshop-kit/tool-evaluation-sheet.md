# Tool evaluation sheet

One sheet per product. Fill it in during a demonstration, then again after your own test. The reasoning is in
[Choosing tools without losing the model](../../docs/optional/choosing-tools.md) and
[Build or buy?](../../docs/optional/build-or-buy.md)

**Product:** ______________________  **Date:** ____________  **Filled in by (role):** ______________________

## Which job is it for?

Tick the jobs you are buying it for. Circle the jobs it would also take over.

- [ ] Collect at the edge
- [ ] Broker
- [ ] Historian
- [ ] Graph or modelling tool
- [ ] Open API
- [ ] Analysis and screens

## The fifteen questions

Score each: **2** shown and it worked, **1** claimed but not shown, **0** no or unknown, **n/a** does not
apply to the job we are buying for.

| # | Question | Score | What we saw |
|---|---|---|---|
| 1 | Which jobs does it do, and which do we already have covered? | | |
| 2 | Can it be configured entirely from files we generate? | | |
| 3 | If someone changes it on screen, can we tell? | | |
| 4 | Does it publish to our broker, or must it be the broker? | | |
| 5 | What happens to relationships? | | |
| 6 | Does it accept types from a published standard? | | |
| 7 | When a type changes, do existing assets follow? | | |
| 8 | What does it keep when the link drops, and whose timestamp does it use? | | |
| 9 | Does it send a value when it changes, or only on a timer? | | |
| 10 | How do people and systems sign in, how is it patched, and how are its flaws made known? | | |
| 11 | If it has an assistant, what leaves our network when it is used? | | |
| 12 | Can everything we put in come back out in an open format? | | |
| 13 | Who owns the model and data we put in, and may the supplier use them? | | |
| 14 | What does it cost at our size, and at renewal? | | |
| 15 | Who supports it, for how long, and what happens to us if the product ends? | | |
| | **Total, out of twice the number of questions that apply** | | |

A total is a summary, not a decision. A **0** on question 2, 3 or 12 matters more than the total: it means
the tool cannot be kept in step with your model, can be changed without anyone knowing, or cannot be left.
A **0** on question 10 is a matter for your security team before anything else.

## Build or buy

| Question | Our answer |
|---|---|
| Does this job encode what we know about our plant? (If yes, own it) | |
| Does it have to run all day, every day, and be patched? (If yes, buy it) | |
| If someone else builds it for us, do we own it and can we change it? | |
| If we built it, who is the second person who understands it? | |
| If we buy it, have we tested leaving? | |

## Our own test

| Test | Result | Notes |
|---|---|---|
| Loaded our ten-asset model | | |
| Renamed one asset in our files and reloaded | | |
| Exported and compared with what we put in | | |
| Seen running at our real number of values | | |

## Before deciding

- [ ] The tool we already own was scored on this sheet too
- [ ] We spoke to another organisation that already runs it
- [ ] Security has reviewed every connection it needs
- [ ] The role that owns the model has seen this sheet
- [ ] Our organisation's purchasing rules were followed
