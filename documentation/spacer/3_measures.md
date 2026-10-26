# measures

**in short.** how to measure inside a spacer: steps and their directions,
distances (two of them round a circle), the intervals and gaps between
points, the joints, seams, bands and runs, and why everything measured is
a whole number.

**builds on:** basics, notation.

the concepts here are listed, with stable IDs, in [concepts.md](../concepts.md).

## steps and distances

a **step** moves from a cell to a neighbouring cell. there are two directions
to step in:

- **+**: towards higher cell numbers; drawn to the right, or clockwise. when
  no sign is written, + is meant
- **−**: towards lower cell numbers; drawn to the left, or counter-clockwise

like the numbering itself, which way is + is a convention, and so are right
and clockwise: they're just how + is usually drawn.

the readings differ at the ends:

- **circular**: there are no ends, so stepping wraps round. one step − from
  cell 0 is the last cell; one step + from the last cell is cell 0
- **linear**: the ends stop you. there's no step − from the first cell, and no
  step + from the last
- **fluid**: stepping works between the ends. going past them belongs to a
  shape, and a fluid spacer has none until a use gives it one

as far as a linear spacer is concerned, nothing exists beyond its ends: it's
**bounded**. sometimes, though, a linear spacer is **scoped**: a piece of
something larger, like a stretch of an endless line. the cells beyond its ends
do exist, just not in this spacer. it's still bounded as a spacer, since its
cells don't record what lies beyond them; the larger whole is context, like an
origin.

the **distance** from one cell to another is how many steps it takes, and it's
never negative; a sign only says which way the steps go. read linearly, there's
one way to go: from cell 0 to cell 5 is +5, and back is −5. read circularly,
you can go either way round: at resolution 8, from cell 0 to
cell 5 is +5 or −3, and the two distances, 5 and 3, add up to the resolution.
unless a sign or the word "shortest" says otherwise, the distance means the +
one: 5 here. the shorter of the two is just as valid, but it has to be asked
for.

### intervals and gaps

a spacer's points are the positions of its true cells (see "basics"). between
one point and the next, going +, there are two things to measure:

- the **interval**: the distance from one point to the next
- the **gap**: how many null cells lie between them

an interval is always one more than its gap: the gap, plus the step onto the
next point.

    cell        0 1 2 3 4 5 6 7
                ■ ■ ◇ ◇ ◇ ■ ◇ ◇       points 0, 1, 5

    circular    intervals  1 4 3      add up to the resolution, 8
                gaps       0 3 2      add up to the sparsity, 5

    linear      intervals  1 4        add up to the distance from the first point to the last, 5
                gaps       0 3        plus end gaps of 0 and 2; all together, the sparsity, 5

- **circular**: one interval and one gap per point. with a single point, the
  interval goes all the way round, the whole resolution
- **linear**: one interval and one gap fewer than there are points, plus an
  **end gap** at each end: the null cells before the first point and after
  the last. in a scoped spacer, the end gaps may be cut short: the null cells
  can carry on past the ends
- an all-null spacer has no points, so no intervals and no gaps. in an
  all-true spacer every interval is 1 and every gap is 0

(in number theory, a "prime gap" is the difference between neighbouring
primes: here, that's an interval, not a gap.)

### joints, seams, bands and runs

every place where two neighbouring cells meet is a **joint**: a line of n
cells has n − 1 joints, and a circle of n cells has n, since its last cell and
cell 0 meet too. a **seam** is a joint where the two cells are in different
states. the seams cut a spacer into **bands**: stretches of cells in the same
state, each as long as it goes. a band of two or more cells is a **run**.
(**panel** would work as well as band: panels are what seams join.)

    cell      0 1 2 3 4 5 6 7
              ■ ■ ◇ ◇ ◇ ■ ◇ ◇
    bands     ■ ■ | ◇ ◇ ◇ | ■ | ◇ ◇       4 bands, 3 of them runs

- **linear**: `<xx...x..>` has 3 seams and 4 bands, so one more band than seams
- **circular**: the last and first cells are neighbours too, so there can be a
  seam between them: `)xx...x..(` has 4 seams and 4 bands. a band can also
  carry on past the last cell into the first: `)x...xx(` has 2 seams and 2
  bands, `[xxx]` (cells 4, 5, 0) and `[...]`, both runs
- an all-null or all-true spacer has no seams: one band covering
  everything

bands follow from the gaps: a gap of 0 joins two points into the same true
band, and any other gap is a null band.

### whole numbers

everything counted or measured in a spacer is a whole number. counts and
distances are never negative; a sign only gives a direction. resolution is at
least 1, density and sparsity run from 0 to the resolution, and cells are
numbered from 0 to one less than the resolution. a number outside that range
doesn't name a new cell: read circularly, it wraps round (cell −1 is the last
cell); read linearly, there's no cell there. proportions, like "half the
cells", only come in with generators.
