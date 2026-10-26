# ai

**in short.** AI as a reader of these docs, and as a collaborator in debugging
them: what makes the docs loadable by a model, how to ask one for help, what
to trust in what it says back, and what teaching looks like when the reader
is an AI.

the concepts here are listed, with stable IDs, in
[concepts.md](../concepts.md).

## AI as a reader

the docs are written for people first. much of what helps people also helps a
model load the perspective, and some of it matters more for a model:

- **explicit semantics**: definitions say what a thing is and what it isn't,
  so a model doesn't have to infer them from use
- **stable IDs**: a concept can be cited exactly, as C016, whatever it's called
  at the time
- **dependency order**: no concept is used before it's defined, so a model
  reading from the top never has to guess a meaning
- **status labels**: a model can tell checked results from recalled ones, and
  pass that on
- **a typed form**: the notation has a plain-text form, `x` and `.`, alongside
  the display shapes, so it survives being copied between tools

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

## related

_from memory_: retrieval and grounding, in AI, where a model is given the
source text to answer from rather than its recall; documentation written to
be read by tools as well as people.
