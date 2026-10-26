# process

**in short.** how the work gets done: how an idea goes from noticed to
documented, how drafts become chapters, how things get checked, and how
changes are kept and explained. the docs are the product; this is the way
they're made.

**builds on:** approach, documents.

the concepts here are listed, with stable IDs, in
[concepts.md](concepts.md).

## the life of an idea

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

## drafts and revisions

the docs grow in drafts. the strand domain, first called spacer, began as one
rough draft; when it
was ready to be shaped, it was frozen as a version, split into chapters with
its text unchanged, and then revised in the chapters. each step was its own
change, so each can be checked on its own: the split moved text and nothing
else, and the revision changed text and nothing else.

## open questions

questions that come up and can't be settled straight away are listed, then
worked through in order. each is either resolved, with the resolution
recorded, or deferred, with the reason. a question that turns out to be badly
posed is restated, not forced to an answer.

## consistency passes

after a run of changes, the whole of a domain is read again, start to finish,
looking for contradictions, leftovers from earlier versions, and rough joins.
the findings are reported first, sorted into what needs a decision and what's
mechanical, and only then fixed. the first pass over the strand chapters found
a word used for two things ("view"), a definition too narrow for what it
covered ("operation"), and about a dozen leftovers.

## checking

worked examples are recomputed by script, not trusted. a check says how far it
went: how many cases, up to what size. a claim recalled from memory stays
labelled until it's checked (see "status labels", in "documents").

## keeping changes

every change is kept, with a message that says what changed and why. moves
and renames keep their history. a rename changes every use at once; the
concept keeps its ID, and its former name is recorded.

**the case against.** process can turn into ceremony, slowing the ideas down
to serve itself. it's there to make thinking checkable, and should stay as
light as that allows.

## related

_from memory_: iterative design; version control, and the habit of small,
explained changes; literate programming, where the explanation and the work
are written together.
