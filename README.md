# Automate It

An agent skill that turns a goal or a manual process into an automation by
interviewing you about it — one question at a time — and refusing to build
until the plan makes sense.

Most automation projects fail before any code gets written. The "goal" was
really a task, the real process differed from the documented one, the
exceptions lived only in someone's head, and nobody defined what a successful
run looks like. This skill makes the agent resolve those things with you first,
then hand off to implementation.

## What it does

- **Turns tasks into outcomes.** "Send reminder emails" becomes "reduce missed
  appointments," with a way to know whether it worked.
- **Maps the current process** as it actually happens, including where the
  documentation and reality disagree.
- **Surfaces hidden decisions** — the rules you apply without noticing, turned
  into explicit branches, escalation paths and approval points.
- **Defines done per step.** What result should exist, which system is the
  source of truth, what counts as failure, where a retry could duplicate work,
  and how an interrupted run resumes.
- **Challenges the process.** Keep and automate it, simplify it first, or
  replace it with a different approach to the same goal.
- **Identifies tools and data**: existing integrations, permissions, what must
  persist between runs, and how records join across systems.
- **Walks realistic scenarios** — a normal run, missing data, conflicting
  records, an exception, an interrupted run, an unrecoverable failure — before
  anything goes live.
- **Plans for feedback**: how problems get detected, explained, reported, and
  changed only with approval.
- **Picks the trigger** that matches the work: manual, message, record change,
  event or schedule.

Every question comes with a recommended answer and a short reason. Facts the
agent can find for itself — files, code, docs, connected systems — it looks up
rather than asking. Decisions stay yours.

The session ends with a reviewable plan: goal, process, decisions, tools and
data, execution, verification, feedback, open questions and a recommendation.
Implementation starts only after explicit approval, in small steps, each
verified before the next.

## Install

Clone it into the skills directory your agent reads.

```sh
# Claude Code
git clone https://github.com/TheSethRose/automate-it.git ~/.claude/skills/automate-it

# Shared skills folder used by some harnesses
git clone https://github.com/TheSethRose/automate-it.git ~/.agents/skills/automate-it
```

Other harnesses: point their skills directory at the repo. The skill is a single
`SKILL.md` with YAML frontmatter and no runtime dependencies.

## Use

Invoke it by name, or just describe the thing you want automated:

```
@automate-it I spend two hours every Monday reconciling invoices by hand.
```

```
@automate-it help me automate reminding clients about overdue invoices
```

The agent starts with the goal, works down the decisions in dependency order,
and stops when the remaining questions would no longer change the plan.

## Repo layout

```
SKILL.md            the skill: interview rules and the 11-part design sequence
agents/openai.yaml  display name and short description for harnesses that read it
LICENSE             MIT
```

## License

MIT — see [LICENSE](LICENSE).
