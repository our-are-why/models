# identity

**in short.** what about a strand is essence and what is convention, and when
two strands count as the same. the default is strict (the same resolution, type
and cells), and the comparisons `=`, `~=`, `<->`, `==` and `===` loosen it in
stated ways.

the concepts here are listed, with stable IDs, in [concepts.md](../concepts.md).

## essence and convention

**builds on:** strand, in "basics".

some things about a strand belong to the strand itself; others are choices we
make to write it down or talk about it. to tell them apart, imagine two people
drawing the same strand differently: starting at a different cell, counting
the other way round, using other symbols. what they still agree on is
essence/semantics; what they don't is convention. (the general idea, beyond
strands, is in [the approach](../meta/approach.md).)

- **essence**: the resolution, the density and the sparsity; the distances
  between cells; in a line, what sits at the ends. these are found in
  the strand, not made up
- **convention**: which cell is cell 0, counting from 0, which way the
  numbering runs, the symbols for the two states, and so the written form
  itself. these are chosen, so that everyone starts from the same place

a line has two ends, so the ends are essence, but which end comes first is
convention. a circle has no start: on its own, its cell 0 is convention. set
against other strands, cell 0 is where it lines up with them, so where it
starts is part of how they relate.

some things sit in between. how the states are written is convention (■ or
`x` here, 1 elsewhere), and so is which one is called true. whether one state
is the thing and the other its absence isn't a convention but a perspective:
the asymmetric perspective sees a thing and its absence, and the symmetric one
sees two equals (see "two states", in "basics").

## identity

**builds on:** state, type, resolution, in "basics"; Commit, Rotate, Reverse,
Mirror, Unwind, Wind, in "functions".

these chapters give identity a **default**: a starting point that any use can
override, tightening or loosening it to fit what it's doing.

**by default, two strands are the same strand when they have:**

- the same resolution
- the same type: both circular, both linear, both abstract, or both the same
  kind of fluid
- the same state in every numbered cell

different encodings never make different strands: typed or display symbols,
cells or points, or any other symbols that follow the rules. what the encoding
says does matter: the resolution, the type and the cells. where a strand
came from isn't part of the default, but a use can add it.

so by default, `|8: 0,1,5|` is the same strand as `|xx...x..|`. but `)x.x..(`
and `)x..x.(` are different (one is the other rotated), and so are `/x../` and
`<x..>` (one is fluid, the other committed to linear).

a scoped piece and a whole linear strand with the same cells, like `[x..]` and
`<x..>`, aren't the same strand by default: one is a piece of something larger,
the other is the whole thing. they are alike, though: the same cells, behaving
the same way within their ends, so a use that only cares about the cells can
set the context aside and treat them as the same, written `[x..] === <x..>`
(see below). likewise, two cascades that flatten to the same strand are alike,
giving the same cells, but whether they're the same cascade, layer by layer, is
a higher-level question, left to the uses that need it.

comparing cell by cell includes cell 0 and the direction. for a strand on its
own, those are conventions; for strands set against each other, they're how
the strands relate: rotations of the same strand score differently in a stack
(see "weights", in "structures"). that's why the default compares them, and a
use that only cares about a strand on its own can loosen it to "up to start".

a fluid strand **fits** a circular or linear strand with the same resolution
and cells: it could become it, just by committing to a type. fitting isn't
identity, and by default it runs one way only, from fluid to committed: `/x../`
fits both `)x..(` and `<x..>`, but those two are still different strands.
between them, unwind and wind convert either way, losing nothing. with
bidirectional fluid, where melting is allowed, fitting runs both ways too. the
comparisons themselves don't depend on the world: they say how two strands
relate, not which moves a world allows.

that gives five ways of comparing:

| comparison                 | means                                                     | typed | display |
| -------------------------- | --------------------------------------------------------- | ----- | ------- |
| **identical**              | the same resolution, type and cells (the default)         | `=`   | `=`     |
| **fits**                   | a commitment away: one fluid, the other committed         | `~=`  | `≃`     |
| **converts**               | a conversion away: one circle, one line, the same cells   | `<->` | `⇄`     |
| **the same up to type**    | any of the three above                                    | `==`  | `≈`     |
| **matches**                | the same number of cells and the same value in every numbered cell, whatever the type, context or origin | `===` | `≍` |

    /x../ ~= )x..(        fits
    )x..( <-> <x..>       converts
    /x../ == <x..>        the same up to type: here, because it fits
    )x..( == <x..>        the same up to type: here, because it converts
    [x..] === <x..>       matches: a piece and a whole line, with the same cells
    [x..] === )x..(       matches: a piece and a whole circle; only the cells count

the more `=` signs, the more is set aside: `=` sets aside nothing, `==` the
type, and `===` the type and the context. (this runs opposite to javascript,
where `===` is the strictest.)

setting the type aside is also what makes a strand abstract (see "abstract
and fluid", in "basics"): strands that are the same up to type are the same
abstract strand.

`==` is whichever of `=`, `~=` and `<->` applies. `=`, `==` and `===` chain: if
A is the same as B, and B as C, then A is the same as C. `~=` and `<->` don't:
two fittings from the same fluid strand give a conversion, and two conversions
come back to the same type, which is identity. `<->` needs spaces around it,
so it's never read as edges.

`===` compares values, so it works for rows of weights too, where the values
are amounts rather than states. the numbering still counts: `)x..( === ).x.(`
is false, since setting the start aside is a separate loosening.

**overriding the default.** the default asks whether the entire thing is the
same. being alike, matching in some respects and behaving similarly, is a
looser question, and the overrides below are ways of asking it. a use can
loosen the default by setting something aside, or tighten it by adding
something. the usual loosenings have exact forms through the functions:

- **up to start**: for circles, the same when one is a rotation of the other
- **up to direction**: the same when one is a reversal of the other (lines),
  or a mirror of the other (circles)
- **up to type**: `==`, the same cells whatever the type

tightening adds what the default leaves out, like where a strand came from, or
its frame in a stack. a use that overrides the default should say what it
compares and what it sets aside.