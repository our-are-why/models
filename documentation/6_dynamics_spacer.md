# dynamics

**in short.** generators are precise rules or processes that make a spacer at
each resolution. following one without end goes towards infinity, which is
never reached and isn't a spacer. generators are described by independent
facets: how their spacers relate as they grow, how cells are decided, how clear
the rule is, how the result looks, and where it comes from.

**builds on:** basics, notation, functions.

the concepts here are listed, with stable IDs, in [concepts.md](concepts.md).

## going to infinity

every spacer has a finite number of cells. infinity comes in through a
**generator**: a precise rule or process that makes a spacer at each
resolution, n, that it covers. it doesn't have to cover them all: one might
only make spacers with an even number of cells, or only ones that double each
time. the rule has to say exactly which cells are true; a loose phrase like
"the first half" isn't enough, since it leaves cases like 5 cells open.
how the rule is written is up to whoever defines the generator.

how its spacers change as n grows is its **resolution dynamics**, and going to
infinity means following them without end.

what lies at the end isn't a spacer, just as zero isn't: there's no last
resolution, and so no spacer with endless cells. we only ever hold the finite
spacers on the way. zero sits below the smallest spacer and infinity beyond
every one; both are named, and neither is a spacer.

like any origin, a generator lives outside the spacers it makes: a spacer
doesn't show which generator made it.

a generator uses the same brace form as a description, followed by `->` and
what it makes: `Primes{r: 8} -> |..xx.x.x|`. the braces say which spacers are
asked for; the arrow is what makes it a generator. with chance involved, the
arrow gives one possible result: `Coin{r: 8} -> |x..x.xx.|` is one run out of
256 possible. fuller notation for generators will come later: for ones that
only cover a range of resolutions, ones that run on without end, and for how
rules are written (directly cell by cell, step by step from earlier spacers, or
case by case).

as a shorthand, the values can go in round brackets, in a fixed order and
without keys: `Primes(8) -> |..xx.x.x|`. the order comes from the generator's
**signature**, which lists its keys in order, the same way each function is
introduced with its values in order (`Rotate(S, k)`):

    Primes(r)                    one value: the resolution
    Block(r, d)                  the first d cells true: first the resolution, then the density
    Block(8, 3)                  means  Block{r: 8, d: 3}
    Block(8, 3) -> |xxx.....|

keys in a signature are mapped to their full names, like any short key. braces
have no order, so in braces every value needs its key. a label directly before
round brackets gives a generator its values; round brackets on their own are a
stack.

generators are described by a few independent **facets**. each can be read on
its own, and any combination can occur, with one exception noted below.

**how spacers relate as n grows**

- **growth/extension**: earlier cells never change; new ones are added. it
  reads like time passing, and fits the linear reading, where a line has an
  end to grow from. making the cells whose number is prime true:
  `|..xx.x.x|` → `|..xx.x.x...x|`
- **refinement/subdivision**: each spacer describes the same whole at a finer
  grain, in either reading. making cell j true when 2j is less than n:
  `|xx..|` → `|xxx..|` → `|xxx...|` → `|xxxx....|`. what counts as "the same
  whole" depends on the context; refinement is named here as one force in a
  spacer's dynamics, not pinned down
- **both**, or **neither** (each spacer made from scratch)

**how cells are decided**

- **rule/deterministic**: a rule fixes every cell
- **chance/indeterministic**: chance decides, like a coin toss for each new
  cell: `|x..x.xx.|` → `|x..x.xx.x...|` (one possible run)
- **rule and chance**: rules decide which cells chance gets to decide

**how clear the rule is** (only where there's a rule)

- **transparent**: the pattern can be read off and carried forward
- **opaque**: seeing part of the spacer doesn't tell you the rest; you have to
  apply the rule each time, as with the primes. a rule can also be unknown
  altogether: a black box

**how the result looks**

- **patterned**: the arrangement shows a pattern
- **random-like**: it passes for chance, judged against some baseline. the
  primes look random-like once their simplest structure is set aside (beyond
  3, every prime is one more or one less than a multiple of 6)

**where it comes from**

- **natural/found**: nobody designed it; it arises from arithmetic or from
  physics. the primes are found in arithmetic
- **made/designed**: someone built it. a computer's random number generator is
  a rule designed to look random, which is what **pseudo-random** means

how a spacer is decided and how it looks are separate facets. the primes are
decided by a rule but look random-like; choosing at random where to start
reading `)xx..xx..(` is chance, but every result is patterned.

the facets can be read flat, or grouped by where each one lives: in the cells
(how the result looks), in the generator (how spacers relate, how cells are
decided), in what we know (how clear the rule is) and in the origin (where it
comes from). either way, they're the same facets.
