# Agent production readiness

A Claude skill that reviews an AI agent for production readiness.

A demo that works in a keynote is not an agent that works at 2am. This skill runs the review I use to tell the difference. It scores an agent across evaluation, cost, observability, guardrails, human oversight, reliability, and governance, and returns the gaps that stand between a prototype and a system you can operate.

It is the executable version of the checklist at [hamidettefagh.com/agent-production-readiness](https://hamidettefagh.com/agent-production-readiness).

## Install

This follows the open [Agent Skills](https://code.claude.com/docs/en/skills) format, so it works anywhere skills are supported. To use it in Claude Code, put this directory in your skills folder:

```bash
git clone https://github.com/hamidettefagh/agent-production-readiness.git \
  ~/.claude/skills/agent-production-readiness
```

Use `.claude/skills/` inside a project instead of `~/.claude/skills/` to scope it to one repo.

## Use

Ask Claude to review an agent, and point it at the design, prompt, tools, or deployment:

> Review this agent for production readiness.

The skill runs a four-phase review: understand the agent, assess each dimension against the evidence, score it out of 28, and return the gaps in priority order. It leads with the gaps, not the score.

## What it checks

Seven dimensions, four checks each. The full rubric, with what to look for on each check, is in [`references/rubric.md`](references/rubric.md).

| Dimension | The question it answers |
|---|---|
| Evaluation | Can you tell if a change helped before users do? |
| Cost | Is it affordable at scale, and will you know before finance does? |
| Observability | When something breaks, can you see what happened? |
| Guardrails | Does it do what it should and refuse what it should not? |
| Human oversight | Can a person step in when the agent should not act alone? |
| Reliability | Does it keep working, and can a bad change be undone? |
| Governance | Can you answer for what the agent did? |

## Why

Most agents that fail in production fail for boring reasons. Not the model, not the prompt, but a missing eval set, an unversioned config, an action that runs with no human near it, an audit trail nobody kept. The interesting work is not getting an agent to work once. It is the evidence that it will keep working, and the ability to see and undo it when it does not.

This skill encodes that as a review you can run. The score is a prompt for a conversation, not a certificate.

---

Hamid Ettefagh — [hamidettefagh.com](https://hamidettefagh.com)
