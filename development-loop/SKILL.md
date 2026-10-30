---
name: development-loop
description: Use when coding work spans multiple steps or sessions and needs a recoverable progress checkpoint to prevent repeated work or scope drift.
---

# Development Loop

Keep one coding goal moving through small, verified steps. This skill manages progress and recovery; project instructions and applicable implementation skills govern the work itself.

## Start or resume

1. Read the user goal, relevant project instructions, existing plan or issue, current diff, and the latest relevant check results. State assumptions and acceptance checks. Resolve material ambiguity before a dependent change.
2. Reuse the task's existing plan ledger or tracker if it has one. Otherwise, for work likely to outlast the current context, create `.loop/<task-slug>.md` in the workspace. Use a distinct file per task; short work needs no file.
3. Check that a resumed record identifies this task and workspace. Reconcile it against the current files, Git history, and test output. Treat observed state as authoritative when they differ.

## Each step

1. Choose the smallest action that advances an acceptance check; say how it will be verified.
2. Make only the needed change. Follow any applicable design, debugging, test, worktree, or review workflow already required by the current environment.
3. Run the relevant check and inspect its output. If it fails, diagnose the cause before changing strategy. Do not weaken checks to manufacture a pass.
4. Update the checkpoint after a meaningful result and before a handoff or pause. Record the next action clearly enough for a fresh agent or session to resume without repeating completed work.

## Checkpoint

Keep only these fields, adding detail when needed:

```text
Task and workspace:
Goal and acceptance checks:
Done and verified: <check/command, result, relevant revision or files>
Current uncertainty or blocker:
Next smallest action and its check:
Decisions that affect later work:
```

Keep secrets and unnecessary logs out of the checkpoint. Do not commit local progress notes unless the user or project workflow calls for a shared handoff.

## Continue, pause, or finish

- Finish only when the acceptance checks have fresh evidence; report what passed and any checks that could not run.
- After two steps with no new evidence, inspect the failed assumptions and try a different bounded probe. Ask for input only when a decision or missing access genuinely requires it; continue independent work when possible.
- Treat a step budget, if supplied, as a checkpoint for reporting and replanning. Do not treat an arbitrary count as proof of completion or a reason to abandon an achievable goal.
- Pause when the user asks, a required decision is missing, or an action crosses an actual authorization boundary. Check the user's existing authorization before asking again.

## Skill and tool fit

Read currently available skills before using them. Relevant Superpowers skills may cover brainstorming, plans, TDD, debugging, worktrees, execution, review, and final verification; follow their current instructions rather than duplicating their ledgers or gates here. Use only tools present in this runtime. Delegate only when the user or governing instructions permit it, the tools are available, and the subtasks are independent.
