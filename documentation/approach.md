# approach

**in short.** the way of modelling behind these docs, written down so that a
reader can load it, test it, and argue with it. it isn't specific to spacers:
it's meant to hold for every domain documented here. it's a stance, not a
doctrine, and it's still forming: each idea comes with why it's chosen, where it
shows up, and the case against it.

**builds on:** nothing. the domain chapters don't depend on agreeing with it,
but much of their shape comes from it.

## how to read this

each idea has the same five parts:

- **what**: the idea itself
- **why**: what it's for
- **where**: where it shows up so far, mostly in the spacer chapters
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

for spacers, a world settles:

- which perspective on the states it takes: true/null or true/false
- whether fluid is abstract or concrete, and if concrete, hierarchical or a
  sibling
- whether a committed spacer can melt back into a fluid one
- what identity sets aside, or adds

by default, the spacer chapters take the asymmetric perspective on the states,
keep commitment one-way, and have no melt.

**why.** some questions have no answer in general. whether a circle can become
a fluid spacer again depends on whether its shape matters, and that depends on
what it's used for: a clock face is a circle in any world that cares about
time. rather than pick one answer and call it the truth, the docs name the
choice, give a default, and leave the rest to the world. so whoever uses the
model should know their world, and align with its semantics.

**where.** "what fluid is", "true and null" and "worlds", in the spacer basics;
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

## defaults and overrides

**what.** where a choice has to be made, the docs make one, call it the
default, and say how to override it. the default is usually the strictest or
simplest option, so that an override loosens it on purpose, not by accident.

**why.** a model with no defaults can't be used until everything is settled; a
model with fixed answers breaks in the worlds it didn't foresee.

**where.** identity: the default is the strictest comparison, and a use that
loosens it should say what it sets aside. stacks: a spacer is framed as
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
spacer basics; cascades written top-down or bottom-up, in structures; a row of
amounts and a cascade as two views of one structure, in functions (levels and
depths).

**the case against.** too many perspectives make a model slippery: a reader
can't tell what's being claimed. so each perspective gets a name, and one of
them is used by default.

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

**why.** it keeps structures simple and general: the same spacer can come from
a careful rule or a coin toss, and nothing in it shows which.

**where.** any arrangement, in the spacer basics; generators, in dynamics; a
flattened cascade, which doesn't show that it was chosen in steps.

**the case against.** some uses need the origin to travel with the object.
that's allowed, but as something a world adds, not as part of the structure.

**related.** syntax and semantics; data and metadata.

## mechanics, derived results and meaning

**what.** three layers are kept apart: the mechanics of working with structures
(frames and stacks), the results derived from them (weights and scores), and
meaning (what a pattern of weights says). each can be talked about without the
others.

**why.** mixing them is how definitions go wrong: defining a family of spacers
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
shapes share, in the spacer basics; zero is named, though it isn't a spacer.

**the case against.** some things really are undecided, and calling them
adaptable would hide that. where both readings are real, the docs keep both:
fluid can be abstract or concrete.

**related.** nothing close comes to mind as an established principle; it's
near the writing advice to say what is, rather than what isn't.

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

**where.** functions, which never change a spacer in place; labels, in
notation; commitment, in the spacer basics.

**the case against.** working this way makes many values where one changing
value would do, which can be costly for large structures in software. that's
a question for implementations, and doesn't change the model.

**related.** immutability and persistent data structures, in functional
programming.

## naming

**what.** plain words first. name a thing after what it lets you do. keep
collisions with other meanings low, pragmatically: no word is free of them, so
it's a judgement, not a ban. pair a term with an established or alternative
name at first use (arrangement/distribution). don't take a precise term from
another field and bend it.

**why.** names are where readers bring in assumptions, and a name that collides
brings in the wrong ones.

**where.** why not "binary string", in notation; functions rather than
operations, in functions; null, fluid and world; the notes on "cell" and
"weight".

**the case against.** plain words carry everyday meanings that technical words
don't. and every renaming (slot to cell, filled to true, neutral to fluid)
costs readers who learned the old name; [concepts.md](concepts.md) keeps
former names for that reason.

**related.** the ubiquitous language of domain-driven design; affordance, in
design and psychology.

## honesty about status

**what.** say how something is known: established elsewhere, worked out here,
checked by computation, or recalled from memory and not yet checked. defer
things on purpose, and say so.

**why.** a reader can only debug what they can see the basis of.

**where.** throughout: "from memory" notes, checks by computation (the
threshold results, the pair of spacers with the same weights), and deferred
topics (more dimensions).

**the case against.** labels add noise, and "from memory" can read as false
modesty, or as an excuse. they should stay short, and be replaced as things
get checked.

**related.** levels of evidence, in science; provenance, in data.

## open to challenge

where the approach is least sure of itself:

- whether "it depends on the world" is used honestly, or as an escape hatch
- whether the asymmetric default for the states is a bias, carried in by the
  name "spacer"
- whether essence and convention need a third category, for perspectives
- where the line between a primitive and a composite should fall
