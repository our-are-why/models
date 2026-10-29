# notation

**in short.** how strands are written: a keyboard form (`x` and `.`) and a
display form for reading (shapes), the five rules any symbols follow, edges
that show the type, the point form, labels, descriptions and repetition, why a
strand isn't called a binary string, and the names the two states can take.

the concepts here are listed, with stable IDs, in [concepts.md](../concepts.md).

## writing a strand down

a strand is written in one of two forms, which map one to one:

- **keyboard**: `x` for true and `.` for null, with no spaces, in
  order from cell 0. easy to enter by hand
- **display/read-only**: shapes, with a space between cells. purer to read

anyone, or any program, can write either; the keyboard form is simply easier to
type.

### rules for the symbols

other symbols work just as well, as long as they follow five rules:

1. **distinct states**: true and null look different
2. **separate cells**: every cell can be told apart from its neighbours
3. **countable runs**: a run of cells in the same state doesn't blur
   together; you can count the cells in it at a glance
4. **minimize collisions**: keep the symbols' other meanings from getting in
   the way. be pragmatic about it: what collides depends on the context the
   notation is read in, and no symbol is free of other meanings, so this is a
   judgement, not a ban
5. **clear edges**: it's clear where a written strand starts and ends

`|xx___x__|` breaks rule 3: in many fonts the underscores merge into one line,
so it's hard to tell how many null cells there are.

rule 4 is the subtle one. 0 and 1 are also numbers, so `1 0 1 0 0 1 0 0` could
be eight states, or eight amounts that happen to be 0 or 1, and the symbols
alone can't say which. rows of amounts like that do come up (weights, in
"structures"), so here digits are a poor choice for states, and a row of digits
always means amounts.

no pair of symbols is entirely free of other meanings: `x` is also a letter,
and `.` a full stop. in a run they don't read as anything else, but a single
`x` could. that's what rule 5 is for: in the keyboard form a strand always has
its edges, so `|x|` is clearly a strand of one true cell. (in figures, where a
strand sits on its own line with labels, the layout marks its edges.)

### edges show the type

in the keyboard form, the edges around a strand say its type:

    )xx...x..(    circular          round brackets turned outward: the edges open
                                    onto each other, as if the ends join round the back
    <xx...x..>    linear            pointing outward: an end on each side, and
                                    nothing beyond
    /xx...x../    unidirectional    leaning forward: change goes forward only, to a
                  fluid             solid type
    \xx...x..\    bidirectional     leaning back: change can come back too
                  fluid
    |xx...x..|    abstract          plain upright walls: no lean, no form, apart from
                                    type
    [xx...x..]    scoped            a piece of a larger strand: it has ends, but
                                    there's more beyond them

each edge says what it is without the context: fluid leans, because it changes,
forward if change only goes forward, back if it can come back; abstract stands
upright and plain. the two kinds of fluid differ from the very first
character, so a reader can tell them apart without scanning to the end. the
backslash is the one cost: written inside a string, where a backslash escapes,
it has to be doubled, `"\\xx...x..\\"`.

**zero** is `|><|`: the plain walls pushed together, with no space left between
them. it only takes the plain walls, since with no cells there's nothing to be
a circle or a line, and nothing inside could be a cell, so it can't be taken
for a strand. `>…<` isn't used, so zero's middle can't be mistaken for edges
turned inward.

### the display form

in the display form, the shapes of the cells carry the type, so no edges are
needed. each shape is its keyboard edges closed up into every cell, and true and
null are the same shape in the same place, full or hollow:

    )xx...x..(    ● ● ○ ○ ○ ● ○ ○         circles, from round brackets
    <xx...x..>    ▲ ▲ △ △ △ ▲ △ △         triangles, from < and > turned upright
    |xx...x..|    ■ ■ □ □ □ ■ □ □         squares, from straight walls
    /xx...x../    ◢ ◢ ◿ ◿ ◿ ◢ ◿ ◿         corner triangles, from / closed up: cut
                                          along a forward lean
    \xx...x..\    ◣ ◣ ◺ ◺ ◺ ◣ ◺ ◺         corner triangles, from \ closed up: cut
                                          along a back lean
    [xx...x..]    [ ▲ ▲ △ △ △ ▲ △ △ ]     a piece is linear in its own terms;
                                          the brackets say there's more beyond
    |><|          |▶◀|                    zero

a single ● can't be mistaken for anything else, so the shapes do the job the
edges do in the keyboard form. because true and null keep the same shape in the
same place, a row keeps an even rhythm, whichever states sit side by side. most
figures in these chapters use the abstract squares: they don't need a type.
where no cells are drawn (in points and labels, below, and in scopes, in
"structures"), the edges stay, with → and − in place of -> and -. square
brackets around cells get a space inside them, like the cells do: `[ ▲ △ ▲ ]`.
ranges and other numbers stay as they are: `[5→8]`.

the display form needs geometric shapes (● ○ ▲ △ ◢ ◿ ◣ ◺ ■ □), which most
modern fonts include. some terminals give them two columns instead of one, and
not every font draws them all the same width, which can upset alignment. where
they aren't available, write the keyboard form, or any other symbols that
follow the five rules: the shapes are one read-optimized choice, not the only
one.

(a tangent: with true and null differing only in fill, size, direction and
turn are left free. if a later use needs to show an extra property of each
cell, those are the first things to use.)

### the point form

a strand can also be written by its points, after its resolution:

    |xx...x..|   →   |8: 0,1,5|
    )x..x.(      →   )5: 0,3(

the resolution has to be there: without it, `|x..x.|` and `|x..x...|` would
both come out as `0,3`. an all-null strand has no points: `|4:|`. here the
digits are positions, which are numbers, so rule 4 holds. the point form is
shorter when few cells are true; the cell form shows the arrangement at a
glance.

### labels

a strand can be given a name, a **label**, to refer to it later:

    S := |x.xx..|

`:=` means "is defined as", which keeps `=` free for saying two things are the
same. labels start with an uppercase letter and are never `X`, so they can't be
mistaken for cells; words work too, like `Primes` or `S1`. inside edges, a
label stands for its cells: `)S(` is S as a circle. a type can only be given to
an abstract or fluid label: if S is already circular, `)S(` just repeats its
type, and `<S>` isn't allowed. like the point form, a label can carry its
resolution: `)6: S(`. a label is defined once: it names one value, and never
changes to mean another. in these chapters, each example's labels belong to
that example: the same letter can name a different strand in another one.

### descriptions

a **description** lists what's known about a strand, in braces:

    {r: 12, d: 7}         resolution 12, density 7
    S{r: 12, d: 7}        S: some strand with resolution 12 and density 7

on its own, a description picks out every strand that fits it: `{r: 12, d: 7}`
fits 792 different strands, not one. keys can be full words (`resolution: 12`)
or short ones, but a short key, like a short label, is only used once it's been
mapped to its full name. so far: `r` for resolution, `d` for density and `s`
for sparsity. every number comes with its key, so nothing has to be guessed
from its position.

### repetition

outside the edges is context. `~` says a strand repeats, out there:

    )x..x.(~       repeats without end
    )x..x.(~3      repeats 3 times

it describes the surroundings and doesn't change the strand: its resolution is
still 5. the study of strings writes repetition as a power, w³ for w three
times over, but that *builds* a new, longer string; here `^` means building it
(see repeat, in "functions").

### inside other formats

the notation is defined on its own terms. inside another format that already
uses some of its symbols, it's escaped the way that format asks, never changed
to suit it. in Markdown, for example, `|` splits table columns (typed `\|`
there), `*` and `~` can turn text bold or struck through, and a bare `<x>` can
vanish as an HTML tag. inside code formatting, most of this goes away.

### rotating

a written strand always has a first cell, even when it's circular,
where it's simply cell 0. to start from another cell, rotate it so that cell
comes first: starting `)xx...x..(` at cell 5 gives `)x..xx...(`; in points,
`)8: 0,1,5(` gives `)8: 0,3,4(` (see rotate, in "functions").

### comparisons

identity's comparisons have symbols of their own:

| comparison | keyboard | display |
| --- | --- | --- |
| identical | `=` | `=` |
| fits | `~=` | `≃` |
| converts | `<->` | `⇄` |
| the same up to type | `==` | `≈` |
| matches | `===` | `≍` |

    /x../ ~= )x..(        fits
    )x..( <-> <x..>       converts
    /x../ == <x..>        the same up to type: here, because it fits
    )x..( == <x..>        the same up to type: here, because it converts
    [x..] === <x..>       matches: a piece and a whole line, with the same cells
    [x..] === )x..(       matches: a piece and a whole circle; only the cells count

the more `=` signs, the more is set aside: `=` sets aside nothing, `==` the
type, and `===` the type and the context. (this runs opposite to javascript,
where `===` is the strictest.) `<->` needs spaces around it, so it's never read
as edges.

## why not "binary string"

write each cell's state as 1 for true and 0 for null and you get a binary
string:

    ■ ■ □ □ □ ■ □ □   →   11000100

it's a familiar way to write something like a strand, and it follows the first
three rules above, though not the fourth, and with no edges, not the fifth
either. we don't call a strand a binary string, and we don't write it with
digits, for three reasons.

**the name should say what the object is.** a strand is named for its shape:
one dimension, separate cells, open or closed into a loop. it says nothing
about what its cells mean, since that's the job of a perspective: read as
things and the space between them, a strand is a spacer; read as truth values,
it's logic. "binary string" isn't neutral: it brings in encoding.

**this encoding is literal; most binary encodings aren't.** in a strand's
string, each character is the cell at the same position: reading the string
is looking at the strand, with nothing to translate. binary encodings usually
have a step of translation in between:

- in a **binary number**, position matters, so it's partly geometric. but
  each position stands for a size (1, 2, 4, 8, …), and the string means the
  total they add up to
- in most other uses (text, images or sound stored as bits), the order is a
  **serialization**: chosen for storing or sending, with positions that mean
  nothing until a format decodes them

so "binary string" suggests something to be decoded. a strand is a discrete
geometric object, and its written form is a literal picture of it. so we use
the language of space (cells, positions, distances), not the language of
encoding (bits, digits, codes).

**digits are needed for other things.** this is rule 4 above: digits stay
numbers. a 0 would also read as zero (no cells at all).

## a note on "cell"

"cell" has established meanings elsewhere, and some come close to this one:

- **cellular automata**: the simplest kind has cells along one dimension, each
  in one of two states, the same picture as a strand. but there the cells are
  updated by a rule, step after step. a strand has no rule and no steps; it's
  just the arrangement
- **topology**: cells are the pieces a space is glued together from, in any
  number of dimensions. close in spirit, but none of that theory is assumed
  here
- **everyday uses** (spreadsheets, computer memory, biology): a cell holds or
  does something

here a cell is only this: one piece/slot of a strand's space, with a position
and one of two states.

## a note on the states' names

the two states can be named in more than one way, and no pair of names is the
only or the best one. each perspective has its default names (see "two states",
in "basics"):

| perspective | default names | other names that fit |
| --- | --- | --- |
| asymmetric | **true** (■) and **null** (□) | present and absent, marked and unmarked, figure and ground |
| symmetric | **true** and **false** | 1 and 0, yes and no |

true is the same in both default pairs; only the other name changes. so where
the functions that combine strands cell by cell take logic's symmetric
perspective, null reads as false (see "functions").
