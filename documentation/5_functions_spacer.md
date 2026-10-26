# functions

**in short.** functions take spacers, or things made from them, and give one
back. primitives each do one basic thing, such as rotate, join, commit or
threshold; named composites are built from them, such as repeat, splice or
flatten. lines and circles get their own functions, and a fluid spacer can
borrow a reading while a function works.

**builds on:** basics, notation, measures, structures.

the concepts here are listed, with stable IDs, in [concepts.md](concepts.md).

a **function** takes spacers, or things made from them (pieces, cascades,
stacks, rows of amounts), and gives one back. most are written with the
function's name, then its values in round brackets, in a stated order, the way
generators take their values. like stacking, a function works on spacers as
written, by default.

(in algebra, an **operation** on a set takes members of that set and gives back
a member of the same set. many functions here are operations in that sense:
rotate takes a circle and gives a circle. not all of them are: threshold takes
a row of amounts and gives a spacer. so the general word here is function, and
"operation" keeps its maths meaning.)

functions come in two kinds:

- **primitives**, which each do one basic thing: commit (and, in some worlds,
  melt), rotate, slide, reverse, mirror, join, unwind, wind, detach, lift,
  press, weights and threshold, along with taking a scope, layering (`>>`),
  and the cell-by-cell `Not`, `And`, `Or`, `Xor` and `Without` (see
  "combining spacers", below)
- **named composites**, which are made of primitives and named because they're
  useful: repeat, insert, splice, collapse, flatten, stages, at most, exactly,
  levels and depths. each is defined by the primitives it's made of, so
  composites can be added or dropped without touching anything else

a primitive is one because it does one basic thing, not because nothing else
could build it. some primitives can also be built from others; when they can,
that's a cross-check, not a reason to make them composites.

functions never change a spacer in place: they always give a new one, and what
went in stays as it was.

most functions work on a spacer's cells. a few work on a **view** instead: a
window onto a spacer, which changes what's looked at, not the spacer itself.
taking a scope, sliding it and lifting it are of this kind. detach and flatten
are the bridges from a view, or a cascade, back to a spacer of its own.

what's allowed depends on the readings going in, by the same idea as stacks:
writing a spacer circular or linear says its reading is part of its structure;
writing it fluid leaves the shape out, so it can take whichever one the
function needs.

a function can borrow a reading while it works, as long as just one reading
makes sense for it and its result doesn't depend on it afterwards, and **fluid
in gives fluid out**: committing to a reading is left to whoever uses the
result. a fluid spacer can be rotated as a circle and then read as a line: with
`N := |xx...x..|`, `Rotate(N, 5)` is `|x..xx...|`, and `<Rotate(N, 5)>` is
`<x..xx...>`. the only exceptions are the functions whose job is to change a
reading: unwind and wind.

each function does one kind of thing to one kind of spacer. when the same idea
means different things for lines and circles, they get different functions,
rather than one function that behaves differently depending on what it's
given.

## combining spacers

two spacers with the same resolution can be combined cell by cell into a new
spacer. like stacking, this frames both spacers, as written by default, and the
same reading rules apply: both circular, both linear or both fluid, and the
result takes their reading.

    A                ■ ■ ◇ ◇ ◇ ■ ◇ ◇
    B                ■ ◇ ◇ ■ ◇ ■ ◇ ◇
    And(A, B)        ■ ◇ ◇ ◇ ◇ ■ ◇ ◇      true where both are
    Or(A, B)         ■ ■ ◇ ■ ◇ ■ ◇ ◇      true where at least one is
    Xor(A, B)        ◇ ■ ◇ ■ ◇ ◇ ◇ ◇      true where exactly one is
    Without(A, B)    ◇ ■ ◇ ◇ ◇ ◇ ◇ ◇      true where A is and B isn't

the negative is the same idea for one spacer: `Not(A)` is true wherever A
isn't.

each of these applies one rule to every cell, so all five are primitives. some
could be built from others, `Without(A, B)` is `And(A, Not(B))`, but each does
one basic thing. they're the familiar operations of logic, and of sets read on
the points: `And` is intersection (∩), `Or` is union (∪), `Xor` is symmetric
difference (△), `Without` is difference (∖), and `Not` is the complement.
these functions take logic's symmetric perspective, where null reads as false
(see "true and null", in "basics").

they're also thresholds on weights: stack A and B, and `And(A, B)` is where the
weight is 2, `Or(A, B)` where it's at least 1, and `Xor(A, B)` where it's
exactly 1. with more spacers in a stack, any threshold works the same way, such
as "at least two of them" (see threshold, below).

`And`, `Or` and `Xor` take any number of spacers, since grouping them
differently doesn't change the result: `Or(A, B, C)` is true where at least
one is, and `And(A, B, C)` where all are. but `Xor(A, B, C)` doesn't mean
"exactly one": it's true where an odd number are. with the stack A, B, C from
"weights", in "structures", that's `|...x.xx.|`, while "exactly one" is
`|...x..x.|`.

## primitives

### commit

committing gives a fluid spacer a reading, by putting edges around it. it's
more than a way of looking at it: the cells stay as they are, but the result is
a new spacer, whose reading is part of what it is. the fluid one stays fluid.
in programming terms, it's a cast: turning a value into a more specific type.

    N := |xx...x..|
    )N(                       →  )xx...x..(       committed circular
    <N>                       →  <xx...x..>       committed linear

a literal can simply be written committed from the start: `)xx...x..(`. edges
can also go around an expression, or around something passed to a function.
wherever an edge would touch another bracket, a space keeps them apart:
`) Rotate(N, 5) (`, `Rotate( )N(, 5)`.

there are two places to commit, and they say different things:

- **on what goes in**: `Rotate( )N(, 5)` commits N as a circle before rotating
  it, so the result is a circle too: `)x..xx...(`. this says the circle is
  part of the structure. using the result as a line afterwards takes a
  conversion: `Unwind(Rotate( )N(, 5))` gives `<x..xx...>`
- **on what comes out**: `<Rotate(N, 5)>` keeps N fluid through the rotation,
  which borrows a circular reading, and commits only the result, as a line:
  `<x..xx...>`. this says the circle was only needed for the move

both arrive at the same cells here. which to use depends on whether the reading
is part of the structure, or a shape given later.

commitment is one-way by default: nothing takes a committed spacer back to
fluid. that fits a world where fluid is abstract, or hierarchical (see "what
fluid is", in "basics").

### melt, in some worlds

in a world where fluid is a sibling of circles and lines, `Melt(S)` forgets a
committed spacer's shape, and gives the fluid spacer with the same cells:

    Melt( )xx...x..( )      →  |xx...x..|
    Melt(<xx...x..>)        →  |xx...x..|

- the triangle closes: unwinding is melting and committing as a line,
  `Unwind(C)` is `<Melt(C)>`, and winding is `) Melt(L) (`
- where the shape is essential, melting throws away meaning, and isn't valid:
  a clock face is a circle in any world that cares about time
- in a hierarchical world, melt usually doesn't fit, since the forms only come
  from fluid. but if the hierarchy is read as "a circle is a fluid spacer with
  a shape added", forgetting the shape is always possible. so even there, the
  world decides

### rotate

`Rotate(S, k)`, a **rotation/phase**, starts S from its cell k: the cells come
round in the same order, and cell k becomes cell 0. k can be negative: −2 is
two cells back from cell 0.

    S := )xx...x..(
    Rotate(S, 5)       →  )x..xx...(
    Rotate(S, -2)      →  )..xx...x(

- **circular**: yes. this is the rotating described in "writing a spacer
  down", in "notation"
- **fluid**: yes, read circularly for the move; the result stays fluid
- **linear**: no. a line has no way round to rotate along. a scoped piece can
  slide along its parent instead

### slide

`Slide(A, k)` moves a scoped piece along its parent: the window keeps its
length, and starts from what was its cell k, which can lie beyond its end. it
works on the view, not on a spacer: the parent stays as it is, and only the
part the window shows changes.

    S := )xx...x..(
    A := )8: S([5+4]       →  [x..xx]       S's cells 5, 6, 7, 0, 1
    Slide(A, 2)            →  [.xx..]       S's cells 7, 0, 1, 2, 3: )8: S([7+4]
    Slide(A, -1)           →  [.x..x]       S's cells 4, 5, 6, 7, 0

    T := <xx...x..>
    B := <8: T>[2->5]      →  [...x]
    Slide(B, 2)            →  [.x..]        T's cells 4 to 7
    Slide(B, 3)            →  not allowed   it would run past T's end

- it moves k steps the way the window walks, in its own + direction
- **circular parent**: it slides freely, wrapping round
- **linear parent**: it can't pass the parent's ends. sliding only as far as it
  can (clamping), or letting the window shrink, would both change what was
  asked for without saying so
- **fluid parent**: within the ends, it slides as usual. crossing an end would
  only make sense if the parent were circular, and the window stays tied to its
  parent afterwards, so the parent's reading has to be committed first: for a
  fluid parent N, `)N(` to wrap round, `<N>` to stay bounded
- a scope of a scope slides within its immediate parent. lifting it first lets
  it slide within the parent above (see lift)
- it undoes cleanly: `Slide(Slide(A, 2), -2)` is A again, as long as each slide
  was allowed

### reverse

`Reverse(L)` runs a line's numbering the other way: its ends swap, so
`<xx...x..>` becomes `<..x...xx>`.

- **linear**: yes
- **circular**: no; a circle is mirrored instead
- **fluid**: yes, read as a line for the move; the result stays fluid.
  `Reverse(|xx...x..|)` is `|..x...xx|`, while `Mirror(|xx...x..|)` is
  `|x..x...x|`: two different functions, so nothing is left ambiguous

### mirror

`Mirror(C)` mirrors a circle, pivoting on cell 0: cell 0 stays where it is, and
cell j goes to cell −j, so the other cells come round the other way.

    )xx...x..(   →  )x..x...x(       8 cells: the mirror line runs through cell 0 and cell 4
    )xx..x..(    →  )x..x..x(        7 cells: through cell 0 and the joint between cells 3 and 4

- **circular**: yes. whether the mirror line comes out at a cell or at a joint
  on the far side depends on whether the resolution is even or odd; the
  function is the same either way
- **fluid**: yes, read circularly for the move; the result stays fluid
- **linear**: no; that's reverse
- mirroring twice gives the circle back, and mirror and rotate combine the way
  reflections and turns do: `Mirror(Rotate(C, k))` is `Rotate(Mirror(C), -k)`
- any other mirror line is a mirror and then a rotate. the line through the
  joint before cell 0 is `Rotate(Mirror(C), 1)`, which is also
  `Wind(Reverse(Unwind(C)))`: reading the cells backwards and closing them
  again

### join

`Join(A, B)` puts B after A's last cell: two lines, end to end, make a longer
line.

    Join(<x.>, <.xx>)      →  <x..xx>

- only something with free ends can be joined: a line, or a fluid spacer read
  as one. joining two fluid spacers gives a fluid one; joining a fluid spacer
  to a line gives a line
- a circle written circular says it has no ends, so there's nothing to attach.
  if its circularity is only a perspective, it can be written fluid, and then
  it can be joined
- a scoped piece has ends, but they aren't free: just past each one is its
  parent's next cell, and attaching something there would contradict the
  parent. detach it first

### unwind and wind

these two change a committed reading, so they're the only functions that turn
a circle into a line, or a line into a circle.

`Unwind(C)` opens a circle into a line, starting from its frame's cell 0.
`Wind(L)` joins a line's two ends into a circle.

    C := )x..(
    Unwind(C)               →  <x..>          the same cells, now as a line
    Wind(<x..>)             →  )x..(          the ends join
    Repeat(Unwind(C), 3)    →  <x..x..x..>    three laps: unwind, then repeat

- each does one thing: unwind only opens, and wind only joins the ends. laps
  come from repeat
- the round trip loses nothing: winding an unwound circle gives it back, and
  unwinding a wound line gives the line back, since both start at cell 0
- unwind takes a circle and wind takes a line: they're the conversions between
  the two committed shapes. a fluid spacer doesn't need them, since it commits
  directly, as `)N(` or `<N>`. this keeps the two moves apart, as the
  comparisons in "identity" do: committing is fitting (`~=`), and converting
  is unwind and wind (`<->`)
- unwinding starts where the spacer's frame starts, its cell 0 as written;
  starting somewhere else means rotating first
- a circular scope with laps walks the same cells as unwinding and repeating:
  `)3: C([0~2%+2]` gives `[x..x..x..]`, a scoped piece

unwinding can also happen over time: a generator that unwinds one more cell at
each resolution, where cell j copies C's cell j, counting round C as many times
as needed. earlier cells never change, so it grows: `|x|` → `|x.|` → `|x..|` →
`|x..x|` → …, and without end it reaches C repeating: `)x..(~`.

### detach

`Detach(A)` takes a scoped piece's cells out of their context, as a line of
their own: the window's edges become free ends.

    S := )xx...x..(
    A := )8: S([5+4]       →  [x..xx]
    Detach(A)              →  <x..xx>

- the result is linear: a piece is already linear in its own terms, and a
  reading only goes one way. `Wind(Detach(A))` makes it a circle
- detaching forgets the context: the parent, and where the piece sat in it. so
  `Detach(A) === A`, the same cells, but they aren't the same spacer: one is
  whole, the other a part. there's no way back, except taking the scope from
  the parent again
- it's what lets a piece be used on its own: joined, or studied as a spacer in
  its own right

### lift

`Lift(B)` takes one step up a chain of scopes: it gives B as a scope of its
parent's parent, by the rule in "back to the root" (in "structures").

    S := )xx...x..(
    A := )8: S([5+4]       →  [x..xx]       S's cells 5, 6, 7, 0, 1
    B := [5: A][2->4]      →  [.xx]         A's cells 2, 3, 4
    Lift(B)                →  [.xx]         )8: S([7+2]: S's cells 7, 0, 1

- the cells it shows stay the same; what changes is the parent it's mounted
  on. a parent's ends are where a scope has to stop, and the parent above
  always contains the one below, so a lifted piece has at least as much room:
  `Slide(B, 1)` isn't allowed, since it would run past A's end, but
  `Slide(Lift(B), 1)` is `[xx.]`, S's cells 0, 1, 2
- it isn't allowed when the parent is a root or a layer: there's nothing above
  it that a scope can reach
- it forgets the parent it skipped, so there's no way back: many chains lift
  to the same scope

### press

`Press(K)` takes one step up a cascade: it presses the deepest layer onto the
layer above, so the cascade has one layer fewer. the pressed layer keeps the
upper layer's resolution, and shows the deepest choices on its cells.

    K := |xx...x.x| >> |x.xx| >> |.xx|
    Press(K)               →  |xx...x.x| >> |..xx|
    Press(Press(K))        →  |.....x.x|

- a root with one layer presses to a single spacer, with the root's
  resolution and reading
- it forgets one layer, the way lift forgets one parent: the result doesn't
  show that it was chosen in two steps
- there's no way back: many cascades press to the same one

### weights

`Weights(S)` counts a stack's true cells, column by column, and gives the row
of amounts, with the stack's reading (see "weights", in "structures"):

    Weights((A, B, C))          →  |2 2 0 1 0 3 1 0|
    Weights( )(A, B, C)( )      →  )2 2 0 1 0 3 1 0(

### threshold

`Threshold(W, k)` turns a row of amounts back into a spacer: a cell is true
where its amount is at least k, and the result keeps the row's reading. it's
the bridge from amounts back to states, the way detach is the bridge from a
view. with the stack A, B, C from "weights", in "structures":

    W := Weights((A, B, C))     →  |2 2 0 1 0 3 1 0|
    Threshold(W, 1)             →  |xx.x.xx.|       at least one of them
    Threshold(W, 2)             →  |xx...x..|       at least two
    Threshold(W, 3)             →  |.....x..|       all three

for two spacers, `Or` and `And` are the two simplest thresholds: `Or(A, B)` is
`Threshold(Weights((A, B)), 1)`, and `And(A, B)` is
`Threshold(Weights((A, B)), 2)`. that's a cross-check, not their definition.

## named composites

each of these is made of primitives, and its definition says how. `:=` reads
"is defined as", as it does for labels.

### repeat

`Repeat(L, m)` builds the line that is L written m times in a row, end to end:

    Repeat(L, 3)  :=  Join(L, Join(L, L))
    Repeat(<x..>, 3)        →  <x..x..x..>

the study of strings writes this as a power, and here `L^3` is shorthand for
`Repeat(L, 3)`.

- **linear**: yes
- **fluid**: yes, and the result stays fluid: the copies come out as the same
  cells whichever way it's read, so nothing depends on a borrowed reading.
  `|x..|^3` is `|x..x..x..|`
- **circular**: no. a circle traced round m times takes three moves, not one
  basic one, so it's written out when a use wants it:
  `Wind(Repeat(Unwind(C), m))`
- **scoped**: no. its ends aren't free; detach it first

this builds a new, longer spacer. `~` is different: it says a spacer repeats in
its surroundings, and leaves the spacer as it is.

### insert

`Insert(H, k, G)` puts a line G into a line H at the joint before H's cell k, k
from 1 to n − 1: H's cells before cell k, then G, then the rest.

    Insert(H, k, G)  :=  Join(Join(Detach(<n: H>[0->k-1]), G), Detach(<n: H>[k->n-1]))
    Insert(<xx..>, 2, <x.>)    →  <xxx...>

at either end, it's simply a join.

### splice

`Splice(C, k, G)` puts a line G into a circle C at the joint before C's cell k,
k from 1 to n, where k = n is the joint between the last cell and cell 0. C
keeps its cell 0.

    Splice(C, n, G)  :=  Wind(Join(Unwind(C), G))
    Splice(C, k, G)  :=  Rotate(Wind(Join(Unwind(Rotate(C, k)), G)), n - k)
    Splice( )xx..(, 2, <x.>)   →  )xxx...(

at the joint after the last cell, it's unwind, join, wind. at any other joint,
the circle is first rotated so that joint comes round to the end, and rotated
back afterwards.

### collapse

`Collapse(B)` lifts a scope until its parent is the root, or a layer it can't
look past. the whole chain of scopes in between collapses, and B ends up as one
scope of the top.

    Collapse(B)  :=  Lift(B), again and again, until its parent is a root or a layer

### flatten

`Flatten(K)` presses a cascade until one spacer is left: its deepest choices,
shown on its root's cells.

    Flatten(K)  :=  Press(K), again and again, until one spacer is left
    Flatten(|xx...x..| >> |x.x|)              →  |x....x..|
    Flatten(|xx...x.x| >> |x.xx| >> |.xx|)    →  |.....x.x|

- the result has the root's resolution and reading
- flattening forgets the layers, the way detach forgets a context: the
  flattened spacer doesn't show that it was chosen in steps (see "layers", in
  "structures")
- the order doesn't matter: any run of neighbouring layers, written out, is a
  cascade too, and flattening the top part first, `Flatten(R >> L1) >> L2`,
  ends in the same spacer as pressing from the bottom. flattening a part is
  partial flattening: `Flatten(R >> L1) >> L2`, or `R >> Flatten(L1 >> L2)`
- there's no way back: many cascades flatten to the same spacer

### stages

    Stages((A, B, C))  :=  (Weights((A)), Weights((A, B)), Weights((A, B, C)))

the running weights of an ordered stack, one row per member as it goes on (see
"weights", in "structures").

### at most and exactly

    AtMost(W, k)   :=  Not(Threshold(W, k + 1))
    Exactly(W, k)  :=  Without(Threshold(W, k), Threshold(W, k + 1))
    Exactly(W, 1)               →  |...x..x.|

### levels and depths

one threshold loses information, but thresholding at every level loses
nothing. `Levels(W)` thresholds W at every amount from 1 up to its largest, and
puts the results in a cascade: the first level is the root, and each next level
chooses, among the previous level's points, those that reach the next amount.
shown flattened, on the root's cells:

    W := |2 2 0 1 0 3 1 0|
    level 1      x x . x . x x .      Threshold(W, 1): the root
    level 2      x x . . . x . .      Threshold(W, 2), chosen among level 1's points
    level 3      . . . . . x . .      Threshold(W, 3), chosen among level 2's points

`Depths(K)` goes back: for each cell, how many levels of the cascade K it's in.
`Depths(Levels(W))` is W again, and `Levels(Depths(K))` is K again, as long as K
doesn't end in an all-null layer.

this isn't a coincidence. a row of whole amounts and a cascade are two ways of
writing the same nested structure: counting how deep each cell goes, or listing
the levels. a map shows the same pairing, between heights and the contour lines
around them. what differs is the meaning: a cascade chooses, layer by layer,
while a row of amounts counts.
