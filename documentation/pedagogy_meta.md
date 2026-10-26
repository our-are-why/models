# pedagogy

**in short.** how the docs try to teach: plain words first, ideas in an order
where nothing is used before it's explained, a short version before the long
one, one running example, and every idea set against what it's easy to
mistake it for. each is a choice about how a reader learns, with its reasons
and its costs.

**builds on:** approach, semiotics.

the concepts here are listed, with stable IDs, in
[concepts.md](concepts.md).

## plain words first

a technical term is introduced with a plain explanation, or paired with an
established or alternative name at first use (arrangement/distribution).
where a plain word will do, it's used instead.

the reason is who can get in. a reader who knows the established term loses
little to a plain word beside it; a reader who doesn't is stopped by its
absence.

**the case against.** plain words carry everyday meanings that technical ones
avoid, and they can sound less precise than they are. the naming idea in the
approach weighs this (see "naming", in "approach").

## dependency order

nothing is used before it's explained. chapters are numbered in the order they
can be read, each says what it **builds on**, and the concept index checks
that no concept builds on one defined after it.

the reason is that a learner can't hold an undefined word open for long: they
fill it with a guess, and the guess becomes what they learned. when the strand
chapters were first split, the check found one place where the points were
used before they were defined, and the definition moved earlier.

**the case against.** strict order can push the interesting part far back,
behind definitions a reader doesn't yet care about. a short summary at the top
of each chapter is the counterweight: it says where the chapter is going
before it starts building.

## the short version first

each chapter opens with **in short**: a few plain sentences on what it covers.
a reader can stop there, or read on knowing where they're headed.

**the case against.** a summary can be mistaken for the whole, and quoted
without the detail that qualifies it. summaries should stay true on their own,
even when they leave things out.

## one running example

the strand chapters keep coming back to one strand, `■ ■ ◇ ◇ ◇ ■ ◇ ◇`, with
points 0, 1 and 5. it's counted, measured, scoped, stacked and rotated, so
that each new idea is the only new thing on the page. new examples come in
only when the running one can't show what's needed.

**the case against.** one example can make an idea look narrower than it is:
a reader may take what's true of it as true in general. the edge cases, such as
the smallest strands and zero, are there to push back.

## telling things apart, for a learner

the approach's idea of telling things apart (see "telling things apart", in
"approach") has a teaching side. a learner's mistakes come mostly from the
nearest neighbours of an idea: a gap mistaken for an interval, a layer for a
scope, null for unknown. saying what a thing isn't, right after saying what it
is, heads off the likeliest wrong lesson.

## knowing what to trust

a learner needs to know which parts are settled. the status labels (see
"status labels", in "documents") tell them: what's checked, what's recalled,
what's deferred. without them, everything reads as equally certain.

## seen from elsewhere

- pedagogy, from AI: in [ai](ai_meta.md)

## related

_from memory_: progressive disclosure, in design; prerequisite graphs and
spiral curricula, in teaching; worked examples and contrasting cases, in the
study of learning.
