---
title: "Your AI Writes Code. Who Checks If It Works?"
date: 2026-04-08
author: Milad Shaddelan
tags: [ai, software-engineering, quality, devtools]
---

# Your AI Writes Code. Who Checks If It Works?

Every engineering team I talk to has the same story: they plugged in an AI coding tool, generation went through the roof, and for about two weeks it felt like magic.

Then the bugs started.

Not obvious bugs — the kind that pass code review because the code *looks* right. The kind that work in isolation but break the moment they touch a real database, a real auth flow, a real user. The AI wrote confident, clean, plausible code that nobody actually validated before merging.

## The generation gap

Most AI tools in software development solve one problem: writing code faster. And they're good at it. But writing code was never the bottleneck.

The bottleneck is everything that happens *after* code is written: Does it actually do what the ticket says? Does it break existing behavior? Does it handle the edge cases the spec didn't mention? Does it pass the tests — and are the tests even testing the right thing?

Generation without validation is just producing bugs faster.

## What changes when AI writes the code

When a human writes code, there's an implicit quality loop. You write a function, you mentally trace through it, you run it, you catch the obvious mistakes before anyone else sees it. The code carries the context of the person who wrote it.

AI-generated code doesn't have that. It's statistically plausible, not logically verified. It passes the eye test because it looks like code that would work — it follows patterns, uses the right libraries, names things sensibly. But "looks right" and "is right" are different problems.

This means the review process has to change. You can't review AI code the same way you review human code, because the failure modes are different. Human code fails in predictable ways — typos, off-by-ones, missed edge cases the developer didn't think of. AI code fails in subtle ways — it hallucinates APIs that don't exist, it makes reasonable-looking assumptions that contradict your codebase, it writes tests that test the wrong thing and pass anyway.

## The missing layer

Here's what I think the stack looks like in two years:

**What we have now:** Developer asks AI to write code → AI generates code → Developer reviews and merges.

**What we need:** Developer defines intent → AI generates code → Automated validation checks correctness → Quality gates verify it meets the spec → *Then* a human reviews the merge.

The difference isn't the AI. It's the infrastructure between generation and production. The planning, the validation, the quality gates — the stuff that turns "AI wrote it" into "it actually works."

If you've ever worked in construction or civil engineering, this isn't a new idea. A building doesn't go up because someone drew blueprints. It goes up because there's a system: inspections at every stage, materials tested against specs, work checked against plans before the next phase starts. The creativity is in the design. The execution is disciplined, validated, and parallel.

Software is finally catching up to that model.

## What this means for engineering teams

If you're leading an engineering team right now, the question isn't whether to use AI for code generation. That ship sailed. The question is: what's your validation story?

Because right now, most teams are doing one of two things:

1. **Trusting the AI output and shipping faster** — which works until it doesn't, and when it doesn't, it's expensive.
2. **Manually reviewing every line of AI code** — which defeats the purpose of using AI in the first place.

Neither scales. What scales is building the layer that sits between generation and production — the automated checks that catch what humans miss, the quality gates that enforce what the spec requires, the validation that runs before a human ever has to look at it.

That's what I'm building with [Qalib](https://github.com/MiladShd). Not another code generator. The part that makes sure generated code actually works.

## The real opportunity

I hear a lot of anxiety about AI replacing developers. I don't see it that way. What I see is that the developer's job is shifting — from writing every line to architecting the system, defining the intent, and making sure the output meets the bar.

That's not less work. It's different work. And honestly, it's the work most senior engineers wanted to be doing anyway.

The teams that figure out the validation layer first are going to ship circles around everyone else. Not because their AI is better — everyone has access to the same models. But because they built the infrastructure to trust what the AI produces.

That's the gap. That's what I'm working on.

---

*If you're thinking about this problem too, I'm always down to [compare notes](https://www.linkedin.com/in/milad-shaddelan/).*
