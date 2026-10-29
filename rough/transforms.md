# transforms

a tangent from types and identity, caught on 2026-10-29. kept rough until
types and identity are settled; then it may become a chapter, after basics and
types, as the idea that functions later carries out.

## the idea

sort transforms by which part of a strand they change. each kind changes one
part and keeps the rest, so the kinds are independent of each other:

| what changes | examples | what stays |
| --- | --- | --- |
| **type** | fluid coming to a solid, returning to fluid, opening or closing between circle and line | the arrangement |
| **arrangement** | moving every state round, reversing, changing one cell, reshuffling | the type |
| **value** | renaming the states, swapping them, changing the kind of value (states into amounts) | the cells |
| **space**, maybe | joining strands, taking a piece, growing, refining | depends |

type, arrangement and value are the user's three. space is a possible fourth,
for transforms that change the resolution or the neighbours, which fit none of
the three; still to check.

types' "change" part (2026-10-29) is the first piece: the type transforms, and
which of them a world allows.

## transform and reframe

a transform changes the strand; a reframe changes only how it's read. moving
every state two cells round, keeping the frame where it is, is a transform:
`● ● ○ ● ○ ○` becomes `○ ○ ● ● ○ ●`. starting from cell 2 instead is a
reframe: the strand stays as it is, and only the frame moves.

the two can give the same written rows, which is how they get confused: in
identity, a symmetric example labelled with `cells 2 3 4 5 0 1` read as a
reframe when it was meant as a transform. a transforms chapter is where the
difference would be explicit.

## the link to identity

an equivalence is "the same up to a kind of transform":

- up to start: moving every state round
- up to direction: reversing the way round
- up to type: changing the type
- up to a reshuffle: any rearrangement that keeps the counts

identity says what's set aside; transforms say what can change, about the
same parts. _from memory_: in mathematics, classes made this way are the
**orbits** of a group of transforms.

up to start can be reached either way, by reframing or by transforming, and
gives the same classes. whether every equivalence comes from a kind of
transform is open.

## perspective decides the kind

swapping the two states is a value transform, renaming, under the symmetric
perspective: basics says swapping them "changes nothing but the names". under
the asymmetric perspective, it changes every cell's role. the same move, a
different kind of transform depending on the perspective.

## open

- whether space is a fourth kind, or splits across the others
- value transforms that leave strands behind: states into amounts gives rows of
  amounts, which aren't strands
- whether a reframe is a transform of the view, and belongs here at all
- how transforms of different kinds compose, and whether order matters
- whether every equivalence comes from a kind of transform
