<div align="center">

# Code Flow— Module 00

### Master Claude Code: from `/init` to the SDK

*A progressive study module to learn how to **control** your development agent.*
*Not just use it. Control it.*

</div>

---

## What is this?

Claude Code is a powerful tool. The problem isn't making it work — the problem is making it work **the way you want**, in a supervised, controlled, and efficient manner.

This module takes you through 5 progressive exercises where you learn to tame the agent layer by layer: from configuring its context to integrating it programmatically into your own C++ code.

And yes — you'll learn to do it **spending fewer tokens**. That's the problem everyone has with Claude Code: the context explodes, the bill explodes, and on top of that it starts forgetting things. Here we dedicate an entire exercise (ex01) to managing the context window the same way you manage memory in C: if you don't control it, it blows up in your face. You'll know when to use `/compact`, when `/clean`, which operations consume more context, and you'll come out with your own strategies to make every token count.

Inspired by the philosophy of schools like 42: **if you can't explain what you've done, you haven't learned it.** This isn't about Claude Code doing your work. It's about you proving you control Claude Code.

---

## Who is this for?

- **You come from a 42-style school** and want to add Claude Code to your arsenal with the rigor you're already used to.
- **You're a developer** who has used Claude Code but suspects you're only scratching the surface.
- **You want to truly understand** how the internal loop works: hooks, context, MCP, SDK.

You don't need to be an expert. You need to know how to program and want to understand the *why*, not just the *how*.

---

## The 5 exercises

| # | Name | What you learn |
|---|------|----------------|
| **ex00** | Init & Context | Initialize a project, write a good `CLAUDE.md`, control context with `@` |
| **ex01** | Session Management | Manage the context window: `/compact`, `/clean`, `Esc Esc` and token savings |
| **ex02** | HookGuard | Intercept Claude with `PreToolUse` and `PostToolUse` hooks. Block dangerous commands, compile automatically |
| **ex03** | PlayBot | Connect external tools via MCP. Automate a browser with Playwright |
| **ex04** | SDK Bridge | Call Claude Code from C++ via SDK. Build an automatic code reviewer |

Each exercise builds on the previous one. ex04 integrates **everything** learned — and closes with a detail that hooks you: you launch a code review, head to the gym, and the result arrives on your phone via Telegram.

---

## Requirements

- Claude Code installed and authenticated with a plan that allows Claude Code usage.
- Node.js >= 18 (for SDK and MCP)
- `jq` installed (`sudo apt install jq` or `brew install jq`)
- Git
- A text editor of your choice

For exercises with C++: compiler with `-std=c++17` support.

> **Windows user?** This module is designed for macOS and Linux. If you're on Windows, use **WSL2** — you'll have a real Ubuntu environment and everything will work exactly the same.
> → [WSL2 installation guide](https://learn.microsoft.com/en-us/windows/wsl/install)

---

## How to start

📄 **Subject:** [English](subject/codeflow_subject_v2.pdf)

This repository is **for reference**. You don't submit here — you use it to read the subject and grab the starters.

```bash
# 1. Clone the repo
git clone https://github.com/zabal42/CodeFlowModule00_EN.git

# 2. Read the full subject (seriously, read it all before starting)
open subject/codeflow_subject_v2.pdf

# 3. Create your own working repo
mkdir codeflow-m00-yourname && cd codeflow-m00-yourname
git init

# 4. Copy the starter for the exercise you're working on
cp -r ../CodeFlowModule00_EN/starters/ex00 .

# 5. Go in, compile, and start working
cd ex00 && make
```

> **Tip:** make a checkpoint commit **before** letting Claude Code modify your code. If something breaks, you go back. And if you can't explain what each line does, don't submit it.

---

## Self-evaluation

No one to grade you? No problem.

➡️ **[Open the interactive rubric](https://zabal42.github.io/CodeFlowModule00_EN/)** — check off items, see your progress in real time and get your final verdict.

Also available as plain text: [`EVALUATION.md`](EVALUATION.md)

How to use it:

1. **Open the link** and go exercise by exercise
2. **When you finish each one**, check the boxes with a click
3. There are three blocks per exercise:
   - **Mandatory** — what the subject requires. Binary: you have it or you don't
   - **Can you explain it?** — as important as the mandatory. If it works but you don't understand it, it doesn't count
   - **Bonus** — only if mandatory is 100% complete
4. **When you complete everything**, the final verdict appears

> If you can check everything in Mandatory **and** all the "Can you explain it?" items, you're ready for a real defense.

---

## The rule that sums it all up

> By Toutatis!! Use your brain!
> Claude Code is a tool, not a substitute for your reasoning ability.

---

<div align="center">

**Made by Mikel Zabal** · CodingWithZabal
[LinkedIn](https://www.linkedin.com/in/mikel-zabal-martin/) · mzabalm@gmail.com

*If this helped you, a ⭐ helps it reach more people.*

© 2026 Mikel Zabal – CodingWithZabal

</div>
