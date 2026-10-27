# semiotics

**in short.** the docs work at three layers, named by semiotics, the study of
signs: syntax, how things are written; semantics, what they mean; and
pragmatics, how meaning depends on where and how they're used. this chapter
says which parts of the docs sit at which layer, so that a question can be
asked at the right one.

the concepts here are listed, with stable IDs, in
[concepts.md](../concepts.md).

## three layers

**builds on:** world, in "approach".

the split comes from semiotics (_from memory_: Charles Morris named the three
in the 1930s):

- **syntax**: how signs relate to each other. what counts as well written,
  apart from what it means
- **semantics**: how signs relate to what they stand for. what a well-written
  thing means
- **pragmatics**: how signs relate to the people and settings that use them.
  what a meaning amounts to in a given use

linguistics uses the same three words for layers of a language. here they're
meant in the general sense, for any system of signs, a notation included.

## where each layer lives

| layer | in the strand domain |
| --- | --- |
| syntax | notation: the typed and display forms, edges, labels, descriptions, the spacing rule, escaping |
| semantics | basics, measures, structures and functions: what a strand, a scope, a layer or a function is |
| pragmatics | worlds: which perspective on the states, abstract or fluid, whether melt exists, what identity sets aside |

some parts sit across layers, on purpose:

- **edges** are syntax, but they carry a semantic choice: `)…(` writes down
  that a strand is circular
- **rule 4** of the symbol rules, minimize collisions, is pragmatic: what
  collides depends on where the notation is read
- **identity** is semantic in its default, and pragmatic in which comparison a
  use takes

## why the layers matter

a question asked at the wrong layer gets a confusing answer:

- is `)x..(` the same as `<x..>`? as written, no: they're different strings. by
  meaning, not by default, since their readings differ, but one converts to
  the other. in use, it depends on the world, which may set the reading aside
- can a circle melt back into a fluid strand? that isn't a question of meaning
  in general. it's pragmatic, and a world settles it
- a `|` that breaks a table in Markdown is a syntax problem, fixed by escaping,
  never by changing what the notation means

keeping the layers apart lets each change without disturbing the others. new
symbols don't change meaning (see "essence and convention", in "approach"),
and a new world doesn't change a definition.

## the case against

three layers is a simplification. in practice they lean on each other: the
edges carry meaning into the syntax, as above, and pragmatics can swallow
everything else ("it depends on the use"). the layers are a tool for asking
better questions, not walls.

## related

_from memory_: semiotics, from Charles Sanders Peirce and Ferdinand de Saussure
on; the syntax and semantics of programming languages, where semantics is
often split again into static (what can be checked before running) and
dynamic (what happens when it runs); and linguistics, where phonology and
morphology sit below syntax.
