# basics

a **spacer** is a one-dimensional, discrete space made of cells, where each
cell is in one of two states.

    ■ ■ ◇ ◇ ◇ ■ ◇ ◇

- **one-dimensional**: the cells lie along a single dimension. from any cell
  you can only step one way or the other
- **discrete**: it's made of separate cells, with no positions in between
- **two states**: each cell is in exactly one of them, drawn here as ■ and ◇

the picture runs left to right, but that's only one way to draw it: a spacer
isn't horizontal, or in time, or laid out in any particular way.

a spacer is one kind of discrete space: one dimension, with each cell in one of
two states. everything in these chapters is worked out for one dimension, where
much of it is close to self-evident. spaces can have more dimensions, and their
cells can hold other kinds of values. but in more dimensions, things like
neighbours, distance and "the next point" stop being obvious, and many ideas
here may change shape. those paths are noted and deliberately left for later.
one other kind of value comes up with weights (see "structures").

## circular and linear

a spacer can be read in two ways. the cells and their states stay the same;
what changes is which cells are neighbours, and what a cell's position means.

    cell   0 1 2 3 4 5 6 7
           ■ ■ ◇ ◇ ◇ ■ ◇ ◇

- **circular**: the last cell is next to the first. there are no ends and
  every cell is alike: cell 0 is just where we start counting. a position is
  a place on the circle, and between two cells there are two distances, one
  each way round. what makes it circular is that the last cell meets the
  first; a circle is just the simplest shape that shows it, with every step
  the same size
- **linear**: the first and last cells are the ends. a position is an amount:
  how far from the start. between two cells there is one distance

a reading can also be left open: such a spacer is **fluid**, and can be read
either way later. once a spacer is read circular or linear, though, that
becomes part of what it is: it doesn't go back to fluid, or switch to the
other reading, on its own. turning one into the other takes a function (see
"functions"): unwinding a circle from its cell 0 gives a line, and winding a
line, so its ends join, gives a circle.

## true and null

a cell's two states are **true** (■) and **null** (◇). the pair can be seen in
two ways, and both are valid:

- **asymmetric, true/null**: a true cell holds something, and a null cell holds
  nothing. null isn't the opposite of true, but its absence: true cells are the
  things being spaced, and null cells are the space between them
- **symmetric, true/false**: neither state is special, and each is the other's
  negation. this is the perspective of logic, where the second state is
  **false**

true is the same in both; they differ only in what the other state is. the
measures in these chapters take the asymmetric perspective, and so do the words
for cells: true and null. the functions that combine spacers cell by cell come
from logic, and there null reads as false (see "functions"). elsewhere, the
same pair often shows up as 1 and 0.

null means absence, not unknown: a null cell is decided, and holds nothing. (in
databases, null often means "unknown", a third state; here there's no third
state.)

- **resolution**: how many cells a spacer has
- **density**: how many of them are true
- **sparsity**: how many are null

      ■ ■ ◇ ◇ ◇ ■ ◇ ◇     resolution 8, density 3, sparsity 5

density and sparsity always add up to the resolution.

these three say how many cells of each kind there are, not where they are,
so many spacers share the same three. with 4 cells, 2 of them true, there are
six:

    ■ ■ ◇ ◇    ■ ◇ ■ ◇    ■ ◇ ◇ ■    ◇ ■ ■ ◇    ◇ ■ ◇ ■    ◇ ◇ ■ ■

swap every cell's state and you get the spacer's **negative**: the same
arrangement/distribution, seen from its null space. the negative's density is
the original's sparsity. one determines the other, but they aren't the same
thing: a spacer and its negative are two different spacers. `Not(A)` gives A's
negative (see "functions").

## any arrangement

a spacer puts no condition on which of its cells are true: any
arrangement/distribution of true and null cells is a spacer, whether it
follows a clear pattern, has some structure, or has no rhyme or reason.

    ■ ■ ◇ ◇ ■ ■ ◇ ◇     a repeating pattern
    ■ ■ ■ ◇ ◇ ◇ ◇ ◇     one block
    ■ ■ ◇ ◇ ◇ ■ ◇ ◇     no particular pattern

so two things need keeping apart:

- **the spacer as a device**: open-ended. it only says there are cells, each
  true or null, and it holds any arrangement at all
- **the meaning of an arrangement**: whether a particular one follows a rule,
  and where it came from (a rhythm, a set of numbers, a coin toss). that
  belongs to the arrangement, not to spacers in general

the cells don't record where an arrangement came from: the same cells could
come from a careful rule or from tossing a coin, and nothing in them would show
which.

put another way: a true cell is just true. it carries no metadata about why
it's true, or what reason/origin put it there. whatever an arrangement
means lives outside the spacer, in what we know about where it came from.

later chapters look closely at particular kinds of arrangement; each is one
kind among all spacers, not what a spacer is.

## the smallest spacers

a spacer has at least one cell. the smallest ones are worth a look, because
they're where the general rules reach their limits.

- **all null** and **all true**: every cell in the same state. both are
  spacers, and each is the other's negative
- **one cell**: read circularly, the cell is its own neighbour, both ways
  round; read linearly, it's both ends at once
- **two cells**: read circularly, the two cells are neighbours twice, once
  each way round. from three cells on, every cell has two different neighbours

### zero

with no cells at all there's no space, and so no spacer. we still give it a
name, **zero**, because it can come up as the result of a change that leaves
no cells. zero isn't the all-null spacer: an all-null spacer is a space with
nothing in it; zero is no space at all.
