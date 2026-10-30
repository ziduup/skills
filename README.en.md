<div align="center">

[中文](./README.md) · **English**

# 🧰 Zidu Skills

#### Some AI Skills I use every day, all open-sourced here

[![License](https://img.shields.io/badge/License-MIT-3B82F6?style=for-the-badge)](./LICENSE)
[![Skills](https://img.shields.io/badge/Skills-2-10B981?style=for-the-badge)](#-skills)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-8B5CF6?style=for-the-badge)](https://agentskills.io)

![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-D97706?style=flat-square&logo=anthropic&logoColor=white)
![Codex](https://img.shields.io/badge/Codex-Skill-10B981?style=flat-square&logo=openai&logoColor=white)
![40+ Agents](https://img.shields.io/badge/40%2B_Agents-Compatible-3B82F6?style=flat-square)

</div>

Each of these ran in my own projects long enough to prove it saves real effort before being published. No tricks — just a few genuinely useful things.

Every Skill here is a structured instruction set an agent can load directly, following the [Agent Skills](https://agentskills.io) open standard. Installable in 40+ agents that support it, including Claude Code, Codex, Qoder, Kimi Code, iFlow, CodeBuddy, and Cursor.

---

## 📋 Table of Contents

| Name | In one line |
|---|---|
| ❓ [**dayi**](#dayi) | Cross-examine your own plan, decision, or design in rounds, in the style of a pointed interviewer |
| 🔁 [**development-loop**](#development-loop) | Keep multi-step, multi-session coding work moving with a recoverable checkpoint |

---

## 📦 Installation

In Claude Code, Codex, or any tool that supports Agent Skills, just say:

```
Install this skill for me: https://github.com/ziduup/skills/tree/main/<skill-name>
```

Replace `<skill-name>` with the one you want, e.g. `dayi`, `development-loop`. The agent clones it into the right directory — you don't manage paths.

If your agent doesn't support Skills, no problem: download the `SKILL.md` from the skill's folder and use it as a project rules file (or paste it into the conversation). Same effect.

---

## ✨ Skills

<a id="-skills"></a>

<table>
<tr><td>

<a id="dayi"></a>

### ❓ dayi

> *"You said this API needs to be 'fast'. Fast enough for what, exactly?"*

**It solves one thing: getting your plan asked clean.**

The skeleton is **design tree + ready questions + rounds**: every decision branches into the decisions that depend on it; every decision whose prerequisites are settled is a "ready question" you can be asked right now. At most 3 questions per round, each with a one-line recommended answer, worded so your "yes" accepts the recommendation. Answer, the frontier expands, recompute, next round.

The questioning craft comes from a pointed interviewer's expression DNA and eight heuristics: short sentences, straight at contradictions, no room to dodge, suspend authority, zero empathy. **No role-play, no emotional comfort, no deciding for you.**

**Two iron rules**

- **Facts are its job, not yours**: questions needing code, config, logs, dependencies, or git history get a sub-agent dispatched — they don't burn your rounds.
- **It ends only when the ready questions are empty**: then it outputs a consensus checklist, and execution may not start before you confirm. If you call stop ("stop asking", "just do it"), it stops immediately and hands over the checklist right there.

**Triggers**

```
cross-examine this plan
ask this design the hard way
interrogate my plan until it's solid
```

→ [SKILL.md](./dayi/SKILL.md)

</td></tr>
</table>

<table>
<tr><td>

<a id="development-loop"></a>

### 🔁 development-loop

> *"Keep one coding goal moving through small, verified steps — a dead session loses no progress."*

**It manages progress and recovery; it does not do the work** — project rules and the applicable implementation skills govern that.

For coding work spanning multiple steps or sessions, it maintains a **recoverable checkpoint** (`.loop/<task-slug>.md`): the goal, acceptance checks, what's done and verified (with the check command and its result), and the next action. Any fresh session picks it up and resumes — no repeated completed work, no scope drift.

Each step is four things: pick the smallest action that advances an acceptance check and say how it will be verified → make only the needed change → run the check and read the output → update the checkpoint after a meaningful result. Checks are never weakened to manufacture a pass.

**Triggers**

```
resume from the last checkpoint
this spans sessions, set up a checkpoint
push this requirement with development-loop
```

→ [SKILL.md](./development-loop/SKILL.md)

</td></tr>
</table>

---

## 🌟 About

These are skills I use every day myself. If open-sourcing them helps you, a ⭐ is enough. Problems or suggestions — say it in Issues.

---

<div align="center">

[MIT License](./LICENSE) · Free to use / modify / redistribute

Made by [@ziduup](https://github.com/ziduup)

</div>
