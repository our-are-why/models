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
two states. everything in this doc is worked out for one dimension, where much
of it is close to self-evident. spaces can have more dimensions, and their cells
can hold other kinds of values. but in more dimensions, things like neighbours,
distance and "the next point" stop being obvious, and many ideas here may
change shape. those paths are noted and deliberately left for later. one other
kind of value comes up with weights.

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
other reading, on its own. turning one into the other takes an operation (see
"operations"): unwinding a circle from its cell 0 gives a line, and winding a
line, so its ends join, gives a circle.

## filled and empty

a cell's two states are called **filled** (■) and **empty** (◇). in other
settings the same pair shows up as 1 and 0, or true and false.

which state is which is a choice, but not an arbitrary one: filled cells are
the things being spaced, and empty cells are the space between them.

- **resolution**: how many cells a spacer has
- **density**: how many of them are filled
- **sparsity**: how many are empty

      ■ ■ ◇ ◇ ◇ ■ ◇ ◇     resolution 8, density 3, sparsity 5

density and sparsity always add up to the resolution.

these three say how many cells of each kind there are, not where they are,
so many spacers share the same three. with 4 cells, 2 of them filled, there
are six:

    ■ ■ ◇ ◇    ■ ◇ ■ ◇    ■ ◇ ◇ ■    ◇ ■ ■ ◇    ◇ ■ ◇ ■    ◇ ◇ ■ ■

swap every cell's state and you get the spacer's **negative**: the same
arrangement/distribution, seen from its empty space. the negative's density is
the original's sparsity. one determines the other, but they aren't the same
thing: a spacer and its negative are two different spacers.

## any arrangement

a spacer puts no condition on which of its cells are filled: any
arrangement/distribution of filled and empty cells is a spacer, whether it
follows a clear pattern, has some structure, or has no rhyme or reason.

    ■ ■ ◇ ◇ ■ ■ ◇ ◇     a repeating pattern
    ■ ■ ■ ◇ ◇ ◇ ◇ ◇     one block
    ■ ■ ◇ ◇ ◇ ■ ◇ ◇     no particular pattern

so two things need keeping apart:

- **the spacer as a device**: open-ended. it only says there are cells, each
  filled or empty, and it holds any arrangement at all
- **the meaning of an arrangement**: whether a particular one follows a rule,
  and where it came from (a rhythm, a set of numbers, a coin toss). that
  belongs to the arrangement, not to spacers in general

the cells don't record where an arrangement came from: the same cells could
come from a careful rule or from tossing a coin, and nothing in them would show
which.

put another way: a filled cell is just filled. it carries no metadata about
why it's filled, or what reason/origin put it there. whatever an arrangement
means lives outside the spacer, in what we know about where it came from.

later chapters look closely at particular kinds of arrangement; each is one
kind among all spacers, not what a spacer is.

## the smallest spacers

a spacer has at least one cell. the smallest ones are worth a look, because
they're where the general rules reach their limits.

- **all empty** and **all filled**: every cell in the same state. both are
  spacers, and each is the other's negative
- **one cell**: in the circular view the cell is its own neighbour, both ways
  round; in the linear view it's both ends at once
- **two cells**: in the circular view the two cells are neighbours twice, once
  each way round. from three cells on, every cell has two different neighbours

### zero

with no cells at all there's no space, and so no spacer. we still give it a
name, **zero**, because it can come up as the result of a change that leaves
no cells. zero isn't the all-empty spacer: an all-empty spacer is a space with
nothing in it; zero is no space at all.
