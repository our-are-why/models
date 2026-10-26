# documents

**in short.** how the docs are organized and written: domains and their
stripes of chapters, the shape every chapter shares, the concept index and its
IDs, frozen versions, the labels that say how something is known, and the
writing conventions.

**builds on:** approach, semiotics.

the concepts here are listed, with stable IDs, in [concepts.md](concepts.md).

## domains and stripes

a **domain** is one subject the docs cover. so far there are two: the meta
domain, which is this one, and spacers. a domain's chapters share a suffix and
are numbered in reading order, so they line up as its **stripe**:

    1_approach_meta.md    2_semiotics_meta.md    3_documents_meta.md
    1_basics_spacer.md    2_notation_spacer.md   …    7_identity_spacer.md

- each chapter builds only on the chapters before it in its stripe, or on
  other domains it depends on
- the meta domain comes first: other domains build on it, and it depends on
  none of them
- a file that covers every domain has no suffix: [concepts.md](concepts.md),
  for now

## the shape of a chapter

each chapter opens the same way:

- a title, in plain words
- **in short**: what the chapter covers, in a few plain sentences
- **builds on**: the chapters it needs
- a pointer to the concept index

the chapter itself then runs in dependency order: nothing is used before it's
defined. the concept index makes that checkable, since no concept may build on
one defined after it.

## concepts and their IDs

every concept the docs define is listed in [concepts.md](concepts.md), with:

- a stable **ID**: C and a number. numbers are given in order, and never reused
  or renumbered: a renamed concept keeps its ID, and a retired one leaves a gap
- its former names, so older notes can still be read
- a line in plain words, and the IDs of the concepts it builds on

a new concept gets the next free number, whichever chapter it's in.

## frozen versions

a whole draft can be **frozen**: `spacer_v0.md` is the first draft of the
spacer domain, kept exactly as it was when the chapters were split from it. a
frozen version is never edited. it's a record of how the ideas stood, not part
of the docs.

## status labels

how something is known is said where it's claimed (see "honesty about status",
in "approach"):

- **_from memory_**: recalled, and not yet checked
- **checked by computation**: with how far the check went, such as "369 of
  369 families up to 60 cells", in `rough/PRIOR_WORK.md`
- **deferred**: noted on purpose, and left for later
- **established names**: given as handles for searching, not as authorities

## writing conventions

- plain words first. a technical term comes with a plain explanation, or is
  paired with an established or alternative name at first use:
  arrangement/distribution
- the docs are written in lowercase, headings and the starts of sentences
  included. names written in code keep their case: `Rotate`, `S`
- notation goes in code formatting, so that no host format can read it as
  formatting of its own (see "inside other formats", in "notation")
- labels in examples belong to their example
- lines are wrapped at 80 characters, except in tables and code blocks
- a cross-reference names the section in quotes, and the chapter if it's
  another one: (see "weights", in "structures")

## rough notes

the `rough/` folder holds working notes, such as `PRIOR_WORK.md`: leads,
established names and ideas to explore, collected along the way. they aren't
docs, and can be wrong.

## to come

- figures, generated from one script
- a crosswalk from these docs to established fields, and a doc of the
  established mathematics
- a test set, then implementations
