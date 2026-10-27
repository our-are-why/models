# types

**in short.** a strand's type says whether its last cell meets its first. this
chapter covers the concrete types: the solid ones, circular and linear, with
the smallest of each, and fluid, in its two kinds; then abstract; which types a
world uses; and how a type stays with a strand.

the concepts here are listed, with stable IDs, in [concepts.md](../concepts.md).

a strand has a **type**: what its space is, beyond its cells in order.
precisely, it's whether its last cell meets its first: the one question about
neighbours that the order of the cells leaves open. the cells and their states
stay the same whatever the type; what the type changes is which cells are
neighbours. a type is concrete or abstract (see "types", in "basics").

## concrete

a **concrete** type is a definite one, distinct from the others. there are
three: two solid types, and fluid.

### solid

a **solid** type holds its form: it settles whether the last cell meets the
first. there are two:

    cell   0 1 2 3 4 5 6 7
           ■ ■ □ □ □ ■ □ □

- **circular**: the last cell is next to the first, so there are no ends, and
  between two cells there are two distances, one each way round. on its own, a
  circle has no special cell: cell 0 is chosen. set against anything else,
  cell 0 is where it lines up, so the same circle started from a different
  cell relates differently
- **linear**: the first and last cells are the ends, and between two cells
  there is one distance

### the smallest circles and lines

the smallest solid strands are where the general rules reach their limits:

- **one cell**: as a circle, the cell is its own neighbour, both ways round; as
  a line, it's both ends at once
- **two cells**: as a circle, the two cells are neighbours twice, once each way
  round. from three cells on, every cell of a circle has two different
  neighbours

### fluid

**fluid** is adaptable: neither circular nor linear, but able to become either.
it has everything the solid types share, its cells in order, but not whether
its last cell meets its first. it comes in two kinds:

- **unidirectional/hierarchical fluid**: change goes one way only, from fluid
  to solid
- **bidirectional/sibling fluid**: change goes both ways: any of the three
  types can become any other

how a fluid strand becomes solid, and back, is in "commit" and "melt", in
"functions".

## abstract

an **abstract** strand has a general type: what the concrete types share, its
cells in order, and no more. a solid type may never apply to it.

an abstract strand is also what identity reaches when it sets the type aside:
circular, linear, unidirectional fluid and bidirectional fluid strands with
the same cells are different strands, but share one abstract strand (see
"identity").

## types and worlds

a world says which of abstract, unidirectional fluid and bidirectional fluid
it uses, possibly several (see "worlds", in "basics"). the running text is
written for unidirectional fluid. in an abstract world, read "fluid" as
"abstract", and `/…/` as `|…|` (the edges for each type are in "notation").

## types stay

a strand's type, whichever it is, is part of what it is, and it stays that way
unless a function changes it (see "types in and out", in "functions").
