# Ask Me Questions

Force your AI to ask questions before it does anything. Seriously. It's the single biggest improvement you can make to any AI agent workflow and almost nobody does it.

## The problem

LLMs are really good at sounding confident. They pattern-match, hedge with "it depends", and produce plausible-looking output even when they have no idea what they're doing. You've seen it. The AI charges ahead, makes assumptions, builds the wrong thing, and you waste 20 minutes figuring out why the output is subtly wrong.

Most agent setups make this worse because the default mode is *execution*. Prompt goes in, code comes out. No one stops to ask "wait, do I actually understand what's being asked here?"

## The core idea

Bullshitting answers is easy. Bullshitting questions is almost impossible.

Think about it -- when you force an AI to come up with actual questions before it starts working, it has to genuinely understand the problem. You can't ask "which database should we use?" if you havent identified what databases are even relevant. You can't offer 3 concrete options if you don't understand the tradeoffs.

Bad answers slip through all the time. Bad questions are obvious instantly.

Its basically a forced self-audit. The question "what should I ask?" requires way deeper understanding than "what should I do?" -- because *doing* can be faked through pattern matching, but *asking* requires you to model what information would actually change your behavior.

## Why the user benefits too

This isnt just about making the AI better. It changes the whole dynamic for you as the human:

- You make decisions *before* work starts, not after. Instead of reviewing 500 lines and going "no, not what I meant", you pick a direction upfront.
- Your domain knowledge gets injected early. The AI surfaces decision points, you bring the context it couldn't possibly have.
- Wrong assumptions get caught in 2 seconds instead of being baked into code you have to debug for an hour.
- You stay in control without micromanaging every step. Choose direction, let the AI handle execution.

The interaction flips from "AI does stuff, human reviews" to "human decides, AI executes". Way better.

## Structured beats open-ended

Don't just say "do you have any questions?" -- that produces vague meandering garbage. Use structured questions with concrete options instead.

The constraints are what make it work:

| Constraint | Why it matters |
|---|---|
| 2-4 options per question | Forces the AI to enumerate real paths, not hand-wave |
| Short category label | What *kind* of decision is this? |
| Description per option | Tradeoffs have to be spelled out, not assumed |
| Max 4 questions at a time | Forces prioritization -- what actually matters *right now*? |

## The surgery thing

A surgeon who says "I'll figure it out when I open you up" doesn't understand the procedure.

A surgeon who says "I need to know X, Y, and Z before I cut" does.

Thats it. Thats the whole difference between an AI that's guessing and one that actually understands what its about to do.

## How to actually do this

Add a question step before execution in your agent workflow:

1. User describes what they want
2. AI generates questions -- identifies decision points, unknowns, ambiguities
3. Present structured options -- concrete choices, not open-ended asks
4. User picks
5. AI executes with validated assumptions

One extra round-trip. Thats the cost. The cost of skipping it is rework, wrong output, and the slow erosion of trust in your tooling.

If your AI can't formulate good questions about a task, it doesn't understand the task well enough to do it. And if it *can*, you get to steer the outcome before anything gets built.
