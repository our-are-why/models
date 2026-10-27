# process

**in short.** how the work gets done. its mechanics: how an idea goes from
noticed to documented, how drafts become chapters, how things get checked, and
how changes are kept and explained. and its dynamics: how, over time, the work
moves between abstract and applied periods. the docs are the product; this is
the way they're made.

the concepts here are listed, with stable IDs, in
[concepts.md](../concepts.md).

## mechanics

### the life of an idea

an idea goes through a few stages, and doesn't have to reach the end:

- **noticed**: it comes up while working on something else, and gets a note,
  often in the rough notes
- **explored**: it's talked through, tried on examples, and compared with
  what's established, before anything is written into the docs
- **decided**: a name and a shape are settled, along with the reasons, and
  what was rejected
- **documented**: it goes into a chapter, in dependency order, with its
  concepts in the index
- **checked**: its examples are recomputed, and it's read against everything
  around it
- **deferred**, at any stage: noted on purpose, and left for later

the order matters most at one point: an idea is explored before it's written
down. writing too early fixes a shape that hasn't been tested.

### drafts and revisions

the docs grow in drafts. the strand domain, first called spacer, began as one
rough draft; when it was ready to be shaped, it was frozen as a version, split
into chapters with its text unchanged, and then revised in the chapters. each
step was its own change, so each can be checked on its own: the split moved
text and nothing else, and the revision changed text and nothing else.

### open questions

questions that come up and can't be settled straight away are listed, then
worked through in order. each is either resolved, with the resolution
recorded, or deferred, with the reason. a question that turns out to be badly
posed is restated, not forced to an answer.

### consistency passes

**builds on:** domain, in "documents".

after a run of changes, the whole of a domain is read again, start to finish,
looking for contradictions, leftovers from earlier versions, and rough joins.
the findings are reported first, sorted into what needs a decision and what's
mechanical, and only then fixed. the first pass over the strand chapters found
a word used for two things ("view"), a definition too narrow for what it
covered ("operation"), and about a dozen leftovers.

### checking

worked examples are recomputed by script, not trusted. a check says how far it
went: how many cases, up to what size. a claim recalled from memory stays
labelled until it's checked (see "status labels", in "documents").

### keeping changes

every change is kept, with a message that says what changed and why. moves
and renames keep their history. a rename changes every use at once; the
concept keeps its ID, and its former name is recorded.

**the case against.** process can turn into ceremony, slowing the ideas down
to serve itself. it's there to make thinking checkable, and should stay as
light as that allows.

## dynamics

### abstract and applied, in turn

the work doesn't stay at one level. it moves back and forth between two kinds
of period:

- **abstract periods**: deep thought, reframing, models and perspectives: a new
  domain sketched out, a word pulled apart, a whole meta domain drafted in a
  day
- **applied periods**: putting those abstractions to work, building and
  shipping, and realizing economic or cultural value with them. sometimes that
  means setting an abstraction aside on purpose, because value now matters
  more than refining it further

this **oscillation** is how each kind of period feeds the other. application
shows what the abstractions got wrong or left out; abstraction gives the next
round of application something better to work with. the meta domain was
written in one abstract stretch, and the work then turned back to strands,
because strands were what mattered next.

it's the idea of teaching both sides at once (see [pedagogy](pedagogy.md)) on
another axis. there, the pure and the applied form are held together in one
lesson; here, they take turns, across periods of work.

**when to switch.** abstraction stops paying when its questions only lead to
more questions, and nothing could be built from the answers yet. application
stops paying when it keeps running into the same unexamined assumption. both
are signs that it's time for the other kind of period.

**setting aside isn't losing.** a parked abstraction stays available: deferred
lists and rough notes keep it findable, with enough written down to pick it up
again (see "the life of an idea", above).

**the case against.** oscillation can hide avoidance: abstraction as a way of
never shipping, application as a way of never thinking. switching has a cost,
since each kind of period takes time to get back into. and some parked ideas
never come back, which may be right, or may be a loss nobody notices.

## related

_from memory_: iterative design; version control, and the habit of small,
explained changes; literate programming, where the explanation and the work
are written together; exploration and exploitation (James March), and doing
both by alternating over time, sometimes called temporal ambidexterity; Kolb's
learning cycle, from concrete experience to abstract ideas and back; divergent
and convergent thinking (J. P. Guilford), and the Double Diamond, in design;
Pasteur's quadrant (Donald Stokes), research driven by understanding and use
at once.
