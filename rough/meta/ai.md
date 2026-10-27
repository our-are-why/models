# ai

**in short.** AI as a reader of these docs, and as a collaborator in debugging
them: what makes the docs loadable by a model, how to ask one for help, what
to trust in what it says back, what teaching looks like when the reader is an
AI, AI in teaching, where it may let a teacher be a shepherd rather than the
source of every piece of expertise, and questions, now that answers are
cheap.

the concepts here are listed, with stable IDs, in
[concepts.md](../../models/concepts.md).

## AI as a reader

the docs are written for people first. much of what helps people also helps a
model load the perspective, and some of it matters more for a model:

- **explicit semantics**: definitions say what a thing is and what it isn't, so
  a model doesn't have to infer them from use
- **stable IDs**: a concept can be cited exactly, as C016, whatever it's called
  at the time
- **dependency order**: no concept is used before it's defined, so a model
  reading from the top never has to guess a meaning
- **status labels**: a model can tell checked results from recalled ones, and
  pass that on
- **a keyboard form**: the notation has a plain-text form, `x` and `.`,
  alongside the display shapes, so it survives being copied between tools

## AI as a debugger

part of the purpose of the docs is to have the thinking in them checked (see
[personal](personal.md)). a model can help with that:

- point it at the "case against" sections and "open to challenge", in the
  approach, and ask where the reasoning fails
- ask it to recompute the worked examples, and to check the claims marked
  _from memory_
- ask it which world it's assuming before it answers, so its answer can be
  read in the right setting (see "worlds", in "approach")

**the case against.** a model can agree too readily, or find flaws that aren't
there, and its own recall is fallible. what it contributes takes the same
labels as anything else: its recall is _from memory_ until checked, and its
calculations are checked by running them, not by trusting the answer.

## pedagogy, from AI

this is a framing of pedagogy (see [pedagogy](pedagogy.md)), from the
side of a reader that's a model.

- **collisions matter more.** a model brings in every meaning a word has in
  what it learned from. a word that collides with another field's meaning
  pulls that meaning in, often without saying so. the docs' care with names
  (null, fluid, function) helps a model as much as a person
- **plain words matter less, contrast matters more.** a model usually knows
  the established terms, so a plain word beside one adds less. what it lacks is
  the docs' own boundaries: what each thing here isn't. saying that out loud
  blocks a plausible but wrong reading
- **order still matters.** a model reading out of order fills gaps with the
  most common meaning it knows, which is exactly the meaning the docs may be
  setting aside

**the case against.** writing for models could bend the docs away from people:
denser, more formal, more hedged. the aim is that a model is helped by the
same clarity that helps a person, not by writing for it separately.

## AI in teaching

this is another framing of pedagogy, from AI's side. much of what pedagogy
proposes asks more of teachers than they can give: framings of mathematics in
every subject, a meta thread few are trained for, and each learner's own
thread, related to everything they're learning. with AI to hand, a teacher no
longer has to be the source of every piece of expertise. they can be a
**shepherd**: guiding, choosing what to look at next, and judging what's been
understood, while AI ties ideas from one subject into the concrete setting of
another, a learner's own interest included.

a general-purpose model is a poor fit for this as it stands. it's shaped to be
helpful by answering, and a learner is often helped most by not being
answered: by a question back, a different angle, another perspective, or
encouragement to keep going. so a model meant for teaching probably needs a
layer of its own, through fine-tuning or other training, aimed at taking part
in the thinking rather than doing it: collaborating, and offering angles,
instead of handing over results.

**the case against.** AI is fallible, and a learner may not catch its
mistakes. it can do the thinking the learner was meant to do, which defeats
the point of teaching thought. and access to it isn't even. so AI's part is to
connect and explain, the learner's is to think, and the shepherd's is to make
sure the second still happens. _from memory_: one-to-one tutoring has long been
known to help a great deal (Benjamin Bloom's "two sigma" finding, 1984), which
is the hope behind AI tutors; the evidence on AI tutors themselves is still
new.

## questions, from AI

this is a framing of "questions before answers" (see
[the approach](approach.md)), from AI's side. a model will answer almost
anything, at once and fluently, so answers have become cheap. what stays scarce
is the question: what to ask, how to frame it, and what to doubt in what comes
back. a well-framed question also guards against a model's failure mode, since
a fluent answer to a badly framed question is still wrong. and a model meant
for teaching, as above, should often answer with a question.

## related

_from memory_: retrieval and grounding, in AI, where a model is given the
source text to answer from rather than its recall; documentation written to
be read by tools as well as people; the teacher as "guide on the side" rather
than "sage on the stage" (Alison King); Bloom's two sigma problem; Socratic
questioning, which teaches by asking rather than telling.
