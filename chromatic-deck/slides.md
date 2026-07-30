---
theme: default
title: Developer-Facing Programs — Will Klein
info: |
  Chromatic Developer Experience Engineer
  Will Klein
class: text-center
drawings:
  enabled: false
transition: fade
mdc: true
---

# Developer-Facing Programs

Will Klein — Chromatic Developer Experience Engineer

<div class="pt-12 opacity-70">
Context · Audience · Objectives · Measurable Impact · Lessons Learned
</div>

---

# Three programs, three angles

<div class="grid grid-cols-3 gap-6 pt-8 text-sm">
<div>

### Design System Adoption

**Workday** · 2.5 years

Engineering + education

</div>
<div>

### React Denver

**2015–2022**

Community + trust

</div>
<div>

### Developer Marketing

**North** · fintech

Content + business impact

</div>
</div>

<div class="pt-12 opacity-70 text-sm">
Engineering, education, and marketing aren't separate skillsets to me — every one of these needed all three.
</div>

---

## layout: section

# 1. Design System Adoption at Workday

---

# Context

- 80+ products in active development at Workday
- Most of them weren't building on Canvas Kit, our design system
- 2.5 years of this effort, during a 5-year tenure at Workday
- Grew out of running a cross-team **Frontend Guild** before I joined the design system team

---

# Audience & Objective

**Audience**
Workday product engineering teams — 80+ products

**Objective**
Make Canvas Kit the developer default for building UI — a default, not a mandate

---

# How: four levers

1. **Interest** — speak in product terms, everyday visibility (demos, announcements)
2. **Education** — workshops, office hours
3. **Delivery** — build what teams actually needed: rich types, docs, upgrade guides, codemods
4. **Investment** — fast contribution turnaround, community building

---

# Measurable impact: adoption & reach

- No firm before/after adoption %, but we fixed real fragmentation — teams were splitting between Canvas Kit, open source libraries, and the UI Platform team's own (more app-oriented) component library
- Turned a competing dynamic with UI Platform into a complementary one — we became actively engaged in each other's roadmap planning
- Grew from a handful of teams using our work to being the central hub for frontend discussion at Workday
- Our Slack channel grew from ~200 to 600+ members during my time on the team
- Last release demo I gave drew 70+ attendees across design and development

---

# Measurable impact: education & tooling

- Annual workshops (e.g. _"Compound Components in React"_) drew 20–30 attendees a year — 2-day/4-hour sessions early on, later condensed to 2 hours
- Weekly office hours, averaging 1–2 attendees with questions
- Codemods and migration tooling introduced May 2021 — no firm adoption numbers, but they dramatically increased the speed of adoption with each new release

---

# Measurable impact: community contribution

- 256 community PRs opened 2019–2024, 215 merged — an **84% merge rate**
- Community PRs merged by year: **2020 – 35 · 2021 – 46 · 2022 – 37 · 2023 – 67**
- Median time to merge for community PRs: **~4 days** (vs. ~1 day for maintainer PRs — the gap is mostly review/iteration, not neglect)
- Analyzed from the full PR history — pulled and classified maintainer vs. community myself to get real numbers, not estimates

---

# Lessons learned

The value of tracking metrics. I have some data, but it's incomplete and doesn't all trace back to the origin — I learned this through experimentation. No one ever demanded a business case, because the impact was visible. If I did it again, I'd instrument everything from day one and automate the metric-gathering — which is far easier with LLMs now.

---

## layout: section

# 2. React Denver

---

# Context

- Organized React Denver, 2015–2022
- ~80 meetups organized over 7 years
- Grew out of learning to speak myself — technical communication and speaking were both things I had to build deliberately, not things I started with

---

# Audience & Objective

**Audience**
Denver-area developers — started at 15 in 2015, grew to 100+ per meetup within a couple of years, with registrations as high as ~170

**Objectives**

- Curate talks and grow the speaker pipeline
- Elevate my employer's brand in the local dev community
- Build a **self-sustaining** community

---

# How

- Curating talks, sourcing and coaching new speakers — including Scott Tolinski (Syntax.fm) and Michael Jackson (Remix)
- Rotating sponsors (Workday, Zoom, Gusto, and others) — we typically took only one month of sponsorship at a time, even when sponsors wanted to continue, so we could keep bringing new sponsors into the community and make it stronger
- Deliberate speaker-pipeline investment: two workshops for underrepresented speakers — one attendee went on to become an invited speaker
- One year: 10 of 22 speakers were non-male

---

# Measurable impact

- Grew from 15 attendees (2015) to 100+ per meetup within a couple of years — registrations up to ~170
- 10 of 22 speakers non-male in a given year; at least one underrepresented-speaker workshop attendee became an invited speaker
- Personally referred 4 engineers to Workday out of the community; as Engineering Director at Crownpeak (2016–2017), helped hire 3 full engineering teams largely sourced through the meetup
- Sustainable and growing pre-pandemic; shifted online in 2020–21 (10–15 attendees/meetup) to keep it alive. When in-person attendance didn't recover in 2022, I handed leadership off to another organizer rather than let it fade

---

# Lessons learned

A community only outlives its organizer if you build the _next_ speakers and organizers, not just the next event — and knowing when to hand it off is part of that job, not a failure of it.

---

## layout: section

# 3. Developer Marketing at North

---

# Context

- At North (fintech), needed to build developer awareness and credibility in a competitive market
- Two connected initiatives: a developer portal overhaul, and a developer meetup ahead of a fintech dev conference

---

# Audience & Objective

**Audience**
External developers, plus product/business decision-makers evaluating North

**Objective**
Raise brand awareness and generate real interest in what we were building — with developers _and_ the people who buy

---

# How: the portal

- Rewrote tone and content on our most-trafficked product pages
- Fixed CSS/layout issues
- Identified and addressed accessibility issues
- Submitted to the DevPortal Awards

---

# How: the meetup

- Created fintech_devcon meetup ahead of a fintech developer conference
- Drew a mixed audience: developers, product, and business/decision-makers

---

# Measurable impact

- **3 DevPortal Awards: Best Overall, Best Onboarding, Best Solution Portal** (out of ~8 categories total)
- 60+ attendees at fintech_devcon, mostly developers with product and business decision-makers alongside them

---

# Lessons learned

Marketing credibility with developers has to be backed by the actual product experience — the portal work is what made the meetup's pitch believable, not just visible.

---

## layout: section

# Why this, why Chromatic

---

# The throughline

- Engineering, education, and marketing aren't separate skillsets for me — every program above needed all three
- I look for the gap between what's shipped and what's understood, and build the program that closes it
- Storybook is already the shared substrate for thousands of frontend teams — I want to help close that gap at a scale I've never had access to before

---

## class: text-center

# Thank you

More of my work is shared at [willklein.co/portfolio](https://willklein.co/portfolio)
