# crossings

a tangent, caught on 2026-10-27 while asking whether fluid's "neither a loop
nor a line yet" assumed there are only two solid types. not developed; kept to
explore.

## the idea

a strand-like space that meets itself: it runs along like a strand, but at one
or more places it crosses itself, and the crossing is real in the space, not
just in a drawing. there are two ways a crossing could be real:

- **a shared cell**: two passes go through the same cell, so it's one cell with
  more than two neighbours
- **a bridge**: two cells far apart along the run become neighbours, without
  becoming one cell

(a crossing that's only in the drawing, or in how a strand is laid into a
larger space, like a scope that runs more than one lap round a circle, is set
aside here: the strand itself doesn't change.)

## families

sorted by what the ends do, each with n crossings:

- **open at both ends**: a run with two loose ends that meets itself n times
- **closed**: a loop that meets itself n times. with one shared cell, it's a
  figure 8: two loops sharing a cell
- **one end attached**: one end meets the run somewhere along it, the other
  stays loose. with no further crossings, it's a tail running into a loop
- **both ends attached**: each end meets the run somewhere along it: two loops
  joined by a run, or three runs between two shared cells

_from memory_, names elsewhere: the tail into a loop is a **ρ** (rho), the
shape of any sequence that eventually repeats, as in cycle detection and
repeating decimals; two loops sharing a cell is a wedge of two circles, in
topology; three runs between two points is a theta graph, and two loops joined
by a run a dumbbell or handcuff graph, in graph theory.

## what changes

- **one dimension breaks at the crossings**: from a crossing you can step more
  than one way or the other, so this is a discrete space, not a strand, unless
  a world widens what a strand is
- **the states are constrained**: a shared cell holds one state, so every pass
  through it must agree. a bridge adds no constraint
- **counts**: a shared cell is counted once, so the resolution is less than the
  length of the run
- **"the next cell"**: away from the crossings it's as clear as in a strand; at
  a crossing it branches

## to explore

- **a direction might rescue "next"**: if every cell has exactly one next cell,
  and only the cells before can branch, a tail into a loop keeps a single next
  everywhere. _from memory_: these are functional graphs, the shape of
  repeatedly applying a function. which families allow that?
- is any of this a **type**, a sibling of the strand in the space chapter's
  family, or something a world adds?
- which measures survive: distances (shortest way through), intervals and gaps
  (which way round at a crossing?), seams, runs
- what a crossing does to arrangements: how many arrangements a shape allows,
  given its shared cells
- uses, speculatively: two loops of different lengths sharing one cell look like
  two rhythms meeting on a shared downbeat; a tail into a loop is a lead-in
  followed by a repeat
