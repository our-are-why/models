# readings

**in short.** a reading says what the two states mean. this chapter covers the
default reading, presence and absence, with its names, true and null, and what
it lets you count: density, sparsity and points; the spacer, the reading these
docs began with, and how it spreads across time, pitch and space; selection,
the reading of which positions are chosen; and symmetric readings, such as
truth values. the last three are named and sketched here, not developed.

the concepts here are listed, with stable IDs, in [concepts.md](../concepts.md).

a **reading** says what the two states mean (see "two states", in "basics"). in
the asymmetric perspective, it says what the two roles are; in the symmetric
one, what the two equals are. a world can take a reading; the strand itself
takes none.

(a side note, _from memory_: linguistics calls the asymmetric kind of pair
markedness. the unmarked member is the default, and the marked one is singled
out against it.)

## presence and absence: true and null

the default reading, the one the running text takes, reads the two roles as
presence and absence: a **true** cell holds something, and a **null** cell
holds nothing. (other names fit too: see "a note on the states' names", in
"notation".)

null means absence, not unknown: a null cell is decided, and holds nothing. (in
databases, null often means "unknown", a third state; here there's no third
state.)

### density, sparsity and points

once one state holds something, its counts get names of their own (see
"counts", in "basics"):

- **density**: how many cells are true
- **sparsity**: how many are null

      ■ ■ □ □ □ ■ □ □     resolution 8, density 3, sparsity 5

density and sparsity always add up to the resolution.

what the counts leave out, the **points** give: the positions of a strand's
true cells. for `■ ■ □ □ □ ■ □ □` they're 0, 1 and 5, and the density is how
many there are.

read this way, a strand's negative (see "combining strands", in "functions")
is the same arrangement/distribution, seen from its null space: the negative's
density is the original's sparsity.

### all true, all null and zero

the two strands with every cell in one state are **all true** and **all
null**. zero isn't the all-null strand: an all-null strand is a space with
nothing in it; zero is no space at all (see "zero", in "basics").

## spacer

read as things, and the space between them, a strand is a **spacer**: its true
cells are things, and its null cells are the space that keeps them apart. the
measures of intervals and gaps take this reading (see "measures"), and it's
where these docs began: the domain was first called spacer.

a spacer can be spread across something, a step per cell. what it's spread
across gives each use its own name.

### across time: rhythm

across time, a spacer is a **rhythm**: the cells are beats, and the true cells
are onsets. a bar that loops is circular; a phrase played once is linear.

    )x..x..x.(        the tresillo: 8 beats, onsets on 0, 3 and 6

(_from memory_: the tresillo, 3 + 3 + 2 beats, is common in Latin American
music.)

### across pitch: scales and chords

across pitch, a spacer is a scale or a chord: the cells are the 12 semitones of
an octave, and the true cells are the notes. notes an octave apart count as the
same note, so the strand wraps round: it's circular. notes in a fixed
register, without wrapping, make a linear strand.

    )x.x.xx.x.x.x(    a major scale: notes on 0, 2, 4, 5, 7, 9 and 11
    )x...x..x....(    a major triad: notes on 0, 4 and 7

the steps are equal in pitch, not in frequency: _from memory_, each
equal-tempered semitone multiplies the frequency by the same amount, about
1.06, so the frequencies of the cells aren't evenly spaced, though their
pitches are.

the major scale spreads its 7 notes as evenly as 12 cells allow, which makes it
an example for evenly spread arrangements, in a chapter still to come.

### across space, and others

across space, a spacer is the posts along a fence, or the lit pixels along a
line. there are likely others.

## selection

read as which positions are chosen, a strand is a **selection**. it's how a
layer reads its root: each of the layer's cells stands for one of the root's
points, and the layer chooses among them (see "layers", in "structures").

readings can meet. a triad is a selection from its scale: the layer
`)x.x.x..(` chooses the scale's notes 0, 2 and 4 (counting from 0; in music,
its 1st, 3rd and 5th), and flattens to the triad (see "flatten", in
"functions"):

    )x.x.xx.x.x.x( >> )x.x.x..(      the major scale, and the layer that chooses from it
    )x...x..x....(                   flattened: the major triad

## symmetric readings

in the symmetric perspective, a reading says what the two equals are. read as
truth values, true and false, a strand is a row of logical values, and the
cell-by-cell functions apply to it (see "combining strands", in "functions").
there are likely others.
