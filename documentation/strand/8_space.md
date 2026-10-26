# space

**in short.** looking up from strands. a strand is the simplest case of a
discrete space, and working with it shows what a discrete space is in general.
this chapter names the general parts (cells, neighbours, values and
dimension), shows readings as boundary conditions, generalizes the measures,
and sorts what in these chapters holds for any discrete space from what holds
only in one dimension.

**builds on:** basics, measures, structures, functions, identity.

the concepts here are listed, with stable IDs, in [concepts.md](../concepts.md).

## looking up from strands

these chapters were worked out for strands, and nothing in them depends on
this one. but along the way, a more general idea kept showing through: a space
made of separate cells, each holding a value, with some cells next to others.
a strand is its simplest case: one dimension, two values.

this chapter writes the general idea down where it was found. if another kind
of space comes along, the general part can move to a home of its own, and this
chapter becomes a view of it from strands (see "cross-cutting topics", in
[documents](../documents.md)).

## a discrete space

a **discrete space**, in the sense used here, has three parts:

- **cells**: separate places, with nothing in between
- a **neighbour relation**: which cells are next to which. in a strand, a
  cell's neighbours are the cells one step away either way, and the joints are
  where neighbours meet
- **values**: each cell holds one value, from a set of values. a strand's set
  has two, true and null

_from memory_: in topology, a discrete space is something else. this is closer
to a graph whose vertices carry values: a labelled graph, the state of a
cellular automaton, or a lattice model in physics.

## dimension

the **dimension** of a discrete space is the shape of its neighbour relation:

- **one dimension**: cells in a row, each with at most two neighbours. it's a
  path, or a cycle when it's read circularly. that's a strand
- **two dimensions**: cells in a grid, with neighbours in two directions, such
  as a sheet
- **more**: the same idea, with more directions

in more dimensions, the neighbour relation is itself a choice. in a grid, a
cell may touch only the four cells beside it, or the eight around it, corners
included (_from memory_: image processing calls these 4- and
8-connectivity). one dimension has no such choice, which is part of why so
much of these chapters reads as close to self-evident.

## readings as boundary conditions

a strand's readings say what happens at its edges: read circularly, the last
cell meets the first; read linearly, the ends stop. _from memory_: physics and
simulation call these **periodic** and **open** boundary conditions.

in more dimensions there's a reading per dimension. a grid read circularly one
way and linearly the other is a cylinder; read circularly both ways, it's a
torus. fluid carries over too: a space whose edges haven't been given a shape.

## measures, generalized

- **resolution** becomes a size per dimension, and the number of cells is
  their product
- **density** becomes a count per value: for two values, density and
  sparsity; for more, a count for each
- **distance** becomes the number of steps through neighbours, taking the
  shortest way. a strand's default distance, the + one, needs a direction to
  count along, and only one dimension gives a direction for free
- **points** are still the positions of true cells, read asymmetrically. but
  "the next point" no longer has an obvious meaning, so intervals and gaps
  don't carry over as they are

## what carries over

a first sort of these chapters:

| holds for any discrete space | worked out only for one dimension |
| --- | --- |
| cells and values; true and null, and the two perspectives | steps and directions, + and − |
| resolution, density and sparsity, as counts | distance as the + one, by default |
| the negative | intervals, gaps and end gaps: "the next point" |
| any arrangement; the smallest cases; zero | seams, bands and runs; bands become regions |
| readings, as one boundary condition per dimension | scopes as ranges; they become boxes or regions |
| collections, stacks and weights; combining, cell by cell | layers, since points in a grid don't form a grid |
| generators, labels, descriptions, the symbol rules | join, insert and splice, which work at ends |
| essence and convention; identity's default | the notation as written: a row of symbols |

the functions that move cells around carry over in a different form. rotate,
reverse and mirror become the space's symmetries: shifts, reflections, and in
two dimensions, turns.

## the family

- **space**: the most general idea, only named here
- **discrete space**: this chapter
- **strand**: one dimension, two values: the chapters before this one
- deferred siblings: more dimensions, such as a sheet, and more values, such
  as a strand whose cells hold one of four (DNA is the familiar case)

## the case against

generalizing from one example risks mistaking its quirks for the general case:
the strand's single direction, its "next point", its two readings. the table
above is a first sort, not a proof. the right-hand column may hide ideas that
do carry over in another form, and the left may hide assumptions that only
hold in one dimension.

## related

_from memory_: graph theory; cellular automata, whose states are arrangements
of values on a discrete space; digital topology and digital geometry; lattice
models, such as the Ising model; boundary conditions, in physics and
simulation; combinatorics on words, for the one-dimensional case; symmetry
groups, such as the wallpaper groups in two dimensions.
