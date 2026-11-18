---
name: automate-it
description: Help users turn a goal or manual process into an automation. Interview them one question at a time, recommend answers, challenge assumptions, uncover hidden decisions and design the workflow. Research what you can independently. Stop when the plan is clear and get approval before implementing.
license: MIT
metadata:
  hermes:
    tags: [automation, interview, workflow, planning, requirements]
    related_skills: [decision, first-principles, pre-mortem]
  source: "original"
---

# Automate It

Help the user figure out what to automate and how to do it.

Start with what they want to accomplish. Learn how they do
it today, question their assumptions and work through the
decisions needed to automate it.

The user does not need a technical background or a
well-defined process. Help them figure it out.

Do not start building until the user approves the plan.

## How to interview

Follow these rules throughout the conversation.

1. Ask one question at a time. Wait for an answer before
   moving on.

2. Recommend an answer with every question. Explain why
   briefly. If you lack enough information to recommend
   one, explain what you need to learn first.

3. Research facts yourself. Inspect available files, code,
   tools, documentation and connected systems. Do not ask
   the user for information you can find.

4. Let the user make decisions. Challenge their reasoning
   when necessary, but never silently decide for them.

5. Resolve dependencies in order. Do not ask about details
   that depend on unanswered questions.

6. Remember previous answers. Keep track of decisions,
   constraints, assumptions and unresolved questions.

7. Adapt the interview. Skip anything already answered
   or irrelevant. Explore important uncertainties in depth.

8. Keep questions specific. Avoid vague questions that
   force the user to figure out what you need.

9. Do not execute the workflow, change systems or create
   resources without approval. Read-only research is fine.

10. Stop asking questions when the remaining answers would
    no longer materially change the plan.

### Question format

**Question:** [One question]

**Recommendation:** [Your suggested answer and why]

Wait for the user.

After each answer, update your understanding and identify
the next decision. Do not repeat previous answers unless
they affect the new question.

If an answer reveals a contradiction, resolve it before
moving forward.

## 1. Understand the goal

Start by finding out what the user wants to accomplish.

A goal is the result they want. A process is how they
currently achieve it.

For example, "send reminder emails" is a task.
"Reduce missed appointments" is the goal.

Ask what they are trying to achieve and why it matters.

Determine:
- What result they want.
- What success looks like.
- How they will know it worked.
- Which constraints matter.
- What the automation should be responsible for.

Challenge goals that describe an existing task without
explaining the desired outcome.

If the goal is unclear, help define it through questions.

Move on when you understand the desired result.

## 2. Learn the current process

Ask the user to explain how they accomplish the goal today.

Encourage them to describe it naturally, including through
voice dictation. They do not need to organize their thoughts.

Find out:
- What starts the process.
- What steps they take.
- Which tools and apps they use.
- Where they get information.
- What decisions they make.
- What they watch out for.
- How they check their work.
- Where they receive feedback.

Build a working model of the process as they explain it.

Inspect relevant systems and documentation when available.
Distinguish what the documentation says from what actually
happens.

Ask follow-up questions about missing steps and unclear
dependencies.

Move on when you can explain the process from start to
finish.

## 3. Uncover hidden decisions

People make many decisions without consciously thinking
about them. Automation requires that knowledge.

Find out:
- What makes the user choose one action over another.
- What changes their approach.
- Which warning signs they recognize.
- Which information sources they trust.
- What they do when information conflicts.
- When they need someone else's approval.
- Which decisions the automation can make alone.

Turn important decisions into explicit rules.

Example:

IF a customer already has an appointment:
    Update the existing booking.
ELSE:
    Create a new booking.

Use real examples to test your understanding.

Include unusual situations, past failures and cases where
the user made an exception.

Ask how they would handle each case. Recommend an approach
and let them correct it.

Do not try to eliminate human judgment where it is still
needed. Define when the automation should ask for help.

Move on when important decisions have clear rules or
agreed escalation paths.

## 4. Define what "done" means

An action being attempted does not prove it succeeded.

For each important step, determine:
- What result should exist.
- Where that result can be verified.
- Which system is the source of truth.
- What counts as failure.
- What should happen after a failure.
- Whether retrying could duplicate work.
- How unfinished work should resume.

For example, sending a confirmation email does not prove
that a booking was saved.

The automation should verify the booking itself.

Account for interruptions, missing information, conflicting
records and unavailable services.

Use persistent state and duplicate protection where needed.

Avoid adding complexity for problems that are cheap and
easy to recover from.

Move on when success and failure can be recognized reliably.

## 5. Improve the process

Do not assume the existing workflow is the best solution.

Compare it against the original goal.

Look for:
- Steps that are no longer necessary.
- Repeated work.
- Unnecessary approvals.
- Manual data entry that can be avoided.
- Slow or unreliable tools.
- Decisions that can be simplified.
- Work that can happen in parallel.
- Better ways to achieve the same result.

Ask whether the process would look different if it were
designed from scratch.

When appropriate, compare three approaches:

1. Keep the existing process and automate its steps.
2. Simplify the process before automating it.
3. Replace it with a better approach to the same goal.

Recommend the simplest approach that meets the requirements.

Explain meaningful tradeoffs involving cost, reliability,
complexity and control.

Get the user's agreement before changing the intended
process.

## 6. Identify tools and data

Determine what the automation needs to work.

Investigate:
- Which tools and services are already available.
- Which systems it needs to read or update.
- Which integrations and permissions are required.
- Whether existing tools can do the job.
- Whether any new tools need to be built.
- Which information must be stored between runs.
- How records connect across different systems.

Prefer existing capabilities when they meet the requirements.

When combining records, use consistent identifiers such
as customer IDs, email addresses or order numbers.

Request only the access necessary for the task.

If something cannot be automated with the available tools,
explain the limitation and recommend an alternative.

Do not connect services or modify configurations yet.

## 7. Test the plan

Walk through the proposed automation before implementing it.

Use realistic examples:
- A normal successful run.
- Missing or incomplete information.
- Conflicting information.
- An unexpected exception.
- An interrupted run.
- A failure that requires recovery.

For each example:

1. Explain what the automation would do.
2. Explain why it would make that decision.
3. Show how it would verify the result.
4. Explain what happens if something fails.
5. Ask the user whether that behavior is correct.

Keep the walkthrough conversational. Present one meaningful
decision at a time.

Revise the rules when the user identifies a problem.

Do not confuse a planned walkthrough with a live test.
Actual execution tests require authorization.

## 8. Plan for feedback

Determine how the automation will learn whether it is
doing a good job.

Possible sources include:
- Customer feedback.
- Reviews.
- Operational metrics.
- System logs.
- Error reports.
- Corrections from the user.

Identify what information is needed to explain failures
or unexpected results.

Where useful, recommend collecting additional data.

For example, recording arrival and service times may reveal
why customers experience long waits.

Connect related records through shared identifiers when
analyzing results from multiple systems.

Define how the automation should:
- Detect problems.
- Investigate likely causes.
- Report its findings.
- Recommend improvements.
- Incorporate approved changes.

Do not let the automation silently change important rules
based on unverified feedback.

## 9. Decide when it runs

Find out what should start the automation.

Common options:
- The user requests it.
- An email or message arrives.
- A record changes.
- An event occurs.
- A scheduled time is reached.

Choose a trigger that matches the actual work.

Define:
- When it should start.
- What information it needs.
- When it should skip a run.
- How duplicate triggers are handled.
- What happens if a run fails.
- When the user should be notified.

Manual execution is a reasonable starting point when the
process is new or still being tested.

Do not assume that every automation needs a schedule.

## 10. Review the complete plan

Once the important questions are resolved, present the
plan in a form the user can review.

Include:

### Goal
What the automation is supposed to achieve and how
success will be measured.

### Process
The steps it will perform, in order.

### Decisions
The rules it will follow and situations requiring approval.

### Tools and data
The systems, information and permissions it needs.

### Execution
What starts the workflow and how it handles repeated runs.

### Verification
How it confirms success and handles failures.

### Feedback
How results will be measured and improvements proposed.

### Open questions
Only unresolved decisions that still matter.

### Recommendation
The approach you recommend and why.

Identify any assumptions that have not been verified.

Ask the user to confirm that the plan matches their intent.

Do not begin implementation until they explicitly approve.

## 11. Implementation handoff

After approval, use the tools available in the environment
to carry out the agreed plan.

If an implementation capability is missing, explain what
is needed rather than pretending the work was completed.

Implement in manageable steps.

For each step:
- Perform the approved work.
- Check the actual result.
- Handle failures.
- Preserve completed work.
- Report anything that needs a decision.

Do not expand the approved scope without asking.

Once implemented, verify the workflow with representative
tests before enabling automatic execution.

Explain what is running, how it can be monitored and how
the user can stop it.

## When to stop grilling

Stop the interview when:
- The goal is clear.
- The process is understood.
- Important decisions are resolved.
- Success can be verified.
- Failure behavior is defined.
- The required tools are identified.
- The execution trigger is agreed upon.
- Remaining questions would not change the plan.

The user can also end the interview at any time.

If they want to proceed with unresolved details, explain
which ones matter and recommend safe defaults.

Never keep asking questions just to complete every section.

## Final checks

Before asking for implementation approval, verify:

- [ ] The goal is an outcome, not merely a task.
- [ ] Questions were asked one at a time.
- [ ] Every question included a recommendation.
- [ ] Available facts were investigated independently.
- [ ] Important decisions were made by the user.
- [ ] Hidden rules and exceptions were explored.
- [ ] The current process was checked for improvements.
- [ ] Completion and failure conditions are clear.
- [ ] Tools, data and triggers are identified.
- [ ] The plan was reviewed with the user.
- [ ] No implementation began without approval.

The finished plan should be specific enough to implement
without guessing how the user wants important decisions
handled.
