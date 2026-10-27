# structures

**in short.** ways of building with strands. scopes take a piece of a strand,
and pieces can be scoped again. layers choose among a strand's points, and form
cascades. collections take several strands together, stacks line them up cell
by cell, and weights count across a stack.

the concepts here are listed, with stable IDs, in [concepts.md](../concepts.md).

## scopes

**builds on:** circular, in "basics"; edges, label, in "notation"; step,
scoped, in "measures".

a **scope** takes a piece of a strand. it's written after the strand, in square
brackets, and the strand's edges and resolution always come with it, because
how a scope behaves depends on both:

    S := |x.xx..|

    )6: S([5+3]      →  [.x.x]      from cell 5, 3 steps +
    )6: S([5->8]     →  [.x.x]      from cell 5 to cell 8, written in full: the same cells
    )6: S(-[5+3]     →  [..xx]      a − in front walks the other way: cells 5, 4, 3, 2
    <6: S>[2->5]     →  [xx..]      read linearly: cells 2 to 5
    <6: S>[5+3]      →  no piece    read linearly, S is bounded, and this runs past its end

- **relative**, `[start+steps]`: the steps go +. the start and end cells are
  both included, so 3 steps cover 4 cells
- **absolute**, `[start->end]`: always goes +. the end is written in full, not
  wrapped round: 8 at resolution 6 shows the walk passed the last cell and came
  round to cell 2
- **direction**: a − in front of the brackets walks the other way, and the
  piece is written in the order it was walked. the direction sign only ever
  sits outside the brackets, so a − inside them always means a position
  counted back from cell 0 (circular only): `)8: S([-2->2]` runs from two
  cells before cell 0 to two after it
- **laps**: in a circular strand, `~3%` means three full laps, without having
  to state the resolution. `)6: S([2~3%+5]` starts at cell 2, goes round 3
  times, then 5 more steps: 23 steps in all, or `[2->25]` as an absolute range.
  `%` is the programmer's wrap-around (modulo), so read `3%` as "3 laps", not
  "3 percent"
- **fluid**: in `|6: S|[…]`, what lies past the ends belongs to a shape,
  which a fluid strand doesn't have, so a scope has to stay within them
- **the result** is a scoped piece, `[…]`, with its own numbering: its cell 0
  is where the scope started, and its + runs the way the scope walked

### scopes of scopes

a scoped piece can be scoped again, using its own numbering: its cell 0 is
where it started.

    S := )xx...x..(
    A := )8: S([5+4]       →  [x..xx]      S's cells 5, 6, 7, 0, 1
    B := [5: A][2->4]      →  [.xx]        A's cells 2, 3, 4

the same thing can be written as a **chain**, where each bracket counts in the
piece the one before it made:

    )8: S([5+4][2->4]      →  [.xx]

a piece of a piece follows a few rules:

1. **it stays inside its parent**: it can't reach past the parent's first or
   last cell. `[5: A][3+4]` runs past A's end, so there's no piece
2. **no laps**: a scoped piece has ends, so there's no way round it. `~3%`
   only works on a circular strand
3. **the edges stay square**: a piece is always read as `[…]`. joining its
   ends to read it circularly would make a new strand, which is a change, not
   a scope: `Wind(Detach(A))` (see "functions")
4. **no repetition**: what lies beyond a piece is its parent, not copies of
   itself, so `~` doesn't apply
5. **everything else works as usual**: relative and absolute ranges, as long
   as the end stays inside the piece, and `-` for walking the other way

**back to the root.** because each piece stays inside its parent, any piece of
a piece is one unbroken stretch of the strand the chain was first taken from.
usually that's the **root**: the strand at the very top, which isn't a piece or
a layer of anything. if it's a layer (see "layers"), the layer is the first
piece's parent, and the chain can't look past it. to find where a piece sits,
go up one parent at a time: add the parent's start to the piece's start. if the
parent walked −, subtract instead, and flip the direction. you can stop at any
parent on the way up. a start can come out below 0, which can only happen when
the chain starts in a circle: at resolution 8, −2 and 6 name the same cell, but
−2 keeps how it was reached. either can be written.

    B starts at A's cell 2, and A starts at S's cell 5:   5 + 2 = 7
    B in S:   )8: S([7+2]  =  )8: S([7->9]          →  [.xx]

    C := )8: S(-[1+4]      →  [xx..x]      S's cells 1, 0, 7, 6, 5
    D := [5: C][1->3]      →  [x..]        C's cells 1, 2, 3
    D in S: C walked −, so 1 − 1 = 0, going −:   )8: S(-[0+2]   →  [x..]

the chain records how a piece was made; written as a scope of the root, it
records where it ends up. both show the same cells, but they're mounted on
different parents (see lift and collapse, in "functions").

## layers

**builds on:** density, points, in "basics".

a strand's true cells can become the cells of another strand. that second
strand is a **layer**: it chooses among the first one's points. the first
strand is the **root**, as with scopes.

    cell      0 1 2 3 4 5 6 7
    root      ■ ■ ◇ ◇ ◇ ■ ◇ ◇      points 0, 1, 5
    layer     ■ ◇       ■          its 3 cells are the root's 3 points; it keeps 0 and 5

layers form a **cascade**, which can go deeper: a layer's points can carry a
further layer, and so on.

- **the fitting rule**: a layer's resolution is the density of the layer above
  it. it can only choose among points that are there
- **distance at two scales**: in the layer, its cells 0 and 2 are two steps
  apart, since its steps go from point to point. on the root, the same two
  cells are five steps apart
- **one reading**: every layer is read the way its root is. points round a
  circle stay in circular order; points along a line stay in line order
- **each layer's own conventions**: a layer has its own cell 0 and direction,
  like any strand
- **zero ends a cascade**: if a layer is all null, a layer below it would have
  no cells, which is zero. so a cascade stops at its first all-null layer
- **flattening**: the deepest layer's choices can be shown on the root's
  cells: here, `|x....x..|`. the flattened strand doesn't show it was chosen in
  steps; like any origin, the cascade lives outside the cells (see press and
  flatten, in "functions")

layers aren't scopes. a scope takes a stretch of neighbouring cells; a layer
chooses among points, skipping the cells in between. both nest and both chain,
and they can be mixed: a scope of a layer is a stretch of consecutive points.

a scope of a layer has the layer as its parent, and can't look past it.
placing it on the cascade's root means following the layers up, which is
flattening, not scoping, and a stretch of consecutive points in a layer can be
scattered across the root: in `|xx...x..| >> |x.x|`, the layer's
cells 1 and 2 are the root's cells 1 and 5.

### writing layers

a cascade can be written from either end. each `>>` or `<<` points at the deeper
layer:

    |xx...x..| >> |x.x|          top-down: the root first, then the layer that chooses from its points
    |x.x| << |xx...x..|          bottom-up: the layer first, placed into the root's points
    |8: 0,1,5| >> |3: 0,2|       point form: the root has 3 points, so the layer has 3 cells
    A >> B >> C                  labels, to any depth; C << B << A is the same cascade

- top-down reads as choosing: start from the root and pick points layer by
  layer. bottom-up reads as placing: start from a small strand and fit it into
  larger ones
- every layer repeats the root's edges, so a circular cascade is `)…( >> )…(`. a
  cascade can't mix readings
- a chain goes one way only: `A >> B << C` isn't written

in the display form, the root sits at the top, whichever way the cascade is
written, and each layer's cells sit under the points they stand for:

    ■ ■ ◇ ◇ ◇ ■ ◇ ◇
    ■ ◇       ■

### cells that open into strands

a different kind of nesting, noted here as a concept only: each cell of a
strand opens into a strand of its own, the way a tile can be divided into
smaller tiles. it's close to refinement, and it's left for later.

## collections, stacks and weights

### collections

**builds on:** strand, in "basics".

a **collection** is several strands taken together. two things about a
collection are independent of each other:

- **order**: whether its members come in a set order
- **repeats**: whether the same strand can appear more than once

each combination has an established name:

|               | no repeats             | repeats allowed            |
| ------------- | ---------------------- | -------------------------- |
| **unordered** | set: `{A, B, C}`       | multiset: `{#A, A, B#}`    |
| **ordered**   | ordered set            | sequence: `(A, A, B)`      |

an ordered set is written like a sequence whose members all differ. the display
form can write a multiset with bag brackets: `⟅A, A, B⟆`.

what counts as a repeat depends on what counts as the same strand, so, like
identity, whether a collection has repeats is decided by the use. a description
picks out strands too, and what it gives can be any of these kinds:
`{r: 8, d: 3}` gives every fitting strand once, but other descriptions can give
repeats, or an order.

### stacks

**builds on:** reading, in "basics".

to count across a collection, its strands are **stacked**: lined up cell by
cell. stacking is a device for working with strands, not a new kind of strand,
and it needs a few things settled:

- every member has the same resolution
- each member sits in a **frame**: the fixed choices that say how it lines up,
  meaning which of its cells is cell 0, which way it runs, and how it's read.
  by default, a strand is framed as written, with its cell 0 over the stack's
  cell 0
- all members share one reading, and the edges around a stack say which:

      )(x.., .x.)(      circular
      <(x.., .x.)>      linear
      |(x.., .x.)|      fluid
      )(A, B)(          labels too: reads both A and B circularly

  edges around anything apply a reading to it, the way `)S(` reads S
  circularly, as long as what's inside is fluid or already reads that way.
  so the members inside are written bare. for now, a stack can't mix readings

framing is where identity gets decided: a stack takes each strand exactly as
framed, so `)x.x..(` and `)x..x.(` add to different columns, although read
circularly one is the other started from a different cell.

### weights

**builds on:** true, points, in "basics".

    cell      0 1 2 3 4 5 6 7
    A         ■ ■ ◇ ◇ ◇ ■ ◇ ◇
    B         ■ ◇ ◇ ■ ◇ ■ ◇ ◇
    C         ◇ ■ ◇ ◇ ◇ ■ ■ ◇
              ---------------
    weights   2 2 0 1 0 3 1 0

- the **cell weights** count the true cells in each column. they ignore order
  and count every repeat
- the weights live in a space of their own: the same cells and reading as the
  stack, but each cell holds an amount instead of one of two states, so a row
  of weights isn't a strand. it's another kind of discrete space (see
  "space"). a circular or linear stack says the reading is part of the
  structure; a fluid one has no shape, and a use can give it one
- the weights add up to the members' densities together (9 here), and no
  weight is more than the number of members
- a member's **strand weight** (or score) is the weights added up at its
  points: how much it agrees with the whole, itself included. A's is
  2 + 2 + 3 = 7; B's and C's are 6
- an ordered stack has **stages**: its running weights as each member goes
  on. unlike the final weights, it depends on the order:

      after A    1 1 0 0 0 1 0 0
      after B    2 1 0 1 0 2 0 0
      after C    2 2 0 1 0 3 1 0

weights are a derived result, and for most stacks they're just that: a count.
but when the strands going in are patterned, the weights can carry structure of
their own: structure of the whole that no member shows on its own, which is
what's sometimes called weak emergence. then they become objects worth studying
in their own right: a space of amounts, where the amount works almost like an
extra dimension. that space is placed among discrete spaces in "space", but
not explored further here.

weights are written as a row of numbers, which are amounts, not states (rule 4,
in "notation"): `|2 2 0 1 0 3 1 0|`. `Weights((A, B, C))` gives a stack's
weights as such a row.

the row takes the stack's reading, written with the same edges: a circular
stack gives `)2 2 0 1 0 3 1 0(`, a linear one `<2 2 0 1 0 3 1 0>`, and a fluid
one `|2 2 0 1 0 3 1 0|`. the display form keeps the edges, since no cells are
drawn. for example, `Weights( )(A, B, C)( )` gives `)2 2 0 1 0 3 1 0(`.

the stages are written as a sequence of rows, one per step: `Stages((A, B, C))`
gives `(|1 1 0 0 0 1 0 0|, |2 1 0 1 0 2 0 0|, |2 2 0 1 0 3 1 0|)`. its last row
is the stack's weights.

("weight" has another meaning in coding theory, where a string's weight is its
number of 1s; here, that's density. here, weights are always taken across a
stack: cell weights per cell, and a strand weight per member.)
