# pedagogy

**in short.** how the docs try to teach: plain words first, ideas in an order
where nothing is used before it's explained, a short version before the long
one, one running example, and every idea set against what it's easy to mistake
it for. then bigger ideas about teaching: the meaning of a form, not only its
mechanics; a subject as a vehicle for training thought; showing the path, not
only the result; teaching a form both pure and hidden in another domain, since
neither is the real one; problems with more than one valid answer; teaching the
meta out loud, with a thread of its own; a thread of each learner's own; and
teaching learners to ask. each is a choice about how a reader learns, with its
reasons and its costs.

the concepts here are listed, with stable IDs, in
[concepts.md](../../models/concepts.md).

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
[documents](../../models/documents.md)).

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

the strand chapters keep coming back to one strand, `■ ■ □ □ □ ■ □ □`, with
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

## both sides at once

**builds on:** framing, in "documents".

a form can be taught two ways. one is the **pure form**: minimal, noiseless,
already extracted, the way algebra is usually taught. the other is the **form
in the noise**: the same structure camouflaged inside another domain, among
subsystems pulling against each other. writing software is full of algebra,
for instance, and it's one of the most basic tools there, yet it's rarely
obvious at first glance.

**neither is the real one.** the pure form shows the structure, but taught
alone it stays in its vacuum: it's hard to recognize anywhere else. word
problems try to add context, but they come inside the class that teaches the
tool, so the hardest part of real use, choosing which tool fits, has already
been done for the student. the form in the noise shows how to find the
structure, but taught alone it may never be found. what's worth learning, the
form and the ability to see it, lies beyond either one. it takes both, side by
side, to sink in.

**choosing the tool.** _from memory_: mixing kinds of problems, so that each
starts with "which method is this?", is called interleaved practice, and it
tends to feel harder and teach better. physics and engineering classes force
the choice all the time, and that's where a weak pure foundation shows. so the
choice is taught, but late: most people stop before the classes that teach it,
and by then it's assumed rather than taught.

**both ends, not the middle.** it can sound like a contradiction to say that
teaching is too abstract and not abstract enough. it isn't: much of it sits in
a narrow middle, procedures that aren't quite abstract, in contexts that aren't
quite real. the call is to widen both ends. up, to abstraction taught as an
idea of its own, early and well beyond computing, with forms taught as forms.
and down, to real settings where several ideas are entangled at once and none
of them is labelled.

**across the curriculum.** schools mostly divide teaching by subject, each in
isolation: mathematics in the mathematics class, and hardly anywhere else. by
the docs' own rule for topics that cut across domains (see "cross-cutting
topics", in [documents](../../models/documents.md)), mathematics would keep its home,
and other subjects would each carry a framing of it: physics, music, art,
economics or a workshop, teaching the same forms from their side, entangled
with their own concerns. that may be where learning that transfers, and
critical thinking, come from.

**in these docs.** strands were found this way. the work started in a noisy,
meaningful setting, rhythms and evenly spread patterns, and the pure form came
out of it: first the strand, then discrete space (see
[space](../../models/strand/space.md), in strand). both are kept: the chapters, and the
path that led to them.

**the case against.** noise can swamp a beginner, who learns better with the
irrelevant cut away. camouflage only teaches if the form can eventually be
found, which is why the pure form has to be there beside it. and teaching
across the curriculum asks a lot: other teachers may not be confident in
mathematics, the timetable is already full, and courses that blend subjects can
end up diluting both.

## more than one valid answer

**builds on:** world, perspective, in "approach".

most problems in school have one right answer, waiting at the back of the book.
many real ones don't: several answers are valid, depending on what's wanted,
and the work is choosing between them, and saying why. this is the docs' idea
of more than one perspective, and of worlds (see [the approach](approach.md)),
from the side of teaching. it is taught, in design, engineering, writing and
law, but mostly implicitly, without saying that this is what's being learned.

**the case against.** beginners need problems with clear answers to build on,
and "it depends" can become a way of never being wrong. so open problems come
alongside the forms and the clear cases, not instead of them.

## teach the meta

say out loud what's usually left implicit: how learning works, how school
works and where it falls short, what abstraction is, why some problems have
several answers, and the mechanics of critical thought. much of this is
learned eventually, by those who go far enough, but it's rarely named, so most
people pick up the procedures without the thinking behind them.

_from memory_: the unstated lessons of school have a name, the **hidden
curriculum** (Philip Jackson, in the 1960s), and thinking about one's own
thinking is **metacognition** (John Flavell). the evidence leans towards
teaching both explicitly: explicit teaching of metacognition and critical
thinking seems to work, and works best when it's both explicit and embedded in
a subject, rather than taught as a separate course.

**a view, not a finding.** much of early schooling, and parts of later
schooling, is rote and shallow. that has its place, but the mechanics of deep
critical thought end up missing for much of the population, and that has
effects well beyond school, socially and otherwise. that's the view behind this
idea; these docs don't show it.

**in these docs.** the meta domain is this idea applied to one project: it
says how the docs work, why, and where they fall short ("the case against",
and "open to challenge", in [the approach](approach.md)).

**the case against.** young learners need something to think about before they
think about thinking, so the meta works best inside subjects, not beside them:
both sides at once, again. time in school is scarce. and a lesson about
learning can be as inert as any other, if it's taught as one more procedure.

## a thread of its own

**builds on:** home, framing, in "documents".

beyond saying the meta out loud inside other subjects, it could have a thread
of its own, beside mathematics, science and language: abstraction, modelling,
semantics, learning how to learn, and how things are known. it would work like
any topic that cuts across others: a home, the thread's own classes, where the
ideas are taught as themselves, and framings in every other subject, where
they're met in the noise. either alone falls short in the usual ways: the home
alone risks being inert, and the framings alone stay implicit.

_from memory_, it has precedents: the medieval trivium (grammar, logic and
rhetoric), taught before the subjects of the quadrivium; Dorothy Sayers's
essay "The Lost Tools of Learning" (1947), which argued for reviving it as
tools for learning; theory of knowledge, a required course in the
International Baccalaureate; philosophy for children (Matthew Lipman); and
computational thinking (Jeannette Wing), for abstraction.

this repository has the same shape: the meta domain is the home, and the
strand domain carries framings of it.

**the case against.** the timetable is already full, few teachers are trained
for it, and the evidence for stand-alone thinking courses is mixed: the
stronger results come from embedding, which is why the framings matter as much
as the home. some of this may be easier now (see "AI in teaching", in
[ai](ai.md)).

## a thread of one's own

each learner chooses something they care about, and keeps coming back to it: a
sport, an instrument, a game, a machine, a question. what they're learning in
their other classes is then related to it, as they go: the mathematics in it,
the physics, the history, the abstractions. it's both sides at once, with the
noisy domain chosen by the learner, so it's one they want to understand.

this repository is one: it grew out of an interest in rhythm and evenly spread
patterns, and the mathematics, modelling and semantics in it were worked out
through that interest.

**the case against.** interests change, and some learners don't have one yet;
a thread chosen too early can narrow what's explored. and relating every
subject to each learner's interest is more than one teacher can do for a whole
class, which is where AI may help (see "AI in teaching", in [ai](ai.md)).

## questions, taught

this is a framing of "questions before answers" (see
[the approach](approach.md)), from the side of teaching. schools mostly reward
answers, and treat a question as a sign of not knowing. but a good question
takes understanding: knowing the shape of what you don't know. asking can be
taught directly: _from memory_, the question formulation technique (Dan
Rothstein and Luz Santana) has learners produce, sort and sharpen their own
questions before anything is answered. it fits the rest of this chapter, too:
interleaving starts every problem with a question, "which tool is this?", and
the meta thread is, in large part, a thread of questions about how we know.

## seen from elsewhere

- pedagogy, from AI, and AI in teaching: in [ai](ai.md)

## related

_from memory_: progressive disclosure, in design; prerequisite graphs and
spiral curricula, in teaching; worked examples and contrasting cases, in the
study of learning; instrumental and relational understanding (Richard Skemp);
the "deductivist" style that hides how mathematics is found, and the
"heuristic" style that shows it (Imre Lakatos, *Proofs and Refutations*); Paul
Lockhart's *A Mathematician's Lament*; George Pólya's *How to Solve It*; formal
discipline and transfer of learning; habits of mind, as a way to organize
what's taught; inert knowledge (Alfred North Whitehead); realistic mathematics
education and guided reinvention (Hans Freudenthal); "Mathland", from Seymour
Papert's *Mindstorms*; anchored instruction; writing across the curriculum;
analogical encoding, where comparing two cases that share a structure shows the
structure (Dedre Gentner; Mary Gick and Keith Holyoak); "hugging" and
"bridging", in teaching for transfer (David Perkins and Gavriel Salomon);
cognitive flexibility theory (Rand Spiro); experts sorting problems by deep
structure rather than surface features (Michelene Chi and others); cognitive
load (John Sweller); concreteness fading; interleaved practice (Doug Rohrer and
others) and desirable difficulties (Robert Bjork); ill-structured problems
(Herbert Simon; David Jonassen) and wicked problems (Horst Rittel and Melvin
Webber); the hidden curriculum (Philip Jackson); metacognition (John Flavell);
explicit teaching of critical thinking (Philip Abrami and others);
project-based learning; the development of interest (Suzanne Hidi and K. Ann
Renninger); self-determination theory, on autonomy, competence and relatedness
(Edward Deci and Richard Ryan); constructionism, and "hard fun" (Seymour
Papert).