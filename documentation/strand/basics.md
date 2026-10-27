# basics

**in short.** a strand is a one-dimensional space of cells, each in one of two
states. its type says whether its last cell meets its first: circular or
linear, or fluid or abstract, which leave that open. this chapter covers the
types; the two states, the perspectives on them and the names each gives them,
with the spacer as one asymmetric perspective among several; the counts
(resolution, density and sparsity), the points and the negative; why any
arrangement is a strand; and the smallest cases, down to zero, which isn't one.
it ends with worlds: the settings that decide what the defaults leave open.

the thinking behind it is in [the approach](../meta/approach.md).

the concepts here are listed, with stable IDs, in [concepts.md](../concepts.md).

a **strand** is a one-dimensional, discrete space made of cells, where each
cell is in one of two states.

    ■ ■ □ □ □ ■ □ □

- **one-dimensional**: the cells lie along a single dimension. from any cell
  you can only step one way or the other
- **discrete**: it's made of separate cells, with no positions in between
- **two states**: each cell is in exactly one of them, drawn here as ■ and □

the picture runs left to right, but that's only one way to draw it: a strand
isn't horizontal, or in time, or laid out in any particular way.

a strand is one kind of discrete space, and a discrete space is one kind of
space: one dimension, with each cell in one of two states. ("discrete" here
means made of separate cells with neighbours. _from memory_: in topology, a
discrete space is something else, and this is closer to a graph, a path or a
cycle; more in "space".) everything in these chapters is worked out for one
dimension, where much of it is close to self-evident. spaces can have more
dimensions, and their cells can hold other kinds of values. but in more
dimensions, things like neighbours, distance and "the next point" stop being
obvious, and many ideas here may change shape. those paths are noted and
deliberately left for later. one other kind of value comes up with weights (see
"structures").

## types

**builds on:** world, in "approach".

a strand has a **type**: whether its last cell meets its first. the cells and
their states stay the same either way; what the type changes is which cells are
neighbours. there are two **solid** types, each holding its form:

    cell   0 1 2 3 4 5 6 7
           ■ ■ □ □ □ ■ □ □

- **circular**: the last cell is next to the first, so there are no ends, and
  between two cells there are two distances, one each way round. on its own, a
  circle has no special cell: cell 0 is chosen. set against anything else,
  cell 0 is where it lines up, so the same circle started from a different
  cell relates differently
- **linear**: the first and last cells are the ends, and between two cells
  there is one distance

a strand's type can also leave that open: it has everything the two solid types
share, its cells in order, but not whether its last cell meets its first. that
can mean two things, with two names:

- **fluid**: a concrete type in its own right, adaptable: neither circular nor
  linear, but able to become either. it comes in two kinds: change goes one
  way only, from fluid to solid (**unidirectional/hierarchical fluid**), or
  both ways, with any of the three able to become any other
  (**bidirectional/sibling fluid**)
- **abstract**: the strand apart from either solid type: only what both share.
  a solid type may never apply to it

an abstract strand is also what identity reaches when it sets the type aside:
circular, linear, unidirectional fluid and bidirectional fluid strands with
the same cells are different strands, but share one abstract strand (see
"identity").

a strand's type, whichever it is, is part of what it is, and it stays that way
unless a function changes it (see "types in and out", in "functions").

## two states

**builds on:** perspective, in "approach".

every cell is in one of two states. the strand itself doesn't say what the two
are, or how they relate: that's a perspective, and there are two kinds:

- **asymmetric**: one state is something, and the other is its absence. the
  second isn't the opposite of the first, but the lack of it
- **symmetric**: neither state is special, and each is the other's negation

each kind can be named in more than one way, and no pair of names is the only
or the best one:

| perspective | default names | other names that fit |
| --- | --- | --- |
| asymmetric | **true** (■) and **null** (□) | present and absent, marked and unmarked |
| symmetric | **true** and **false** | 1 and 0, yes and no |

these docs prefer the asymmetric perspective, and call the states **true** and
**null** by default: the measures take that perspective, and so do the words
for cells. the functions that combine strands cell by cell come from logic,
which is symmetric, and there null reads as false (see "functions"). true is
the same in both default pairs; only the other name changes.

null means absence, not unknown: a null cell is decided, and holds nothing. (in
databases, null often means "unknown", a third state; here there's no third
state.)

the asymmetric perspective can be taken in more than one way:

- read as things, and the space between them, a strand is a **spacer**. the
  measures of intervals and gaps take this reading, and it's where these docs
  began: the domain was first called spacer
- read as which positions are chosen, it's a **selection**, the way a layer
  reads the strand above it
- read as onsets in time, it's a **rhythm**

these are named here, not developed, and there are likely others. each is a
perspective a world can take; the strand itself takes none of them.

## counts and points

- **resolution**: how many cells a strand has
- **density**: how many of them are true
- **sparsity**: how many are null

      ■ ■ □ □ □ ■ □ □     resolution 8, density 3, sparsity 5

density and sparsity always add up to the resolution.

these three say how many cells of each kind there are, not where they are,
so many strands share the same three. with 4 cells, 2 of them true, there are
six:

    ■ ■ □ □    ■ □ ■ □    ■ □ □ ■    □ ■ ■ □    □ ■ □ ■    □ □ ■ ■

what the counts leave out, the **points** give: the positions of a strand's
true cells. for `■ ■ □ □ □ ■ □ □` they're 0, 1 and 5, and the density is how
many there are.

swap every cell's state and you get the strand's **negative**: the same
arrangement/distribution, seen from its null space. the negative's density is
the original's sparsity. one determines the other, but they aren't the same
thing: a strand and its negative are two different strands. `Not(A)` gives A's
negative (see "functions").

## any arrangement

a strand puts no condition on which of its cells are true: any
arrangement/distribution of true and null cells is a strand, whether it
follows a clear pattern, has some structure, or has no rhyme or reason.

    ■ ■ □ □ ■ ■ □ □     a repeating pattern
    ■ ■ ■ □ □ □ □ □     one block
    ■ ■ □ □ □ ■ □ □     no particular pattern

so two things need keeping apart:

- **the strand as a device**: open-ended. it only says there are cells, each
  in one of two states, and it holds any arrangement at all
- **the meaning of an arrangement**: whether a particular one follows a rule,
  and where it came from (a rhythm, a set of numbers, a coin toss). that
  belongs to the arrangement, not to strands in general

the cells don't record where an arrangement came from: the same cells could
come from a careful rule or from tossing a coin, and nothing in them would show
which.

put another way: a true cell is just true. it carries no metadata about why
it's true, or what reason/origin put it there. whatever an arrangement
means lives outside the strand, in what we know about where it came from.

chapters still to come, starting with evenly spread arrangements, look closely
at particular kinds of arrangement; each is one kind among all strands, not
what a strand is.

## the smallest strands

a strand has at least one cell. the smallest ones are worth a look, because
they're where the general rules reach their limits.

- **all null** and **all true**: every cell in the same state. both are
  strands, and each is the other's negative
- **one cell**: as a circle, the cell is its own neighbour, both ways round; as
  a line, it's both ends at once
- **two cells**: as a circle, the two cells are neighbours twice, once each way
  round. from three cells on, every cell has two different neighbours

### zero

with no cells at all there's no space, and so no strand. we still give it a
name, **zero**, because it can come up as the result of a change that leaves
no cells. zero isn't the all-null strand: an all-null strand is a space with
nothing in it; zero is no space at all.

## worlds

a **world**, or semantic world, is the setting a strand is used in, with its
own semantics. it settles what these chapters leave open: the perspective on
the states, which of abstract, unidirectional fluid and bidirectional fluid it
uses, and what identity sets aside. by default, the running text takes the
asymmetric perspective and unidirectional fluid. in an abstract world, read
"fluid" as "abstract", and `/…/` as `|…|`. worlds aren't specific to strands:
they're part of [the approach](../meta/approach.md) behind all these docs.
