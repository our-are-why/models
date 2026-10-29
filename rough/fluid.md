# fluid

a tangent from identity, caught on 2026-10-28, and still moving. kept rough
until it settles; then parts of it go to types and worlds.

## two questions folded into one

the docs' two kinds of fluid fold two separate questions together:

- **change between the solids**: can a circle and a line change directly into
  each other, by joining or parting the ends?
- **return to fluid**: can a solid strand go back to fluid?

each answer can go either way, so there are four kinds of world:

| | solids don't return to fluid | solids return to fluid |
| --- | --- | --- |
| **no direct circle–line change** | a decision, once made, is final | to switch solids, go back up through fluid, then down again |
| **direct circle–line change** | today's default: commit once, then convert between solids | everything connects |

the kind of fluid should answer only the second question. "any of the three
concrete types can become any other" answers both at once.

since functions never change a strand in place, a unidirectional world doesn't
need a way back: keep the fluid strand, and commit fresh copies whenever a
circle or a line is needed. a way back only earns its place when all you hold
is a committed strand you didn't make.

## movement and standing

two orderings, also folded together:

- **movement**: which way change can go. one way orders the types, a hierarchy
  of what can reach what; both ways orders nothing
- **standing**: whether fluid says less than a solid, a hierarchy of
  specificity, or as much, differently, a sibling

unidirectional movement gives a hierarchy of movement, and pairs naturally with
fluid saying less. bidirectional movement fixes only the movement: the standing
has to be stated separately. so "unidirectional/hierarchical" holds up, and
"bidirectional/sibling" overstates.

## what fluid is: two angles

- **flexible**: a real shape with loose ends. a thread is neither a rigid ring
  nor a rigid rod: it can be tied into a loop or laid out straight. concrete,
  and a sibling of the solids comes naturally
- **deferred**: "let the context decide", like a setting left to follow its
  surroundings. this leans towards abstract, which is the true deferral: free,
  tied to no particular semantics. a hierarchy comes naturally

which angle a world takes is part of what it settles.

## necklace

a necklace: clasped, it's a circle; unclasped, a loose thread; and it can be
clasped and unclasped freely. a world where fluid is a sibling, with no
deferral in it.

it may deserve its own name, split from fluid, since the names carry different
nuance: fluid is adaptable; a necklace is a loop that opens and closes. open
questions:

- is a necklace a kind of fluid, a kind of circle, or a type of its own?
- a clasp sits at one particular joint, so unclasping opens the loop there.
  opening a circle (unwinding, melting) always needs a place to open it, which
  the frame's start currently supplies; a necklace carries that place in
  itself. is the clasp part of the strand, or part of its frame?

## ends that bounce

a line whose ends bounce: stepping past an end lands back on it (_from memory_:
reflecting boundaries, in physics). the cells and neighbours are a line's, but
the rule at the ends differs: one more thing a world could settle, alongside
"the ends stop you".

## an aside: a pattern in the splits

a split that recurs in the model: a parent with two children, one terminal and
one that splits again, and so on down, until the last split ends in two
terminals. the types follow it exactly:

- type: abstract (terminal), and concrete
  - concrete: fluid (terminal at this layer), and solid
    - solid: circular and linear, both terminal

it shows up elsewhere too: unidirectional fluid (terminal) against
bidirectional (split again, by standing); identical (terminal) against the
looser comparisons (split again, by what they set aside).

_from memory_, the exact name is a **pectinate tree**, or **comb**, from
phylogenetics, where it's also called a caterpillar: the rooted binary tree
with exactly one cherry, a pair of sibling leaves. every other split sets one
leaf aside, which makes it the most unbalanced binary tree, drawn like a comb
with its teeth on one side. graph theory's caterpillar is broader: any tree
whose non-leaf vertices lie on one path, with any number of leaves on each,
unrooted. related ideas elsewhere: in logic and philosophy, the tree of
Porphyry, and division by dichotomy (Plato's diairesis); in biology,
dichotomous keys; in computing, right-nested pairs, the shape of a linked list.

## fits and converts

identity's two relations between types have been doing different jobs:

- **fits** is specificity: one type says less, and the other is a particular
  case of it
- **converts** is between peers: two equally definite types, each the other
  with one thing changed, like circle and line, closed or opened

which one holds between fluid and solid depends on fluid's standing. above the
solids, fluid fits them. alongside them, as in the necklace world, the
unclasped thread and the clasped ring are peers, and they convert.

identity commits to the first (2026-10-28): the types run from general to
specific, abstract, then fluid, then circular and linear, side by side. that's
the caterpillar tree read as a chain of generality: each leaf set aside is one
level, and the cherry is the pair of peers at the bottom. with fluid as a
sibling, the bottom would be three peers, and the tree would stop being a
caterpillar: the tree's shape is itself a statement about standing.

two gaps this closed, or left:

- abstract wasn't covered by fits or converts at all; as the most general type,
  it fits every concrete one
- unidirectional and bidirectional fluid with the same arrangement are neither
  more general one than the other, nor circle and line. identity now defines
  "the same up to type" directly, as the same arrangement whatever the type, so
  the three named relations are cases of it, not the whole of it

the sibling case still lacks a concrete example that convinces: the necklace is
the best candidate so far.

## to decide later

- define fluid's two kinds by return to fluid only, and state standing
  separately
- worlds rows: change between circular and linear; return to fluid; fluid's
  standing, and which angle it takes
- whether necklace gets its own name, or its own type
- whether the slash pairs "unidirectional/hierarchical" and
  "bidirectional/sibling" survive
