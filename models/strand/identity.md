# identity

## comparisons

two strands can be compared in more than one way. the most literal is
**identical**: it takes the strands exactly as they are, setting nothing aside
and adding nothing. two strands are identical when they have

- the same resolution
- the same type
- the same state in every pair of cells their frames line up
- the same surroundings: what lies beyond their ends, if anything, is the same

how a strand is written doesn't matter, only what the writing says about these.

two comparisons are looser than identical:

- **the same up to type**: identical, once the type is set aside: as abstract
  strands, they're identical
- **matches**: identical, once the type and the surroundings are set aside:
  their states agree cell by cell

two strands that are the same up to type differ, at most, in their types, and
the types run from general to specific: abstract, then fluid, then circular
and linear, side by side. so their types relate in exactly one of three ways:

- **the same type**: they're identical
- **one more general than the other**: the more general one **fits** the
  other. an abstract strand fits every concrete one, and a fluid strand fits
  the circle and the line
- **circular and linear**: they **convert**, each being the other closed or
  opened

fits and converts never relate a strand to itself: fitting needs a type that's
more general, converting a type that's different. fits runs one way, from
general to specific; converts works both ways.

these comparisons say how two strands relate, not which changes a world allows:
whether a solid strand can return to fluid, or a circle become a line directly,
doesn't change them.

**example.** two circles can have the same pattern round the loop and still
not be identical:

    ● ○ ● ○ ○
    ● ○ ○ ● ○

lined up cell by cell, their states differ. the other way round, two strands
whose states agree cell by cell can still differ in type: a fluid strand and a
line are the same up to type, and the fluid one fits the line; a circle and a
line convert. a scoped piece and a whole line with the same arrangement aren't
identical either: one is a piece of something larger, the other is the whole
thing. setting their surroundings aside, they match.

## equivalences

two strands are **alike** when they're the same in some respects. a comparison
says which respects, and the comparisons that behave like "the same" are
**equivalences** (equivalence relations, in mathematics): everything is the
same as itself, it works both ways, and it chains. identical, the same up to
type and matches are equivalences; fits runs one way, and converts doesn't
chain, so they aren't.

an equivalence can set aside something identical compares, or add something
it leaves out. the same **up to** something means the same once that
something is allowed to differ. some equivalences lie inside others, and some
lie side by side.

### how many count as the same

take one circle, with 6 cells, three in each state. drawn as a ring, with its
cell numbers beside it:

       0                ●
    5     1          ○     ●
    4     2          ○     ○
       3                ●

written from cell 0, the way the numbers run, it's `● ● ○ ● ○ ○`.

**up to start**: the same way round, from any start. starting from each of the
six cells gives six circles. lined up cell by cell they differ, but each is the
same ring, started somewhere else:

    cells 0 1 2 3 4 5     ● ● ○ ● ○ ○
    cells 1 2 3 4 5 0     ● ○ ● ○ ○ ●
    cells 2 3 4 5 0 1     ○ ● ○ ○ ● ●
    cells 3 4 5 0 1 2     ● ○ ○ ● ● ○
    cells 4 5 0 1 2 3     ○ ○ ● ● ○ ●
    cells 5 0 1 2 3 4     ○ ● ● ○ ● ○

**up to direction**: from the same start, either way round. there are two ways
round, so two circles. the second keeps the first cell and reverses the rest;
writing the first one backwards, `○ ○ ● ○ ● ●`, would change the start too:

    cells 0 1 2 3 4 5     ● ● ○ ● ○ ○
    cells 0 5 4 3 2 1     ● ○ ○ ● ○ ●

**up to frame**: any start, either way round: 6 starts and 2 ways round give
12 circles. **up to a reshuffle**: only the counts are kept, three cells in
each state, anywhere: 20 circles.

the strands that count as the same as a strand under one equivalence are its
**class** under it (equivalence class, in mathematics). the size of the class
of `● ● ○ ● ○ ○` depends on the equivalence:

    identical             1
    up to start           6
    up to direction       2
    up to frame          12
    up to a reshuffle    20

### nesting and branching

compared by what they set aside, two different equivalences either nest or
branch.

they **nest** when one sets aside everything the other does, and more: it's
the **looser** one, the other the **tighter**. strands the same under the
tighter one are the same under the looser one too: up to start nests in up to
frame, and the class of `● ● ○ ● ○ ○` up to start, its 6, lies inside its
class up to frame, its 12.

they **branch** when each sets aside something the other keeps. up to start
keeps the way round, up to direction keeps the start, and the classes of
`● ● ○ ● ○ ○` under the two each hold a circle the other doesn't:

    cells 0 1 2 3 4 5     ● ● ○ ● ○ ○     in both
    cells 1 2 3 4 5 0     ● ○ ● ○ ○ ●     up to start only
    cells 0 5 4 3 2 1     ● ○ ○ ● ○ ●     up to direction only

branches rejoin both ways. setting aside everything either one sets aside
gives an equivalence both nest in: up to start and up to direction rejoin in up
to frame, and up to type and up to surroundings in matching. being the same
under both at once gives one that nests in both: for `● ● ○ ● ○ ○`, only the
strand itself.

#### by classes

classes don't overlap: under each equivalence, every strand is in exactly one
class.

nesting and branching are two cases of one mechanism, **splitting**: a class
of one equivalence splits under another when its strands fall into more than
one of the other's classes. between two equivalences, it runs one of two ways,
or not at all:

- **vertical**, one way only: only one has classes that split under the
  other, and that one is the looser. this is nesting
- **horizontal**, both ways: each has classes that split under the other.
  this is branching
- **neither** way: they're the same equivalence

branches rejoin by merging classes that overlap, until none do, and by keeping
only the overlaps. seen this way, nesting and branching hold for any
equivalence, not only for those built by setting things aside.

**example.** for the 20 circles with three cells in each state, up to start
gives classes of 6, 6, 6 and 2, and up to frame classes of 12, 6 and 2. the
two split vertically: the class of `● ● ○ ● ○ ○` up to frame splits into two
classes of 6 up to start, and no class up to start splits up to frame. up to
start and up to direction split horizontally: under up to direction, the class
of `● ● ○ ● ○ ○` up to start splits into six single circles, and under up to
start, its class up to direction splits into two.

### identical, in the middle

identical compares what the strand itself carries: its resolution, type,
arrangement and surroundings, placed in the frame as written. looser
equivalences compare less than that. tighter ones add what lives outside the
strand, in its world, like its origin or its meaning.

that's why identical is the default: any looser equivalence can be reached
from it by setting something aside, but what a looser one sets aside can't be
brought back.

a strand with symmetries of its own shows where tightening matters. move every
state two cells round, keeping the frame where it is: the state in cell 0 goes
to cell 2, the one in cell 1 to cell 3, and so on round. most strands show the
move: `● ● ○ ● ○ ○` becomes `○ ○ ● ● ○ ●`. but `● ○ ● ○ ● ○` becomes
`● ○ ● ○ ● ○`: cell by cell, before and after agree, so they're identical.
what differs is where each state came from, and that isn't in the cells:
identical can't see it, and a tighter equivalence, one that adds where the
arrangement came from, can. the same arrangement, but not the same thing.

### what can be set aside, and what added

for a looser equivalence, any of these can be set aside:

- **the frame**: the start, the direction, or both, giving up to start, up to
  direction and up to frame
- **the type**: up to type, the same arrangement whatever the type
- **the surroundings**: up to surroundings, a piece and a whole line with the
  same arrangement are the same
- **where the states are**: up to a reshuffle, the same counts, in any cells

for a tighter one, what's added lives outside the strand, in its world:

- **origin**: where the arrangement came from, as with the move above
- **meaning**: what the cells are taken to say

### choosing an equivalence

no equivalence is the true one: each answers a different question, and a use
picks the one its question needs. which one counts as "the same" is one of the
choices a world makes: identical, by default.

whichever is used should be named: what it sets aside, or what it adds,
compared with identical.
