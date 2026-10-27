# basics

a **strand** is a one-dimensional, discrete space of cells, with one of two
states in each cell.

    ■ ■ □ □ □ ■ □ □

- **one-dimensional**: the cells lie along a single dimension. from any cell
  you can only step one way or the other
- **discrete**: it's made of separate cells, with no positions in between
- **two states**: each cell is in exactly one of them, drawn here as ■ and □

the picture runs left to right, but a strand isn't laid out in any particular
way.

## space

a strand's **space** is its cells in order, apart from their states: where each
cell is, and which cells are next to each other. how many cells it has is its
**resolution**.

a strand's space is one kind of **discrete space**, which is one kind of space.

## types

a strand has a **type**: what its space is, beyond its cells in order.

- **concrete**: a definite type, distinct from the others:
  - **circular**: a loop, with no ends
  - **linear**: a line, with two ends
  - **fluid**: neither yet, but able to become either
- **abstract**: a general type: what the concrete types share, and no more

## two states

the strand doesn't say how its two states relate: that's a perspective, of two
kinds:

- **asymmetric**: the two states play different roles. what those roles are
  is left open
- **symmetric**: the two states play the same role: swapping them changes
  nothing but the names

## arrangement

a strand's **arrangement/distribution** is which cell is in which state. a
strand puts no condition on it: any arrangement is a strand, whether it follows
a clear pattern, has some structure, or has no rhyme or reason.

    ■ ■ □ □ ■ ■ □ □     a repeating pattern
    ■ ■ ■ □ □ □ □ □     one block
    ■ ■ □ □ □ ■ □ □     no particular pattern

the cells don't record where an arrangement came from: a careful rule and a
coin toss can give the same cells. an arrangement's **reason/origin**, and
whatever it means, live outside the strand, in its world.

## counts

the most universal thing to say about a strand's states, short of its whole
arrangement, is how many of its cells are in each state. these **counts** don't
depend on the type or the perspective, and the two add up to the resolution.

what counts leave out is where: two arrangements have the same counts exactly
when one is a reshuffle of the other. with 4 cells, 2 in each state, there are
six:

    ■ ■ □ □    ■ □ ■ □    ■ □ □ ■    □ ■ ■ □    □ ■ □ ■    □ □ ■ ■

## identity

by default, two strands are the same strand when they have the same resolution,
type and arrangement. other comparisons are more inclusive: they set something
aside, such as the type.

## zero

with no cells at all there's no space, and so no strand. it still has a name,
**zero**, because a function or a structure can arrive at no cells.

## worlds

these chapters are a framework, like those in mathematics or physics: a general
model, with perspectives and the reasoning behind them. a **world** is a
crystallization/realization of it, tailored to a use: it communicates its
semantics precisely, with as little room as possible for
miscommunication/misrepresentation.

a world can keep, redefine, leave out or add to anything in these chapters:
what the cells and states mean, the perspectives, the types, identity, even
what counts as a strand. where the chapters have to choose, they state a
default, which a world can override.
