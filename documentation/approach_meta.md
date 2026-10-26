# approach

**in short.** the way of modelling behind these docs, written down so that a
reader can load it, test it, and argue with it. it isn't specific to strands:
it's meant to hold for every domain documented here. it's a stance, not a
doctrine, and it's still forming: each idea comes with why it's chosen, where it
shows up, and the case against it.

**builds on:** nothing. the domain chapters don't depend on agreeing with it,
but much of their shape comes from it.

this is the modelling part of the meta domain, which is about how every domain
here is modelled and written down; why it's done at all is in
[personal](personal_meta.md). the concepts here are listed, with stable
IDs, in [concepts.md](concepts.md).

## how to read this

each idea has the same five parts:

- **what**: the idea itself
- **why**: what it's for
- **where**: where it shows up so far, mostly in the strand chapters
- **the case against**: its tensions and trade-offs, and what the alternative
  would be
- **related**: established ideas elsewhere that come close. they're noted from
  memory, as handles, not as authorities: being close to something established
  doesn't make an idea right

disagreement is welcome. where an idea here seems wrong, its "case against" is
the place to start, and the last section lists where the approach is least
sure of itself.

## worlds

**what.** the docs give defaults, and a **world**, or semantic world, settles
what they leave open. a world is the setting something is used in, with its
own semantics: what its parts mean, which moves make sense, and what counts as
the same. one structure can mean different things in different worlds, and a
move that's sound in one can be meaningless in another.

for strands, a world settles:

- which perspective on the states it takes: true/null or true/false
- whether fluid is abstract or concrete, and if concrete, hierarchical or a
  sibling
- whether a committed strand can melt back into a fluid one
- what identity sets aside, or adds

by default, the strand chapters take the asymmetric perspective on the states,
keep commitment one-way, and have no melt.

**why.** some questions have no answer in general. whether a circle can become
a fluid strand again depends on whether its shape matters, and that depends on
what it's used for: a clock face is a circle in any world that cares about
time. rather than pick one answer and call it the truth, the docs name the
choice, give a default, and leave the rest to the world. so whoever uses the
model should know their world, and align with its semantics.

**where.** "what fluid is", "true and null" and "worlds", in the strand basics;
melt and commitment, in functions; the default and its overrides, in identity.

**the case against.** worlds can become an escape hatch: if every conflict is
answered with "it depends on the world", the model can never be wrong. the
guard is that a world declares its choices up front, from the listed options,
and keeps them: it can't pick one after seeing the problem. there's a cost
too: every open choice multiplies the worlds a reader has to keep in mind, so
the defaults should cover the common case, and the options should stay few.

**related.** possible worlds in modal logic, where a statement can be true in
one world and false in another; model theory, where one set of axioms can have
many models; and the bounded context of domain-driven design, where a model's
terms keep their meaning within a stated boundary.

## structure follows use

**what.** organize for how things are used and made, not to mirror their
taxonomy. a thing is placed at the level where it's looked for, its basic
level, and its ancestry is stated in words rather than built into nesting: a
strand is a kind of discrete space, which is a kind of space, but it sits at
the top, not three folders down. structure is added once it's earned: a
subdomain starts as one file, and becomes a folder when it grows chapters. and
where it helps, one thing is reached from more than one place, the way a
database denormalizes a record for access (see "cross-cutting topics", in
[documents](documents.md)). the structure follows the use, not the other way
round.

**why.** a hierarchy mirrored exactly makes every path long, and fixes a
taxonomy before it's understood. placing things where they're used keeps the
common paths short, and leaves the taxonomy free to change.

**where.** the layout of these docs: the strand domain at the top, and the
meta subdomains as single files; a strand's ancestry, stated in its basics;
and, in the strand functions, collapse and flatten, which do the same to
chains of scopes and to cascades.

**the case against.** a flat layout hides a hierarchy that's really there: a
reader can't see how things relate by looking at the folders, so the ancestry
has to be written down, or it's lost. and use changes: what's flat today may
need structure tomorrow, and moving things has a cost.

**related.** basic-level categories, in cognitive science (Eleanor Rosch);
denormalization, in databases; the facade, in software; "pave the cowpaths", in
design, which builds paths where people already walk; and, in software, adding
structure only once it's needed (YAGNI, the rule of three).

## defaults and overrides

**what.** where a choice has to be made, the docs make one, call it the
default, and say how to override it. the default is usually the strictest or
simplest option, so that an override loosens it on purpose, not by accident.

**why.** a model with no defaults can't be used until everything is settled; a
model with fixed answers breaks in the worlds it didn't foresee.

**where.** identity: the default is the strictest comparison, and a use that
loosens it should say what it sets aside. stacks: a strand is framed as
written. worlds: the defaults for the states, fluid and melt.

**the case against.** a default looks like the truth, whatever the docs say.
readers may take the strict identity, or the asymmetric states, as the real
answer and the rest as exceptions. calling a default a default, every time,
is the only guard.

**related.** convention over configuration, in software; default reasoning, in
logic.

## more than one perspective

**what.** some things can be seen in more than one way, each valid, with none
the hidden truth behind the others. the docs name the perspectives side by
side, and say which one the running text uses, and why.

**why.** forcing one perspective loses what the others see. the asymmetric view
of the states is what makes spacing meaningful; the symmetric view is what
makes logic work. both are needed.

**where.** true/null and true/false, and fluid as abstract or concrete, in the
strand basics; cascades written top-down or bottom-up, in structures; a row of
amounts and a cascade as two views of one structure, in functions (levels and
depths).

**the case against.** too many perspectives make a model slippery: a reader
can't tell what's being claimed. so each perspective gets a name, and one of
them is used by default.

the docs apply the same idea to themselves: a topic that cuts across domains
has one home and several framings (see "cross-cutting topics", in
"documents").

**related.** figure and ground, in perception; duality, in mathematics, where
one structure has two descriptions that carry the same information.

## essence and convention

**what.** some things about an object belong to it; others are choices made to
write it down or talk about it. the test: imagine two people describing the
same thing differently. what they still agree on is essence/semantics; what
they don't is convention.

**why.** without the line, conventions harden into facts: "cell 0" starts to
feel like part of a circle.

**where.** the essence and convention section, in identity; the symbol rules,
in notation, where any symbols will do; + as a convention, in measures.

**the case against.** the line isn't always sharp. which state is "the thing"
turned out to be neither essence nor convention, but a perspective. a third
category may be needed, rather than forcing everything into two.

**related.** essence and accident, in classical philosophy; invariants, in
mathematics and physics: what stays the same when the coordinates change.

## the device and its meaning

**what.** a structure carries no record of where it came from, or of what it
means. meaning lives outside it, in what's known about its origin and its use.

**why.** it keeps structures simple and general: the same strand can come from
a careful rule or a coin toss, and nothing in it shows which.

**where.** any arrangement, in the strand basics; generators, in dynamics; a
flattened cascade, which doesn't show that it was chosen in steps.

**the case against.** some uses need the origin to travel with the object.
that's allowed, but as something a world adds, not as part of the structure.

**related.** syntax and semantics; data and metadata.

## mechanics, derived results and meaning

**what.** three layers are kept apart: the mechanics of working with structures
(frames and stacks), the results derived from them (weights and scores), and
meaning (what a pattern of weights says). each can be talked about without the
others.

**why.** mixing them is how definitions go wrong: defining a family of strands
by how they're framed confuses a mechanism with what it's used to show.

**where.** collections, stacks and weights, in structures.

**the case against.** the layers leak: a derived result can carry structure of
its own, which starts to look like meaning. the docs name that (weak
emergence) rather than force a clean line.

**related.** levels of abstraction, in software; the difference between a
model, what's computed from it, and how it's interpreted.

## positive definitions

**what.** define a thing by what it is, not by what it lacks, or hasn't yet
become.

**why.** a definition by lack invites the reader to fill the gap with a guess:
"null" read as "unknown", "fluid" as "undecided".

**where.** null means absence, not unknown, and fluid has everything the two
shapes share, in the strand basics; zero is named, though it isn't a strand.

**the case against.** some things really are undecided, and calling them
adaptable would hide that. where both readings are real, the docs keep both:
fluid can be abstract or concrete.

**related.** nothing close comes to mind as an established principle; it's
near the writing advice to say what is, rather than what isn't.

## telling things apart

**what.** define a thing, then mark its boundary: say what it's easy to mistake
it for, and how it differs. the nearest neighbours matter most, since they're
the likeliest mistakes.

**why.** a definition says what's inside; a boundary says what's outside. a
reader needs both, and a model that can't say what something isn't hasn't
pinned it down.

**where.** why not "binary string", in notation; layers aren't scopes, in
structures; zero isn't the all-null strand, in the strand basics; fitting
isn't identity, in identity; functions rather than operations, in functions.

**the case against.** contrasts can multiply without end, and a thing defined
mostly by what it isn't stays vague. so a contrast comes after a positive
definition, never instead of one (see "positive definitions", above), and only
with the neighbours a reader is likely to confuse it with.

**related.** definition by genus and difference, in classical logic: name the
kind, then what sets this one apart; contrast sets, in teaching.

## tailoring and primitives

**what.** each function does one kind of thing to one kind of thing. when an
idea means different things for different kinds, they get different
functions, rather than one that behaves differently depending on what it's
given. a primitive does one basic thing; a composite is defined by primitives,
and named because it's useful.

**why.** a function that quietly changes with its input hides decisions.
separate functions put them in the open.

**where.** functions: reverse and mirror, join and splice, unwind and wind, and
the split into primitives and named composites.

**the case against.** more functions to learn, some of them close to each
other. and "one basic thing" is a judgement, not a test: it isn't minimality,
and two people may draw the line differently. a primitive that can also be
built from others is kept, and the other route becomes a cross-check.

**related.** the single-responsibility principle, in software; the opposite of
duck typing; well-typed functions, in functional programming.

## nothing changes in place

**what.** structures don't change: functions give new ones, and a label is
defined once. when information is lost, a named function loses it, on purpose.

**why.** a change that can't be seen can't be reasoned about. naming each loss
(detach forgets the context, flatten the layers, melt the shape) keeps the
losses visible.

**where.** functions, which never change a strand in place; labels, in
notation; commitment, in the strand basics.

**the case against.** working this way makes many values where one changing
value would do, which can be costly for large structures in software. that's
a question for implementations, and doesn't change the model.

**related.** immutability and persistent data structures, in functional
programming.

## reduce on purpose

**what.** forms that are equal as values aren't interchangeable as meanings.
`- 3`, taking three away, and `+ -3`, adding a debt of three, give the same
result, but they say different things about what's happening. reducing an
expression to its simplest form is a comparison that sets that meaning aside.
it's useful on purpose: simple forms are easy to compare and to calculate
with. done by default, and taken as the truth, it loses the reasons the form
had. so the meaningful form is kept as the source, a reduced form is taken for
a use, and what it sets aside is named. the noisiest form isn't the answer
either: the aim is the form that matches the meaning.

**why.** a reduced form can't be un-reduced: the meaning it dropped isn't in it
anymore. in code, the same loss turns up later as a bug: a refactor that merges
two things which only looked alike, or drops a check whose reason was never
written down.

**where.** identity, where every comparison says what it sets aside; the strand
functions, where every loss has a name (detach, flatten, melt); and null, kept
apart from false although the two could be reduced to one.

**the case against.** keeping every form makes things heavier: more to read,
more to carry. the meaningful form is a judgement, and people can disagree
about what the meaning is. and sometimes the mechanics are the point: reduced
forms are what make calculation possible, and a purely mechanical view of
mathematics is valid too.

**related.** canonical and normal forms, in mathematics; Chesterton's fence,
don't remove what you don't understand; "the wrong abstraction" (Sandi Metz),
since duplication is cheaper than merging things that only look alike;
primitive obsession and value objects, in software design.

**seen from elsewhere.** teaching the meaning, not only the mechanics, in
[pedagogy](pedagogy_meta.md).

## naming

**what.** plain words first. name a perspective after what it lets you do,
and a structure after what it is, neutrally, so that no perspective is built
into it: a strand read as things and the space between them is a spacer, but
the strand itself is named only for its shape. keep collisions with other
meanings low, pragmatically: no word is free of them, so
it's a judgement, not a ban. pair a term with an established or alternative
name at first use (arrangement/distribution). don't take a precise term from
another field and bend it.

**why.** names are where readers bring in assumptions, and a name that collides
brings in the wrong ones.

**where.** why not "binary string", in notation; strand rather than spacer,
for the structure; functions rather than operations, in functions; null, fluid
and world; the notes on "cell" and "weight".

**the case against.** plain words carry everyday meanings that technical words
don't. and every renaming (slot to cell, filled to true, neutral to fluid,
spacer to strand) costs readers who learned the old name;
[concepts.md](concepts.md) keeps former names for that reason.

**related.** the ubiquitous language of domain-driven design; affordance, in
design and psychology.

## honesty about status

**what.** say how something is known: established elsewhere, worked out here,
checked by computation, or recalled from memory and not yet checked. defer
things on purpose, and say so.

**why.** a reader can only debug what they can see the basis of.

**where.** "from memory" notes, in these meta chapters and in the rough notes;
checks by computation, in the rough notes (the threshold results, the pair of
strands with the same weights); deferred topics, in the strand basics (more
dimensions).

**the case against.** labels add noise, and "from memory" can read as false
modesty, or as an excuse. they should stay short, and be replaced as things
get checked.

**related.** levels of evidence, in science; provenance, in data.

## open to challenge

where the approach is least sure of itself:

- whether "it depends on the world" is used honestly, or as an escape hatch
- whether the asymmetric default for the states is a bias. the structure was
  renamed from spacer to strand partly for this reason, but the running text
  still takes the asymmetric perspective by default
- whether essence and convention need a third category, for perspectives
- where the line between a primitive and a composite should fall
