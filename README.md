<div align="center">

**中文** · [English](./README.en.md)

# 🧰 Zidu Skills

#### 我自己每天在用的一些 AI Skill，都开源在这里

[![License](https://img.shields.io/badge/License-MIT-3B82F6?style=for-the-badge)](./LICENSE)
[![Skills](https://img.shields.io/badge/Skills-2-10B981?style=for-the-badge)](#-skills)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-8B5CF6?style=for-the-badge)](https://agentskills.io)

![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-D97706?style=flat-square&logo=anthropic&logoColor=white)
![Codex](https://img.shields.io/badge/Codex-Skill-10B981?style=flat-square&logo=openai&logoColor=white)
![40+ Agents](https://img.shields.io/badge/40%2B_Agents-Compatible-3B82F6?style=flat-square)

</div>

都是在自己项目里跑通了一段时间，确实省事，才搬出来开源的。没什么花活，就是几个挺实用的东西。

这里的每个 Skill 都是 Agent 能直接加载的结构化指令集，遵循 [Agent Skills](https://agentskills.io) 开放标准。Claude Code、Codex、Qoder、Kimi Code、iFlow、CodeBuddy、Cursor 等 40+ 支持该标准的 Agent 都能装。

---

## 📋 目录

| 名字 | 一句话 |
|---|---|
| ❓ [**dayi（拷问）**](#dayi) | 用易立竞的提问手艺，对自己的计划、决策或设计做分轮次拷问 |
| 🔁 [**development-loop（开发循环）**](#development-loop) | 跨步骤、跨会话的编码工作，用可恢复检查点防止重复劳动和范围漂移 |

---

## 📦 安装方式

在 Claude Code、Codex 等支持 Agent Skills 的工具里，直接说：

```
帮我安装这个 skill：https://github.com/ziduup/skills/tree/main/<skill-name>
```

把 `<skill-name>` 换成你想装的那个，比如 `dayi`、`development-loop`。Agent 会自己 clone 到对应目录，不用你操心路径。

你的 Agent 不支持 Skill 也没关系：把对应目录的 `SKILL.md` 全文下载下来，当成项目规则文件（或直接贴进对话）让 Agent 照着执行，效果一致。

---

## ✨ Skills

<a id="-skills"></a>

<table>
<tr><td>

<a id="dayi"></a>

### ❓ dayi（拷问）

> *"你说这个接口'要快'。快到什么程度算合格？"*

**它只解决一件事：把你的方案问清楚。**

骨架是**设计树 + 就绪问题 + 分轮**：每个决策向下分出依赖它的决策；所有前置已定的决策就是"就绪问题"，现在就能问。每轮最多问 3 题，每题附一句推荐答案——措辞让你的"是"就等于采纳推荐。答完就绪问题外扩，重新计算，再问下一轮。

提问手法取自易立竞的表达 DNA 与八条启发式：短句、直取矛盾、不留闪避空间、身份悬置、零共情。**不扮演角色，不给你情绪按摩，不替你做判断。**

**两条铁律**

- **事实归它查，不归你答**：需要代码、配置、日志、依赖、git 历史支撑的问题，派子 agent 去查，不占用你的轮次。
- **就绪问题清空才算结束**：此时输出一份共识清单，你确认之前不许开始执行。你叫停（"别问了""直接做"）也立刻停，当场交共识清单。

**怎么触发**

```
拷问一下这个计划
用易立竞的方式问问这个方案
帮我把这个设计问透
```

→ [SKILL.md](./dayi/SKILL.md)

</td></tr>
</table>

<table>
<tr><td>

<a id="development-loop"></a>

### 🔁 development-loop（开发循环）

> *"让一个编码目标穿过小的、已验证的步骤，坏了一个会话也不丢进度。"*

**它管进度和恢复，不管干活本身**——项目规则和对应的实施 skill 说了怎么干。

编码工作跨多个步骤、跨会话时，它维护一份**可恢复检查点**（`.loop/<任务 slug>.md`）：目标、验收检查、已完成且已验证的事项（附检查命令和结果）、下一步动作。任何新会话拿着它就能接着跑，不重复已完成的工作，也不放任范围漂移。

每步只有四件事：选一个能推进验收检查的最小动作并说明怎么验证 → 只做必要的改动 → 跑检查并亲眼看输出 → 有实质结果就更新检查点。检查不许为了让进度好看而放水。

**怎么触发**

```
接着上次的进度做
这个任务跨会话，建个检查点
用 development-loop 推这个需求
```

→ [SKILL.md](./development-loop/SKILL.md)

</td></tr>
</table>

---

## 🌟 关于

这些 skill 都是我自己每天在用的，开源出来如果对你有帮助，给个 ⭐ 就行。有问题或建议，欢迎在 Issues 里说一声。

---

<div align="center">

[MIT License](./LICENSE) · 自由使用 / 修改 / 再分发

Made by [@ziduup](https://github.com/ziduup)

</div>
