# notation

## writing a spacer down

a spacer is written in one of two forms, which map one to one:

- **typed/keyboard**: `x` for true and `.` for null, with no spaces, in
  order from cell 0. easy to enter by hand
- **display/read-only**: shapes, with a space between cells. purer to read

anyone, or any program, can write either; the typed form is simply easier on a
keyboard.

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
5. **clear edges**: it's clear where a written spacer starts and ends

`|xx___x__|` breaks rule 3: in many fonts the underscores merge into one line,
so it's hard to tell how many null cells there are.

rule 4 is the subtle one. 0 and 1 are also numbers, so `1 0 1 0 0 1 0 0` could
be eight states, or eight amounts that happen to be 0 or 1, and the symbols
alone can't say which. rows of amounts like that do come up (weights, in
"structures"), so here digits are a poor choice for states, and a row of digits
always means amounts.

no pair of symbols is entirely free of other meanings: `x` is also a letter,
and `.` a full stop. in a run they don't read as anything else, but a single
`x` could. that's what rule 5 is for: in the typed form a spacer always has its
edges, so `|x|` is clearly a spacer of one true cell. (in figures, where a
spacer sits on its own line with labels, the layout marks its edges.)

### edges show the reading

in the typed form, the edges around a spacer say how it's read:

    )xx...x..(    circular      round brackets turned outward: the edges open
                                onto each other, as if the ends join round the back
    <xx...x..>    linear        bounded: an end on each side, and nothing beyond
    [xx...x..]    scoped        a piece of a larger spacer: it has ends, but
                                there's more beyond them
    |xx...x..|    fluid         plain walls: just the spacer, no reading chosen

**zero** is `|><|`: the walls pushed together, with no space left between them.
it only takes the plain walls, since with no cells there's nothing to read as a
circle or a line, and nothing inside could be a cell, so it doesn't read as a
spacer. `>…<` isn't used, so zero's middle can't be mistaken for edges turned
inward.

### the display form

in the display form, the shapes of the cells carry the reading, so no edges are
needed. each shape is its typed edges closed up into every cell, and true and
null always differ twice: solid or hollow, and in size, direction or turn:

    )xx...x..(    ● ● ⚬ ⚬ ⚬ ● ⚬ ⚬         circles, from round brackets: big solid
                                          true, small hollow null
    <xx...x..>    ▲ ▲ ▽ ▽ ▽ ▲ ▽ ▽         triangles, from < and > turned upright:
                                          true up, null down
    |xx...x..|    ■ ■ ◇ ◇ ◇ ■ ◇ ◇         squares, from straight walls: a solid
                                          square, and a hollow one turned (a diamond)
    [xx...x..]    [ ▲ ▲ ▽ ▽ ▽ ▲ ▽ ▽ ]     a piece is linear in its own terms;
                                          the brackets say there's more beyond
    |><|          |▶◀|                    zero

a single ● can't be mistaken for anything else, so the shapes do the job the
edges do in the typed form. the figures before this section use the fluid
shapes: no reading chosen yet. where no cells are drawn (in points and labels,
below, and in scopes, in "structures"), the edges stay, with → and − in place
of -> and -. square brackets around cells get a space inside them, like the
cells do: `[ ▲ ▽ ▲ ]`. ranges and other numbers stay as they are: `[5→8]`.

the display form needs geometric shapes (● ⚬ ▲ ▽ ■ ◇), which most modern fonts
include. some terminals give them two columns instead of one, which can upset
alignment; ⚬ is drawn narrower than the others there, so circular rows are the
first to go out of line. where they aren't available, write the typed form, or
any other symbols that follow the five rules: the shapes are one read-optimized
choice, not the only one.

(a tangent: having true and null differ twice spends a second visual
difference, size, direction or turn, that could otherwise carry something
else. if a later use needs to show an extra property of each cell, that
second difference is the first thing to give back.)

### points

a spacer can also be written by its points, after its resolution:

    |xx...x..|   →   |8: 0,1,5|
    )x..x.(      →   )5: 0,3(

the resolution has to be there: without it, `|x..x.|` and `|x..x...|` would
both come out as `0,3`. an all-null spacer has no points: `|4:|`. here the
digits are positions, which are numbers, so rule 4 holds. the point form is
shorter when few cells are true; the cell form shows the arrangement at a
glance.

### labels

a spacer can be given a name, a **label**, to refer to it later:

    S := |x.xx..|

`:=` means "is defined as", which keeps `=` free for saying two things are the
same. labels start with an uppercase letter and are never `X`, so they can't be
mistaken for cells; words work too, like `Primes` or `S1`. inside edges, a
label stands for its cells: `)S(` is S read circularly. a reading can only be
applied to a fluid label: if S is already circular, `)S(` just repeats its
reading, and `<S>` isn't allowed. like the point form, a label can carry its
resolution: `)6: S(`. a label is defined once: it names one value, and never
changes to mean another. in these chapters, each example's labels belong to
that example: the same letter can name a different spacer in another one.

### descriptions

a **description** lists what's known about a spacer, in braces:

    {r: 12, d: 7}         resolution 12, density 7
    S{r: 12, d: 7}        S: some spacer with resolution 12 and density 7

on its own, a description picks out every spacer that fits it: `{r: 12, d: 7}`
fits 792 different spacers, not one. keys can be full words (`resolution: 12`)
or short ones, but a short key, like a short label, is only used once it's been
mapped to its full name. so far: `r` for resolution, `d` for density and `s`
for sparsity. every number comes with its key, so nothing has to be guessed
from its position.

### repetition

outside the edges is context. `~` says a spacer repeats, out there:

    )x..x.(~       repeats without end
    )x..x.(~3      repeats 3 times

it describes the surroundings and doesn't change the spacer: its resolution is
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

a written spacer always has a first cell, even when it's read circularly,
where it's simply cell 0. to start from another cell, rotate it so that cell
comes first: starting `)xx...x..(` at cell 5 gives `)x..xx...(`; in points,
`)8: 0,1,5(` gives `)8: 0,3,4(` (see rotate, in "functions").

## why not "binary string"

write each cell's state as 1 for true and 0 for null and you get a binary
string:

    ■ ■ ◇ ◇ ◇ ■ ◇ ◇   →   11000100

it's a familiar way to write something like a spacer, and it follows the first
three rules above, though not the fourth, and with no edges, not the fifth
either. we don't call a spacer a binary string, and we don't write it with
digits, for three reasons.

**the name should match the object's affordance.** an affordance is what an
object lets you do, and a spacer lets you space things out: it's about where
things sit and how far apart they are. so it's named after that.

**this encoding is literal; most binary encodings aren't.** in a spacer's
string, each character is the cell at the same position: reading the string
is looking at the spacer, with nothing to translate. binary encodings usually
have a step of translation in between:

- in a **binary number**, position matters, so it's partly geometric. but
  each position stands for a size (1, 2, 4, 8, …), and the string means the
  total they add up to
- in most other uses (text, images or sound stored as bits), the order is a
  **serialization**: chosen for storing or sending, with positions that mean
  nothing until a format decodes them

so "binary string" suggests something to be decoded. a spacer is a discrete
geometric object, and its written form is a literal picture of it. so we use
the language of space (cells, positions, distances), not the language of
encoding (bits, digits, codes).

**digits are needed for other things.** this is rule 4 above: digits stay
numbers. a 0 would also read as zero (no cells at all).

## a note on "cell"

"cell" has established meanings elsewhere, and some come close to this one:

- **cellular automata**: the simplest kind has cells along one dimension, each
  in one of two states, the same picture as a spacer. but there the cells are
  updated by a rule, step after step. a spacer has no rule and no steps; it's
  just the arrangement
- **topology**: cells are the pieces a space is glued together from, in any
  number of dimensions. close in spirit, but none of that theory is assumed
  here
- **everyday uses** (spreadsheets, computer memory, biology): a cell holds or
  does something

here a cell is only this: one piece/slot of a spacer's space, with a position
and one of two states.
