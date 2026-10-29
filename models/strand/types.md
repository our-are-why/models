# types

a strand has a **type**: the kind of strand it is. any arrangement can have any
type. a type is concrete or abstract.

## concrete

a **concrete** type is a definite one, distinct from the others. there are
three: two solid types, and fluid.

### solid

a **solid** type has a form: its ends meet, or they don't. there are two:

    cell   0 1 2 3 4 5 6 7
           ■ ■ □ □ □ ■ □ □

- **circular**: a loop, with no ends: between two cells there are two
  distances, one each way round
- **linear**: a line, with two ends: between two cells there is one distance

in one dimension there are no others: finitely many cells in one piece, each
with at most two neighbours, make a loop or a line.

### the smallest circles and lines

the smallest solid strands are where the general rules reach their limits:

- **one cell**: as a circle, the cell is its own neighbour, both ways round; as
  a line, it's both ends at once
- **two cells**: as a circle, the two cells are neighbours twice, once each way
  round. from three cells on, every cell of a circle has two different
  neighbours

### fluid

**fluid** is undecided: neither circular nor linear yet, but it can come to
either. it says less than a solid: it leaves open what a solid settles.

## abstract

**abstract** is free: what the concrete types share, and no more, tied to no
particular semantics or use.

## the ends

the types can also be seen through a strand's ends. a strand's neighbours are
all settled but one pair: whether its two ends meet. each type answers it its
own way:

- **circular**: they meet, so there are no ends
- **linear**: they don't, so there are two
- **fluid**: neither answer, but it can come to either
- **abstract**: it sets the question aside

## change

a type says what a strand is, not what it can become. which changes between
types are possible is a separate matter, and a world settles it. fluid can
always come to circular or linear: that's what being undecided means. two
questions stay open:

- **returning**: can a solid strand go back to fluid?
- **between the solids**: can circular and linear become each other directly,
  by joining or parting the ends?

if nothing returns, change between fluid and the solids is
**unidirectional/hierarchical**: it goes one way only, from fluid to solid, so
fluid sits above the solids by movement as well as by what it says. if solids
can return, it's **bidirectional**: it goes both ways and orders nothing by
itself, though fluid still sits above the solids, because it still says less.

a strand whose ends can part and meet again isn't a type of its own: at any
moment, its ends meet or they don't. that it can open and close is change,
between circular and linear.
