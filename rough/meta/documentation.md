# documentation

**in short.** what documentation is here, and what it's for: a record of
perspective, written well enough to be checked, revised as the thinking
moves, and read to use, to learn or to challenge. it's set apart from its
neighbours: tutorials, references, specifications and journals.

the concepts here are listed, with stable IDs, in
[concepts.md](../../models/concepts.md).

## a record of perspective

**builds on:** perspective, in "approach".

documentation is usually a description of a product: here's what it does, and
how to use it. here it's more than that. the docs record how a set of ideas
looks from a particular place: what's chosen, what's set aside, and why, along
with the case against. the docs are the primary work. the code follows from
them: first a test set drawn from the docs, then implementations.

someone who records perspective this way is a **documentarian** of it, the
way a documentary records a subject: from somewhere, openly, without claiming
to be the only view. (why this repository is written that way is personal,
and in [personal](personal.md).)

## writing as thinking

writing a thought down well enough that someone else can check it is how the
thought gets tested. gaps that hide in the head show up on the page: a word
used for two things, a definition that doesn't cover its cases, an idea used
before it's explained. the docs aren't written after the thinking is done;
writing them is part of the thinking.

## telling documentation apart

the docs are easiest to read when it's clear what kind of writing they are:

- **not a tutorial or a how-to guide**: they don't walk a reader through a
  task. they're mostly explanation, with reference alongside: the concept
  index, and the definitions
- **not a specification**: a specification says what must hold. these docs
  say what's chosen, why, and what else could have been
- **not a journal**: a journal is dated and fixed. these docs are revised as
  the thinking moves, and their history is kept separately, in version control
  and in frozen versions

## living documents

**builds on:** frozen version, in "documents".

the docs are never finished. each chapter says what it is now; the history of
how it got there is kept, not deleted, but it isn't the docs. a frozen version
marks a point worth keeping whole (see "frozen versions", in
[documents](../../models/documents.md)).

## readers

the docs are written for people first, and for AI too (see [ai](ai.md)).
a reader comes for one of three things:

- **to use**: to apply a model, or build on it
- **to learn**: to understand the ideas, in order
- **to challenge**: to find where the reasoning fails

the docs try to serve all three, and the third is the one they're most
written for: a perspective that can't be challenged can't be improved.

## the case against

documentation can stand in for doing: a well-written idea can feel finished
when it hasn't been tried. and docs drift from code, as each changes without
the other. the planned test set, drawn from the docs, is the guard: when the
docs and the code disagree, the tests say so.

## related

_from memory_: the Diátaxis framework, which sorts documentation into
tutorials, how-to guides, reference and explanation; literate programming,
where the explanation and the code are one work; docs-as-code; and
architecture decision records, dated records of a decision and its reasons.
