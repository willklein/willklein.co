---
theme: default
title: Design System Tools Every Developer Should Use - Will Klein
info: |
  React Day Berlin proposed talk, draft deck
  Cue-card style: slides are prompts, not scripts. Full talking points in speaker notes.
class: text-center
drawings:
  enabled: false
transition: fade
mdc: true
---

# Design System Tools

# Every Developer Should Use

Will Klein

<!--
There are people building design systems.

And there are people building products, hopefully using a design system.

There's probably more of us who have done the latter though.

And as someone who's lived in both worlds, I'd like to take all the best things from working in a design system, and introduce them to everyone else. Most of all, there are tools we consider standard in design systems that are surprisingly effective for everyday UI development.
-->

---
class: text-center
---

# "That's a design<br>system thing."

<!--
When I talk with non-design system devs about tools like Storybook, visual testing, and accessibility testing,

I often hear them say: that's a design system thing.

They MIGHT be doing accessibility testing, but the for the most part, they're missing out.
-->

---
layout: section
---

# 🎥 DEMO

## build → break → catch

<!--
Just in case anyone's not familiar with Storybook, let me share a quick demo. I'll also make a UI change and share an example of how my workflow benefits from having visual testing setup on a product page.

Demo 1:
Open Storybook with our UI components, as well as product pages/screens.
Make a proposed design hange: changing a card heading color from black to purple.

"This looks cool, so I pushed it to a branch and let my CI do it's thing."

Show the visual tests that fail - and spot the color contrast accessibility issue introduced in dark-mode.

Note: goal of this demo is to introduce Storybook and also use it from the perspective of a product developer.
-->

---

# Reframe

- Not just for design systems
- UI-oriented dev tools

<!--
Design system teams adopted Storybook, along with visual testing & a11y checks, because inconsistency costs them the most.
-->

---
layout: statement
---

# Same Challenge.<br>No design system required.

<!--
Anyone building UI has the same challenge though: to ship UI that renders and behaves the way we expect.

In fact, the stakes are even higher - this is what your users experience.

And often, you're building UI components that deserve the same attention as the ones in your design system.
-->

---

# Product UI has its own components

- components you built, bespoke to your app
- design system components you styled or themed
- components from open source libraries
- views/pages composed of everything

<!--
Sometimes you're using off-the-shelf design system components. SOME of the time.

In every product I've worked on, there's a bunch of other UI components we have where things can go wrong.

And where we can improve the DX of building them.

Note: devs generally don't realize how much component development they have in their project, and it's usually not treated with the same attention as design system components. Need a good background image to drive this home. May split into several slides with quick examples, but need to check time across the entire talk.
-->

---
layout: section
---

# Habit One

## Story-driven development

<!--
Let's introduce the first best practice that we can steal from design systems.
-->

---

# Write the story first

<!--
Write the story as part of building the component, not documentation after the fact.

Note: this and the next couple slides are quick beats, so we can jump into a demo proving out the workflow.
-->

---

# Forces the hard states

- Loading
- Error
- Empty
- Long text
- RTL

<!--
These states exist before shipping, not discovered in prod.
-->

---

# Storybook == dev environment

- Isolate our components
- Wire up state independent of app logic - or clicking around to set it up

<!--
Fast iteration on one component in isolation instead of navigating the full app to reach a state.
-->

---
layout: section
---

# 🎥 DEMO

## Create a story for a new UI feature

<!--
Note: still deciding what's going to be a good demo here, but we'll be prompting our agent to use Storybook's MCP capabilities to create some new stories for a new feature (TBD). I might move this slide to the beginning of the Story-driven Developemnt section, so it's running in the background while I talk through the benefits.
-->

---
layout: two-cols
layoutClass: gap-8
---

# Before AI

- Type every story
- Setting up UI state manually
- Easy to skip

::right::

# After AI

- Draft in seconds
- Every scenario we need is ready to go
- It's done for us

<!--
We used to type every story by hand, but AI has changed that. In fact, I should say that I just ask my agent to setup Storybook in whatever app I'm building.

Major learning: tooling that was an optional chore is now a "no-brainer."

There's still the pressure to ship quickly. The funny thing is, spending a few minutes asking an agent to set this up will save us time.

And give us a full set of states based on our components' prop types.
-->

---
layout: section
---

# Habit Two

## Visual regression, by default

---

# Not DS-exclusive

- Chromatic
- Percy
- Applitools
- Any component

<!--
We can point these at any component, and even our pages and views.

Note: I'm most experienced with Chromatic and need to vet Percy and Applitools for quality in 2026. Worth mentioning there are different services. Also need to see if anyone is rolling their own testing service in CI; this is really not worth it but I'm going to look around.
-->

---

# Fast enough for product PRs

- Chromatic has TurboSnap
- Incremental diffing

<!--
Let's be honest about two potential obstacles.

CI can slow us down, and we need these checks to be fast. It can also be an incremental cost with usage-based pricing.

Chromatic introduced a feature called TurboSnap. It considers what's changed in git, and identifies in the dependency graph what components and stories could be affected. Then it selectively runs only the tests that matter.

This saves us time and cost. Note: check for similar features with Percy & Applitools.
-->

---
class: text-center
---

# "Does this look right?"

## subjective review → objective gate

<!--
In the past, we might have reviewed this with QA, or maybe even with our designer. We'd notice the larger brushstrokes, but easily miss small changes that we didn't intend to make.

Visual tests give us a complete check.
-->

---
layout: two-cols
layoutClass: gap-8
---

# Before AI

- DS components only
- Baselines = expensive
- Humans triage diffs

::right::

# After AI

- Any component in our UI
- Catches bugs introduced by AI (and us)
- Visual diff review > Code diff review

<!--
Note: Key Lesson

Before: reserved for shared/DS components, baseline setup and diff triage were expensive.

After: visual diffing is how you review AI-generated UI without reading every line of JSX. A diff gets approved/rejected in seconds; line-by-line review of generated code doesn't scale the same way. And it never caught the visual changes.
-->

---
layout: section
---

# 🎥 DEMO

## visual diff catches an AI regression

<!--
DEMO 3, ~45 sec. Show a Chromatic/visual diff flagging a change an AI agent introduced.
-->

---
layout: section
---

# Habit Three

## Accessibility, continuously

---

# axe-core, every story

- Product or DS
- Seconds, not once a year

<!--
The addon runs on every story you write. Bugs caught in seconds instead of during a once-a-year audit.

We also catch them during development.

Demo: show the a11y addon panel and how it tells us what's wrong while we develop. Then show how this comes up in a CI example (PR fails a check).

Note: consider adding talking point around what axe covers and what it doesn't. I want to give people an accurate understanding of what automated checks do (really well) and where human a11y expertise still matters.
-->

---

# Product screens need it most

- Least likely
- To get an audit

<!--
One-off product screens are exactly the surfaces least likely to ever get a dedicated a11y review otherwise.
-->

---
layout: two-cols
layoutClass: gap-8
---

# Before AI

- Periodic audits
- Manual tab-through
- Needed a specialist

::right::

# After AI

- AI skips basics _more_
- Missing focus states
- Now non-negotiable

<!--
Note: Key Lesson

AI-generated components skip a11y basics more often than hand-written ones. Their training data historically over-represents demo code that never worried about this.

What used to be "nice to have for compliance" is now required to keep AI-authored UI honest.
-->

---
layout: section
---

# Habit Four

## Build on accessible-by-default primitives

---

# The foundation

- shadcn/ui
- Radix UI
- Base UI
- React Aria

<!--
When we do need to build our own components, we don't need to start from scratch.

We can use headless components, style them to fit our design, and compose them into custom components when we need to. Inherit correct focus management, keyboard nav, ARIA wiring instead of reinventing it.

Note: naming these from memory but need to check that all are still active/preferred and see if I'm missing something else
-->

---
layout: two-cols
layoutClass: gap-8
---

# Before AI

- Components built from scratch
- Or copied/stolen from another library, without their tests
- Often incomplete

::right::

# After AI

- AI makes a11y mistakes
- "Modal from scratch" = wrong
- Point it at a primitive instead

<!--
Key lesson learned:
AI models are trained on lots of "here's a modal from scratch" tutorial code that gets ARIA wrong.

An agent asked to build a modal with no guardrails will confidently reproduce the broken pattern.

The fix isn't a better prompt; it's an architectural constraint.Don't let the agent invent ARIA, let it wire up a primitive that already got it right.

Note: I'm not sure I need or want every Before/After AI. I have them here right now to test out. Talking points from them are definitely warranted, but I'm still evaluating the best way to present the content.
-->

---
layout: section
---

# The AI Factor

## why this matters more than ever

<!--
Give this section the most weight
-->

---
class: text-center
---

# AI defaults to generic

## unless something checks its work

<!--
AI coding models generate output by predicting the most statistically likely continuation based on their training data.

They don't exercise design judgment or checking against a quality bar.

A component-oriented development workflow isn't just for our benefit. It's really effective for guiding AI to creating purpose-built UI, with quality.
-->

---

# Not new habits

- Same 4 habits
- Higher stakes now

<!--
These aren't new ideas, but ones I want you to steal from design systems.

they're existing dev-tool discipline that AI raised the stakes on. Don't let this feel like a topic pivot.
-->

---
layout: section
---

# Storybook MCP

## agents that can see your components

---

# What it gives an agent

- Component docs
- Props + examples
- Reuse over reinvention

<!--
Gives agents (Claude Code, Cursor, Copilot, Gemini CLI) direct visibility into whatever
components already exist in your codebase.

AI sometimes does handles this OK, but with MCP tools, we're giving it clear directions.

And saving a bit on tokens.
-->

---
class: text-center
---

# generate → test → fix → re-run

## the self-healing loop

<!--
Note: Walk through the loop verbally before the demo.
-->

---
layout: section
---

# 🎥 DEMO

## the self-healing loop, live

<!--
Key demo (60-90 seconds)

Give an agent a task → uses MCP to discover an existing component → generates a story →
fails a test → reads the failure → fixes → re-runs.

Note: I've tripped over this happening and need to think of a good example for this. I'll have a pre-baked example ready to take out of the oven in case AI doesn't cooperate.
-->

---
layout: statement
---

# Better guardrails.<br>Not better prompts.

<!--
We need better guardrails.

Not better prompts.

The same tooling investment that makes our design system trustworthy for humans
is what makes it safe to hand to an agent.
-->

---

# What changed, in one slide

- Stories: type → review
- Visual: DS-only → everywhere
- A11y: infrequent → continuous
- Primitives: from scratch → composition
- Discovery: reinvent → reuse

---
layout: section
---

# Install This Today

---

# The starter kit

- Storybook + Controls
- Chromatic / TurboSnap
- axe-core addon
- Radix or React Aria
- Storybook MCP

<!--
Here's the cheatsheet. Only one of these is opinionated (Chromatic). By the way, I do NOT work there!
-->

---
class: text-center
---

# No design system required.

<!--

No design system required... to use these tools. I hope you have a design system!

But seriously, the quality of UI in the age of AI, is in my opinion, seeing a dip.

While the stakes have never been higher. With agents, we're shipping more, and faster, than ever.

With the right tools though, we can ship _everything_ with more quality than ever.

-->

---
layout: center
class: text-center
---

# Thanks!

Will Klein
[willklein.co](https://www.willklein.co)

<!--
Note: QR code and URL for slides to be added. Also lots of images added as backgrounds like I usually do.
-->
