# documents

**in short.** how these docs are organized and written: domains, subdomains
and their stripes of chapters, topics that cut across them, the shape every
chapter shares, the concept index and its IDs, frozen versions, the labels
that say how something is known, and the writing conventions. it's the place
to start. why the docs are written at all, and what documentation is for, is
in [the meta domain](meta/documentation/1_foundations.md).

**builds on:** nothing; start here.

the concepts here are listed, with stable IDs, in
[concepts.md](concepts.md).

## domains and stripes

a **domain** is one subject the docs cover, with a folder of its own. so far
there are two: the meta domain, about how all of it is thought through and
made, and spacers. a domain can
have **subdomains**, folders of their own inside it. the chapters in a folder
are numbered in reading order, and line up as its **stripe**:

    documentation/
      documents.md    this file
      concepts.md
      meta/
        personal/     1_purpose.md
        modelling/    1_approach.md
        language/     1_semiotics.md
        pedagogy/     1_foundations.md
        documentation/  1_foundations.md
        ai/           1_foundations.md
        process/      1_foundations.md
      spacer/         1_basics.md … 7_identity.md, spacer_v0.md

- each chapter builds only on the chapters before it in its stripe, or on
  other stripes it depends on
- the meta domain comes first: other domains build on it, and it depends on
  none of them. its subdomains are read in the order above: personal,
  modelling, language, pedagogy, documentation, ai, process
- a file that covers every domain sits at the top, outside the domain folders:
  this one, and [concepts.md](concepts.md)

## cross-cutting topics

many topics cut across domains: pedagogy matters to AI, AI to pedagogy, and
naming to everything. rather than file each topic in one place and nowhere
else, a topic has one home and any number of framings:

- **home**: the topic's foundational, abstract treatment lives in exactly one
  place, its home subdomain. pedagogy's foundations are in `meta/pedagogy/`
- **framing**: another domain or subdomain can treat the topic from its own
  side, such as "pedagogy, from AI", in `meta/ai/`. a framing builds on the
  home, and links to it rather than restating it
- **no duplicate definitions**: a framing applies the home's concepts, or
  extends them. anything new it defines gets its own concept ID, where it's
  defined
- **both directions**: the home lists its framings under "seen from
  elsewhere", so a reader can find every side of a topic
- **size**: a framing starts as a section, and becomes a chapter of its own
  when it grows

it's the idea of more than one perspective (see "more than one perspective",
in "approach"), applied to the docs themselves.

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

every concept the docs define is listed in [concepts.md](concepts.md),
with:

- a stable **ID**: C and a number. numbers are given in order, and never reused
  or renumbered: a renamed concept keeps its ID, and a retired one leaves a gap
- its former names, so older notes can still be read
- a line in plain words, and the IDs of the concepts it builds on

a new concept gets the next free number, whichever chapter it's in.

## frozen versions

a whole draft can be **frozen**: `spacer/spacer_v0.md` is the first draft of
the spacer domain, kept exactly as it was when the chapters were split from it.
a frozen version is never edited. it's a record of how the ideas stood, not part
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
  arrangement/distribution (see "plain words first", in pedagogy)
- the docs are written in lowercase, headings and the starts of sentences
  included. names written in code keep their case: `Rotate`, `S`
- the personal chapters are written in the first person, because they're
  about who's writing. the rest are impersonal, though they carry the same
  perspective
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
