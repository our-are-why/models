# concepts

every concept these docs define, with a stable ID. IDs are numbered in the order
they were first assigned, and never reused or renumbered: a renamed concept keeps
its ID, and a retired one leaves a gap. **was** gives former names, and **builds on**
lists the concepts its definition uses. the words here are short reminders; each
chapter has the full definition.

## meta: approach

from [`1_approach_meta.md`](1_approach_meta.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C001 | default |  | the choice the docs make where one has to be made, stated so that it can be overridden |  |
| C002 | world |  | a semantic world: the setting something is used in, with its own semantics; it settles what the defaults leave open | C001 |
| C003 | perspective |  | one of several valid ways of seeing the same thing, none the hidden truth behind the others |  |

## meta: semiotics

from [`2_semiotics_meta.md`](2_semiotics_meta.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C127 | syntax |  | how signs relate to each other: what counts as well written, apart from meaning |  |
| C128 | semantics |  | how signs relate to what they stand for: what a well-written thing means | C127 |
| C129 | pragmatics |  | how meaning depends on who uses the signs, and where; worlds sit here | C128, C002 |

## meta: documents

from [`3_documents_meta.md`](3_documents_meta.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C130 | domain |  | one subject the docs cover, such as spacers, or the meta domain itself |  |
| C131 | stripe |  | a domain's chapters: numbered in reading order, sharing a suffix, like `_spacer` | C130 |
| C132 | concept ID |  | C and a number, given in order, never reused or renumbered |  |
| C133 | frozen version |  | a whole draft kept exactly as it was, as a record; never edited, and not part of the docs | C130 |

## spacer: basics

from [`1_basics_spacer.md`](1_basics_spacer.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C004 | spacer |  | a one-dimensional, discrete space of cells, each in one of two states |  |
| C005 | cell | slot | one piece of a spacer's space, with a position and a state | C004 |
| C006 | state |  | what a cell holds: true or null | C005 |
| C007 | reading | view | how a spacer is read: which cells are neighbours, and what a position means | C004 |
| C008 | circular |  | a reading where the last cell is next to the first, so there are no ends | C007 |
| C009 | linear |  | a reading where the first and last cells are ends | C007 |
| C010 | fluid | neutral | a spacer with everything the two shapes share, its cells in order, but no shape | C007 |
| C011 | commitment |  | once a spacer is read circular or linear, that's part of what it is, and doesn't change on its own | C008, C009, C010 |
| C012 | abstract fluid |  | fluid as a placeholder for a shape not yet chosen | C010, C002 |
| C013 | concrete fluid |  | fluid as a form in its own right, adaptable, like a liquid taking its container's shape | C010, C002 |
| C014 | hierarchical fluid |  | concrete fluid above circles and lines: they come from it, and only that way | C013, C011 |
| C015 | sibling fluid |  | concrete fluid as a third form beside circles and lines: any of the three can become any other | C013 |
| C016 | true | filled | the state of a cell that holds something | C006 |
| C017 | null | empty | the state of a cell that holds nothing: the absence of true, not unknown | C006 |
| C018 | asymmetric perspective |  | true/null: one state is a thing, the other its absence. the measures take this one | C016, C017, C003 |
| C019 | symmetric perspective |  | true/false: neither state is special, and each is the other's negation. logic's perspective | C016, C017, C003 |
| C020 | resolution |  | how many cells a spacer has | C005 |
| C021 | density |  | how many cells are true | C005, C016 |
| C022 | sparsity |  | how many cells are null | C005, C017 |
| C023 | points |  | the positions of a spacer's true cells; density is how many there are | C016, C021 |
| C024 | negative |  | the spacer with every cell's state swapped | C006 |
| C025 | arrangement/distribution |  | which cells are true and which null; any arrangement is a spacer | C016, C017 |
| C026 | origin |  | where an arrangement came from. the cells don't record it; it lives outside the spacer | C025 |
| C027 | all null, all true | all empty, all filled | every cell in the same state; each is the other's negative | C024 |
| C028 | zero |  | no cells at all: no space, so not a spacer | C004 |

## spacer: notation

from [`2_notation_spacer.md`](2_notation_spacer.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C029 | typed form |  | `x` for true and `.` for null, from cell 0, with edges. easy to enter by hand | C016, C017 |
| C030 | display form |  | shapes, with a space between cells, that carry the reading: ● ⚬, ▲ ▽, ■ ◇ | C029, C007 |
| C031 | symbol rules |  | the five rules any symbols follow: distinct states, separate cells, countable runs, minimize collisions, clear edges | C029 |
| C032 | edges |  | the brackets that show a written spacer's reading: `)…(` circular, `<…>` linear, `[…]` scoped, `\|…\|` fluid, and `\|><\|` for zero | C029, C007, C028 |
| C033 | point form |  | a spacer written by its resolution and points: `\|8: 0,1,5\|` | C020, C023 |
| C034 | label |  | a name for a spacer, `S := …`, defined once; each example's labels are its own | C004 |
| C035 | description |  | what's known about a spacer, in braces with keys: `{r: 12, d: 7}`. it picks out every spacer that fits | C020, C021 |
| C036 | repetition |  | `~` after the edges: the spacer repeats in its surroundings, and stays as it is | C032 |
| C037 | escaping |  | inside another format, the notation is escaped the way that format asks, never changed to suit it | C029 |

## spacer: measures

from [`3_measures_spacer.md`](3_measures_spacer.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C038 | step |  | a move from a cell to a neighbouring cell | C005 |
| C039 | direction |  | + goes towards higher cell numbers, − towards lower; + when no sign is written | C038 |
| C040 | bounded |  | a linear spacer with nothing beyond its ends | C009 |
| C041 | scoped |  | a linear spacer that's a piece of something larger: there's more beyond its ends, as context | C009 |
| C042 | distance |  | how many steps from one cell to another, never negative. round a circle there are two; the + one by default | C038, C039 |
| C043 | interval |  | the distance from one point to the next, going + | C042, C023 |
| C044 | gap |  | how many null cells lie between one point and the next. an interval is one more than its gap | C017, C023 |
| C045 | end gap |  | the null cells before a line's first point, or after its last | C044, C009 |
| C046 | joint |  | a place where two neighbouring cells meet | C005 |
| C047 | seam |  | a joint where the two cells are in different states | C046, C006 |
| C048 | band |  | a stretch of cells in the same state, as long as it goes; seams cut a spacer into bands (panel would work too) | C047 |
| C049 | run |  | a band of two or more cells | C048 |
| C050 | whole numbers |  | everything counted or measured in a spacer is a whole number; proportions come in with generators | C004 |

## spacer: structures

from [`4_structures_spacer.md`](4_structures_spacer.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C051 | scope |  | taking a piece of a spacer, after the spacer in square brackets: `)6: S([5+3]`, `<6: S>[2->5]` | C038, C032, C034 |
| C052 | scoped piece |  | what a scope gives: `[…]`, with its own numbering from where the scope started | C051, C041 |
| C053 | lap |  | `~3%` in a circular scope: three full turns, without stating the resolution | C051, C008 |
| C054 | parent |  | what a piece was taken from: a spacer, a piece, or a layer. a piece can't reach past it | C052 |
| C055 | chain |  | scopes one after another, each counting in the piece the one before made | C051, C054 |
| C056 | root |  | the spacer at the very top, which isn't a piece or a layer of anything | C054 |
| C057 | layer |  | a spacer whose cells are the points of the spacer above it: it chooses among them | C023 |
| C058 | cascade |  | layers one under another, written `R >> L` or `L << R` | C057, C056 |
| C059 | fitting rule |  | a layer's resolution is the density of the layer above it | C057, C021 |
| C060 | collection |  | several spacers taken together; order and repeats are its two facets | C004 |
| C061 | set |  | a collection with no order and no repeats: `{A, B, C}` | C060 |
| C062 | multiset |  | a collection with no order, repeats allowed: `{#A, A, B#}`, or `⟅A, A, B⟆` in display | C060 |
| C063 | sequence |  | a collection in order, repeats allowed: `(A, A, B)` | C060 |
| C064 | ordered set |  | a collection in order, with no repeats | C060 |
| C065 | stack |  | a collection lined up cell by cell, sharing one reading: `)(A, B)(`, `<(A, B)>`, `\|(A, B)\|` | C060, C007 |
| C066 | frame |  | the fixed choices for how a member lines up in a stack: its cell 0, its direction, its reading | C065 |
| C067 | cell weights |  | how many members are true in each column of a stack | C065, C016 |
| C068 | row of amounts |  | numbers on a stack's cells, with its reading: `\|2 2 0 1 0 3 1 0\|`. not a spacer | C067 |
| C069 | spacer weight |  | a member's cell weights added up at its points (or score): how much it agrees with the whole | C067, C023 |
| C070 | stages | build-up | an ordered stack's running weights, one row per member as it goes on | C067, C063 |
| C071 | weak emergence |  | weights can show structure of the whole that no member shows on its own | C067 |

## spacer: functions

from [`5_functions_spacer.md`](5_functions_spacer.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C072 | function | operation | takes spacers, or things made from them, and gives one back | C004 |
| C073 | operation |  | in the maths sense: a function that takes members of one set and gives a member of the same set | C072 |
| C074 | primitive |  | a function that does one basic thing, whether or not others could build it | C072 |
| C075 | named composite |  | a function defined by the primitives it's made of | C074 |
| C076 | view |  | a window onto a spacer: a view function changes what's looked at, not the spacer | C051 |
| C077 | borrowing a reading |  | a function can use a reading while it works if only one makes sense; fluid in gives fluid out | C010, C072 |
| C078 | tailoring |  | each function does one kind of thing to one kind of spacer; lines and circles get their own | C072, C008, C009 |
| C079 | Not | `not A` | true wherever A isn't: the negative | C024, C074 |
| C080 | And | `A and B` | true where all of its spacers are (intersection) | C074, C019 |
| C081 | Or | `A or B` | true where at least one is (union) | C074, C019 |
| C082 | Xor | `A xor B` | true where an odd number are; for two, where exactly one is (symmetric difference) | C074, C019 |
| C083 | Without | but not | true where A is and B isn't (difference) | C074, C019 |
| C084 | Commit |  | gives a fluid spacer a reading, by putting edges round it: a cast | C010, C032, C011 |
| C085 | Melt |  | in some worlds: forgets a committed spacer's shape, giving the fluid spacer with the same cells | C084, C015, C002 |
| C086 | Rotate |  | starts a circle from its cell k: a rotation/phase | C008 |
| C087 | Slide |  | moves a scoped piece along its parent; the window keeps its length | C052, C054, C076 |
| C088 | Reverse |  | runs a line's numbering the other way: its ends swap | C009 |
| C089 | Mirror |  | mirrors a circle, pivoting on cell 0: cell j goes to cell −j | C008 |
| C090 | Join |  | puts one line after another, end to end | C009 |
| C091 | Unwind |  | opens a circle into a line, from its cell 0 | C008, C009, C011 |
| C092 | Wind | Close | joins a line's two ends into a circle | C008, C009, C011 |
| C093 | Detach |  | takes a scoped piece out of its context, as a line of its own | C052 |
| C094 | Lift |  | gives a scoped piece as a scope of its parent's parent | C055, C054, C076 |
| C095 | Press |  | presses a cascade's deepest layer onto the layer above | C058 |
| C096 | Weights |  | a stack's cell weights, as a row of amounts | C067, C068 |
| C097 | Threshold |  | a row of amounts back into a spacer: true where the amount is at least k | C068 |
| C098 | Repeat |  | a line written m times, end to end; `L^3` is shorthand | C090 |
| C099 | Insert |  | puts a line into a line, at a joint | C090, C093, C046 |
| C100 | Splice |  | puts a line into a circle, at a joint; the circle keeps its cell 0 | C091, C090, C092, C086, C046 |
| C101 | Collapse |  | lifts a piece until its parent is the root or a layer | C094, C056 |
| C102 | Flatten |  | presses a cascade until one spacer is left, on the root's cells | C095, C056 |
| C103 | Stages | BuildUp | the stages of an ordered stack, as a sequence of rows | C096, C070 |
| C104 | AtMost |  | true where the amount is at most k | C079, C097 |
| C105 | Exactly |  | true where the amount is exactly k | C083, C097 |
| C106 | Levels |  | a row of amounts thresholded at every amount, as a cascade | C097, C058 |
| C107 | Depths |  | for each cell, how many levels of a cascade it's in; undoes levels | C058, C068 |

## spacer: dynamics

from [`6_dynamics_spacer.md`](6_dynamics_spacer.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C108 | generator |  | a precise rule or process that makes a spacer at each resolution it covers | C004, C020 |
| C109 | resolution dynamics |  | how a generator's spacers change as the resolution grows | C108 |
| C110 | infinity |  | following a generator without end; never reached, and not a spacer | C108, C028 |
| C111 | signature |  | a generator's or function's keys in order, so values can go without keys: `Block(r, d)` | C108, C035 |
| C112 | growth/extension |  | facet: earlier cells never change, and new ones are added | C108 |
| C113 | refinement/subdivision |  | facet: each spacer describes the same whole at a finer grain | C108 |
| C114 | rule/chance |  | facet: whether a rule fixes every cell, chance decides, or both | C108 |
| C115 | transparent/opaque |  | facet: whether the rule can be read off and carried forward | C108 |
| C116 | patterned/random-like |  | facet: whether the result shows a pattern, or passes for chance | C108 |
| C117 | natural/designed |  | facet: whether it was found (natural/found) or built (made/designed) | C108 |

## spacer: identity

from [`7_identity_spacer.md`](7_identity_spacer.md)

| id | concept | was | in plain words | builds on |
| --- | --- | --- | --- | --- |
| C118 | essence |  | essence/semantics: what two people drawing the same spacer differently still agree on | C004 |
| C119 | convention |  | choices made to write a spacer down or talk about it, such as which cell is cell 0 | C118 |
| C120 | identical |  | `=`, the default: the same resolution, reading and cells | C020, C007, C006 |
| C121 | fits |  | `~=`: a commitment away; one fluid, the other committed, the same cells | C120, C084 |
| C122 | converts |  | `<->`: a conversion away; one circle, one line, the same cells | C120, C091, C092 |
| C123 | same up to reading |  | `==`: identical, fits or converts | C120, C121, C122 |
| C124 | matches |  | `===`: the same number of cells and the same value in each, whatever the reading, context or origin | C120 |
| C125 | alike |  | the same in some respects; overriding the default is a way of asking it | C120 |
| C126 | override |  | loosening or tightening the default: up to start, up to direction, up to reading | C120, C086, C088, C089 |
