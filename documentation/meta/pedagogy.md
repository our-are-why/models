# pedagogy

**in short.** how the docs try to teach: plain words first, ideas in an order
where nothing is used before it's explained, a short version before the long
one, one running example, and every idea set against what it's easy to
mistake it for. then three bigger ideas about teaching: the meaning of a form,
not only its mechanics; a subject as a vehicle for training thought; and
showing the path, not only the result. each is a choice about how a reader
learns, with its reasons and its costs.

the concepts here are listed, with stable IDs, in
[concepts.md](../concepts.md).

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

nothing is used before it's explained. a section that uses an idea from
elsewhere says so, in a **builds on** line, and the concept index checks that
definitions bottom out: no chain of "builds on" comes back to where it
started. order between chapters is shown in a map rather than fixed by
numbers, since some chapters lean on each other (see "the map", in
[documents](../documents.md)).

the reason is that a learner can't hold an undefined word open for long: they
fill it with a guess, and the guess becomes what they learned. when the strand
chapters were first split, the check found one place where the points were
used before they were defined, and the definition moved earlier.

understanding can go round where definitions can't: a reader may need a
later chapter to see why an earlier one matters, and that's fine, as long as
nothing is defined in terms of itself.

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

## meaning, not only mechanics

this is a framing of "reduce on purpose" (see [the approach](approach.md)),
from the side of teaching. learners are often taught to reduce an expression to
its simplest form as soon as they can, and rarely to ask what each form means.
`- 3` and `+ -3` become the same thing to them, though one takes three away and
the other adds a debt. taught that way, mathematics looks purely mechanical,
and the semantics it carries is left out, apart from attempts to show its use
in an imagined real-world setting. teaching the meaning of a form, and when to
reduce it, shows a side of mathematics that's easy to miss, and maybe its most
valuable one.

**the case against.** the mechanical view is valid too, and fluency with
mechanics is what frees attention for meaning. the point is to teach both, not
to swap one for the other.

## the subject as a vehicle

a subject can be taught for itself, or as a **vehicle**: a concrete, demanding
place to exercise general mechanisms of thought, such as abstracting,
analysing, organizing and holding structure in mind, that work beyond it. on
this view, learning algebra isn't the point of learning algebra: the
mechanisms it trains are. mathematics may be the clearest vehicle, but it isn't
the only one. years of writing software seem to work the same way (see
[personal](personal.md)), and in these docs, strands have been the
vehicle, and much of the meta domain is what they trained.

**the case against.** this is where the idea is weakest, and it should be said
plainly. _from memory_: the old view that a subject trains the mind the way
exercise trains a muscle (formal discipline) has been tested since the early
1900s. research on **transfer** has found that near transfer, to similar
problems, holds up well, while far transfer, to reasoning in general, has
weak evidence, and expertise tends to stay in its own field. what seems to
help is making the mechanisms explicit and practising them as such, and long,
deep practice rather than a short course. so the claim here is a hypothesis,
about depth and explicitness, not a settled fact. talk of building "neurons"
for critical thought is a metaphor for it, not a finding.

## show the path

good teaching and honesty about discovery are the same move: showing how an
idea was reached, not only where it ended up. a result in its final, polished
order hides the questions, the false starts and the reasons, and a learner who
only sees the result learns the mechanics without the understanding.

these docs try to keep the path visible: the life of an idea (see
[process](process.md)), former names in the concept index, the frozen
first draft, and notes on where ideas came from, such as the strands' space
chapter, written where the idea was found.

**the case against.** the path can bury the result: a reader who wants the
answer has to dig through the history. so the two are kept apart: the chapters
say what holds now, and the path sits beside them.

## seen from elsewhere

- pedagogy, from AI: in [ai](ai.md)

## related

_from memory_: progressive disclosure, in design; prerequisite graphs and
spiral curricula, in teaching; worked examples and contrasting cases, in the
study of learning; instrumental and relational understanding (Richard Skemp);
the "deductivist" style that hides how mathematics is found, and the
"heuristic" style that shows it (Imre Lakatos, *Proofs and Refutations*); Paul
Lockhart's *A Mathematician's Lament*; George Pólya's *How to Solve It*;
formal discipline and transfer of learning; habits of mind, as a way to
organize what's taught.
