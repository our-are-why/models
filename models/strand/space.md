# space

**in short.** looking up from strands. a strand is the simplest case of a
discrete space, and a stack's row of amounts is a second case, built from
strands. working with them shows what a discrete space is in general. this
chapter names the general parts (cells, neighbours, values and
dimension), shows types as boundary conditions, generalizes the measures,
and sorts what in these chapters holds for any discrete space from what holds
only in one dimension.

the concepts here are listed, with stable IDs, in [concepts.md](../concepts.md).

## looking up from strands

these chapters were worked out for strands, and nothing in them depends on
this one. but along the way, a more general idea kept showing through: a space
made of separate cells, each holding a value, with some cells next to others.
a strand is its simplest case: one dimension, two values. and it isn't the only
case here: a stack's **row of amounts**, its weights, is a discrete space too,
with the same cells, neighbours and type as the stack, but whole numbers
for values (see "weights", in "structures").

both cases come from strands, so this chapter writes the general idea down
where it was found. if a kind of space comes along that doesn't come from
strands, the general part can move to a home of its own, and this chapter
becomes a view of it from strands (see "cross-cutting topics", in
[documents](../documents.md)).

## a discrete space

a **discrete space**, in the sense used here, has three parts:

- **cells**: separate places, with nothing in between
- a **neighbour relation**: which cells are next to which. in a strand, a
  cell's neighbours are the cells one step away either way, and the joints are
  where neighbours meet
- **values**: each cell holds one value, from a set of values. a strand's set
  has two states, true and null by default. a row of amounts holds whole
  numbers, from 0 up to the number of members in its stack

_from memory_: in topology, a discrete space is something else. this is closer
to a graph whose vertices carry values: a labelled graph, the state of a
cellular automaton, or a lattice model in physics.

## dimension

the **dimension** of a discrete space is the shape of its neighbour relation:

- **one dimension**: cells in a row, each with at most two neighbours. it's a
  path, or a cycle when it's circular. that's a strand
- **two dimensions**: cells in a grid, with neighbours in two directions, such
  as a sheet
- **more**: the same idea, with more directions

in more dimensions, the neighbour relation is itself a choice. in a grid, a
cell may touch only the four cells beside it, or the eight around it, corners
included (_from memory_: image processing calls these 4- and
8-connectivity). one dimension has no such choice, which is part of why so
much of these chapters reads as close to self-evident.

## types as boundary conditions

a strand's type says what happens at its edges: circular, the last cell meets
the first; linear, the ends stop. _from memory_: physics and simulation call
these **periodic** and **open** boundary conditions.

in more dimensions there's a type per dimension. a grid that's circular one way
and linear the other is a cylinder; circular both ways, it's a torus. fluid and
abstract carry over too, for edges whose type is left open.

## measures, generalized

- **resolution** becomes a size per dimension, and the number of cells is
  their product
- **density** becomes a count per value: for two values, density and
  sparsity. for a row of amounts, how many cells hold each amount, and the
  total, which is the members' densities added together
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
| cells and values | steps and directions, + and − |
| two states, and the two perspectives on them, for two values | distance as the + one, by default |
| resolution, and a count per value | intervals, gaps and end gaps: "the next point" |
| the negative, for two values | |
| any arrangement; the smallest cases; zero | seams, bands and runs; bands become regions |
| types, as one boundary condition per dimension | scopes as ranges; they become boxes or regions |
| collections, stacks and weights; combining, cell by cell | layers, since points in a grid don't form a grid |
| generators, labels, descriptions, the symbol rules | join, insert and splice, which work at ends |
| essence and convention; identity's default | the notation as written: a row of symbols |

the functions that move cells around carry over in a different form. rotate,
reverse and mirror become the space's symmetries: shifts, reflections, and in
two dimensions, turns.

## the family

- **space**: the most general idea, only named here
- **discrete space**: this chapter
- **strand**: one dimension, two values: the rest of this domain
- **row of amounts**: one dimension, whole numbers: a stack's weights. it can
  be rebuilt from strands, since a row of amounts and a cascade of strands are
  two ways of writing the same thing (see levels and depths, in "functions")
- deferred: more dimensions, such as a sheet, and other sets of values, such
  as four letters in each cell (DNA is the familiar case)

## the case against

generalizing from two examples, both one-dimensional and one built from the
other, risks mistaking their quirks for the general case: a single direction,
"the next point", two types. the table above is a first sort, not a proof.
the right-hand column may hide ideas that do carry over in another form, and
the left may hide assumptions that only hold in one dimension.

## related

_from memory_: graph theory; cellular automata, whose states are arrangements
of values on a discrete space; digital topology and digital geometry; lattice
models, such as the Ising model; boundary conditions, in physics and
simulation; combinatorics on words, for the one-dimensional case; symmetry
groups, such as the wallpaper groups in two dimensions.
