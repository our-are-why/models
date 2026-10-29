# comparisons

a tangent from identity, caught on 2026-10-29. kept rough until other chapters
earn it; then it may become a chapter of its own, which identity builds on.

## the idea

identity is the way in: everyone already has an intuition for "the same". a
later chapter can step out from there: sameness is one kind of comparison
among eight.

identity defines what it needs on its own: comparison, the three questions,
equivalence and resemblance. a comparisons chapter would build on those terms
and add the other kinds, so definitions run the same way as reading, and
nothing loops.

## three questions

ask any comparison three questions, each answered yes or no:

- **itself**: is every strand related to itself?
- **both ways**: whenever A is related to B, is B related to A?
- **chains**: whenever A is related to B and B to C, is A related to C?

together, the three yes answers are what make a comparison sort strands into
groups, its classes, with no strand left out and none in two:

| question | its job in the sorting | without it |
| --- | --- | --- |
| itself | every strand gets a group | a strand could be left out |
| both ways | a group is the same whoever you start from | a strand's group would depend on who's asking |
| chains | groups don't overlap | a strand could sit in two groups at once |

## eight kinds

the answers place every comparison in exactly one of eight kinds, so sorting
comparisons this way is itself a sorting, with nothing ambiguous.

each kind has a plain example from basics, using only counts and which cells
differ. checked by computation: all eight on the 16 strands of 4 cells.

| itself | both ways | chains | example | the docs' comparisons | established name (_from memory_) |
| --- | --- | --- | --- | --- | --- |
| yes | yes | yes | the same counts | identical, up to start, matches | equivalence relation |
| yes | yes | no | differ in at most one cell | resemblance | tolerance relation |
| yes | no | yes | no more true cells than | fits, if it included itself | preorder |
| yes | no | no | the same, or one null cell turned true | | no common name |
| no | yes | yes | both have two cells in each state | a group picked out by a condition | partial equivalence relation |
| no | yes | no | differ in exactly one cell | converts | symmetric, irreflexive |
| no | no | yes | fewer true cells than | fits | strict partial order |
| no | no | no | exactly one more true cell than | | no common name |

notes:

- **resemblance** is equivalence's nearest neighbour, one answer away: it
  doesn't chain. under "differ in at most one cell", `● ● ○ ○` and `● ○ ○ ○`
  are alike, and so are `● ○ ○ ○` and `○ ○ ○ ○`, but `● ● ○ ○` and `○ ○ ○ ○`
  aren't. the middle strand would sit in two groups
- **a group picked out by a condition** sorts the strands inside it and says
  nothing about the rest: works both ways and chains, but leaves strands out.
  adding "everything else" as a second group makes it a sorting
- **fits** is strict today: no strand fits itself. defined as "at least as
  general", it would move up a row, to the preorders. open question
- names: "order", "rank" and "hierarchy" are taken in the docs (cell order and
  ordered stacks, the spacer labels, hierarchical fluid). the kinds without a
  plain name may be best described by their three answers

## two sides: likeness and contrast

every comparison divides all pairs of strands into related and not related.
**likeness** reads the related side; **contrast** reads the other, its
negative space. so likeness and contrast aren't two kinds of comparison, but
two readings of one: the same division, from either side.

"itself" really has three answers: always, never, or only for some strands,
the partial kind. the eight kinds above lump the last two together as no.

reading the other side does three different things to the three questions.
checked by computation, on all eight examples above, on the 16 strands of 4
cells:

- **itself flips**: always becomes never, and never always. a likeness's other
  side is a contrast, and a contrast's other side is a likeness. the partial
  kind stays partial
- **both ways never changes**: it belongs to the division, not to a side
- **chains can change**: it belongs to the side being read

| comparison | itself | both ways | chains | its other side | itself | both ways | chains |
| --- | --- | --- | --- | --- | --- | --- | --- |
| the same counts | always | yes | yes | different counts | never | yes | no |
| differ in at most one cell | always | yes | no | differ in two cells or more | never | yes | no |
| no more true cells than | always | no | yes | more true cells than | never | no | yes |

so "itself" isn't a property of what's compared, the way the other two are: it
says which side of the division is being read. an equivalence's contrast side
is "in different classes": the contrast is already inside the likeness.

### side and direction

flipping sides never changes both ways, so both ways or one way belongs to the
division itself. that makes it the clean partner for likeness and contrast,
and every square is filled, so the two are independent:

| | mutual (both ways) | one-way |
| --- | --- | --- |
| **likeness** | the same counts; differ in at most one cell | no more true cells than |
| **contrast** | different counts; differ in exactly one cell; converts | fewer true cells than; fits |

chaining isn't an axis of the same sort: it belongs to the side being read.
within mutual likeness, it's what makes an equivalence rather than a
resemblance.

names: "mutual" isn't used anywhere in the docs; "one-way" already describes
commitment (fluid to solid), in the same everyday sense.

### the asymmetry of sameness

sameness chains, but difference doesn't. "the same counts" chains; "different
counts" doesn't: two strands can each differ from a third and still have the
same counts as each other. that's why strands can be sorted by what's the
same, but not by what's different: the classes come from the likeness side,
even though the contrast side describes the same division.

the reason is short. take a comparison that works both ways and chains: if A
is related to B, then B is related to A, and chaining the two gives A related
to A. so it relates every strand it touches to itself: it's a likeness, at
least on those strands. a mutual contrast can therefore never chain, and
difference can't sort.

it also means the three questions aren't fully independent: never itself,
both ways and chains together happen only for the comparison that relates
nothing at all.

worth communicating somewhere, at some point; the docs don't say it yet.

## what may earn it

- **measures**: comparing counts, such as "fewer true cells than", an order
- **dynamics**: growth, where a strand extends an earlier one, also an order
- **resemblance**: "how many cells differ" is a measure, and a natural way to
  grade closeness
- **types**: fits and converts relate types, not sameness, and may belong
  there, or here, rather than in identity

when one of these needs a kind beyond equivalence, the chapter has its reason.
if another domain ever needs the eight kinds too, they get one home, with
strands as one framing.
