# Build or buy?

*Optional. About 4 minutes.*

Some parts of this approach are worth writing yourselves. Most are not. This page gives a starting position
for each part, and four questions for the cases it does not settle. It names no products.

"Buy" here includes adopting open-source software. It is free to license and still costs people, skills and
support. "Build" means writing and maintaining something yourselves.

There is a third option, and for many utilities it is the usual one: **have someone build it for you.** Work
done by an integrator or a consultant is still built, and question 3 below applies to it in full. Before the
work starts, agree in writing that you own what is written, that you receive it in a form you can read and
change, and that someone on your own staff has run it.

## A starting position, part by part

The parts are the same nine as on [Choosing tools](choosing-tools.md#the-jobs-to-be-done): three that are
yours, and six jobs a product can do.

| Part | Usual choice | Why | When the other choice makes sense |
|---|---|---|---|
| **The model** | **Own it** | It is your knowledge of your plant. Nobody sells that | Never. Reuse published standards inside it, but the model is yours |
| **The checks on the model** | Build, small | They are simple rules about your own files. The check columns in the [spreadsheet template](../../examples/workshop-kit/) are a first version | A tool you already use can run them |
| **The program that turns the model into tool settings** | Build, small | It is glue, and should stay thin | A tool can read your files directly |
| **Collect at the edge** | **Buy** | Reading many kinds of equipment takes drivers that are costly to write and keep current | One or two simple sources that a small script can read |
| **Broker** | **Buy** | It must be reliable, secure and patched around the clock. That is a full-time job for its maker | Almost never |
| **Historian** | **Buy** | Storing and retrieving years of data efficiently is hard, and already solved | Almost never |
| **Graph or modelling tool** | Start small, buy when it grows | The graph is rebuilt from your model, so a small library can hold it at first | Buy when many people need to explore it, or you want screens, access control or an assistant on top |
| **Open API** | Use the published standard; buy a product that implements it | Inventing your own interface recreates the lock-in you are trying to leave | A thin layer of your own over tools that lack one, following the same standard |
| **Analysis and screens** | Build the rules, buy the screens | The rules encode how your plant behaves. Screens are a solved problem | A tool has the exact rule you need built in |

This is a common starting position, not a rule. Your team's size and skills can move any row.

## Four questions that settle most cases

1. **Does it encode what we know about our plant?** Own it. That is the model and the rules.
2. **Does it have to run all day, every day, and be patched?** Buy it. That is the broker, the historian and
   the edge.
3. **Who looks after it when its author moves on?** Anything built needs a second person who understands it,
   whether it was written by your staff or by a contractor. If you cannot name one, buy.
4. **Can we leave?** For anything bought, the answer has to be yes, tested, before you depend on it.

## The pattern in one line

**Buy the plumbing, own the meaning, and keep the glue small.**

- **The plumbing** moves and stores data. It is the same for every utility, and others do it better than you
  could.
- **The meaning** is your model and your rules. It is different for every utility, and only you can write it.
- **The glue** joins the two. Every line of it is something you must maintain, so write as little as you can.

## A caution about what you build

Home-built glue has a habit of growing into a product that one person understands. Three habits keep it small:

- Keep it in version control, with a short note on what it does and how to run it.
- Have a second person run it at least once.
- When a tool gains the ability to read your files directly, delete the glue.

Next: [An incident, followed through the graph](an-incident-followed-through.md).
