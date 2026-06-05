# Self-evaluation rubric — CodeFlow Module 00

> This rubric lets you evaluate yourself without an external grader.
> Every check is binary: **you meet it or you don't**. No middle ground.
>
> Golden rule of the module: if it works but **you can't explain why**, it doesn't count.
> The "Can you explain it?" column is as important as the functional checks.

---

## How to score

- Each exercise has a **mandatory minimum**. If you fail a single Mandatory check, the exercise is **incomplete** — bonus doesn't compensate.
- **NOTES.md is mandatory** in all exercises. Without it, the exercise is 0 regardless of whether everything else works.
- Bonus only counts if Mandatory is **100% complete**.

| Status | Meaning |
|--------|---------|
| ✅ | Done and I can explain it |
| ⚠️ | Works but I don't fully understand it → review it |
| ❌ | Not done |

---

## ex00 — Init & Context

### Mandatory

- [ ] I ran `/init` in the starter directory
- [ ] I examined the generated `CLAUDE.md` and documented what Claude detected
- [ ] My `CLAUDE.md` includes **compilation rules** (flags, C++ standard, directory structure)
- [ ] My `CLAUDE.md` includes **style restrictions** (variable names, comment format)
- [ ] My `CLAUDE.md` limits the directories Claude can modify to `src/` and `inc/`
- [ ] My `CLAUDE.md` includes the instruction to respond in English
- [ ] I used `@src/Calculator.cpp` to limit context to one file
- [ ] I used `@tests/` to limit context to the tests folder
- [ ] I have **at least 3 screenshots** in `screenshots/` demonstrating `@` usage
- [ ] `NOTES.md` compares the original `CLAUDE.md` vs the customized one

### Can you explain it?

- [ ] I can explain **why** I chose each rule in my `CLAUDE.md`
- [ ] I can explain exactly what `@` does and how it affects context

### Bonus

- [ ] "Common mistakes" section in `CLAUDE.md` (e.g.: don't use printf, don't touch the Makefile)
- [ ] Second `CLAUDE.md` in `tests/` with testing-specific rules

---

## ex01 — Session Management

### Mandatory

- [ ] I ran the complete **9-step scenario** on the ex00 project
- [ ] `session_log.txt` records all 9 steps with real observations
- [ ] I ran `/compact` and documented what Claude remembered and what it forgot
- [ ] I ran `/compact [instructions]` and compared it with the normal compact
- [ ] I demonstrated the use of `/clean`
- [ ] I demonstrated the use of `Esc Esc` to interrupt an operation
- [ ] `NOTES.md` answers: when `/compact` vs `/clean`? When is double Esc critical?
- [ ] `NOTES.md` includes **at least 2 personal strategies** to minimize token usage

### Can you explain it?

- [ ] I can explain what information survives a `/compact` and why
- [ ] I can explain the real difference between `/compact` and `/clean`

### Bonus

- [ ] Comparative table: operation → tokens consumed
- [ ] I identified which operations consume the most context and why

---

## ex02 — HookGuard

### Mandatory

- [ ] I created a `PostToolUse` inspection hook with matcher `"*"` that dumps stdin to JSON
- [ ] I made Claude use **at least 3 tools** (Read, Write, Bash) and examined the JSONs
- [ ] `hooks/guard.sh` **blocks** `rm -rf` and `sudo`
- [ ] `hooks/guard.sh` logs all bash commands to `logs/commands.log` with timestamp
- [ ] `hooks/compiler_check.sh` runs `make` after every Write on `.cpp` or `.hpp`
- [ ] If compilation fails, the error is passed back to Claude for correction
- [ ] `hooks/compiler_check.sh` logs OK/FAIL + timestamp to `logs/compile.log`
- [ ] `settings.json` has both hooks configured (Pre and Post)
- [ ] `logs/commands.log` has **at least 5 entries** with timestamp
- [ ] `logs/compile.log` has **at least 3 entries** (with OK and FAIL)
- [ ] `NOTES.md` explains the JSON structure of each tool

### Can you explain it?

- [ ] I can explain why `exit 2` blocks the operation and `exit 0` allows it
- [ ] I can explain **why I inspect with jq FIRST** before writing the hook
- [ ] I can explain how the PostToolUse stdout reaches Claude as feedback

### Bonus

- [ ] `Notification` hook that warns in `notifications.log` when Claude has been idle >60s
- [ ] `Stop` hook that runs `make clean && make` at the end of each Claude turn
- [ ] `settings.local.json` with absolute paths + explanation of why they're safer

---

## ex03 — PlayBot

### Mandatory

- [ ] I installed the Playwright MCP server
- [ ] `mcp_config.json` is configured and Claude Code detects it
- [ ] I captured a screenshot of the available MCP tool verification
- [ ] Claude navigated to a public website and extracted specific data
- [ ] `reports/github_profile.md` contains **real extracted data**
- [ ] I designed a test that verifies page load (status 200)
- [ ] The test checks that a specific element exists on the page
- [ ] `reports/test_results.md` has **at least 2 tests** (PASS/FAIL + timestamp)
- [ ] `screenshots/` has process captures
- [ ] `NOTES.md` explains the MCP pattern: configure → verify → use

### Can you explain it?

- [ ] I can explain what MCP is and why it's Claude Code's "plugin system"
- [ ] I can explain the configure→verify→use pattern in my own words

### Bonus

- [ ] Second MCP server configured and used in the same session
- [ ] `PostToolUse` hook from ex02 combined with Playwright (logs each visited page)

---

## ex04 — SDK Bridge

### Mandatory

- [ ] **Step 1:** my C++ program reads and parses `sample_report.json` correctly
- [ ] **Step 2:** `bridge.mjs` receives a `.cpp` path, analyzes it via SDK and generates JSON
- [ ] **Step 2:** I use `allowedTools: ["Read"]` to limit what Claude can do
- [ ] **Step 3:** `CodeReviewer` launches `bridge.mjs` with `system()`
- [ ] **Step 3:** I read the generated JSON and display it via stdout
- [ ] **Step 3:** I handle errors (file not found, SDK unavailable, malformed JSON)
- [ ] **Step 4:** I detect the memory leak in `leak.cpp`
- [ ] **Step 4:** I detect the uninitialized variable in `uninit.cpp`
- [ ] **Step 4:** I detect the logic bug in `logic_bug.cpp`
- [ ] The program compiles with `-Wall -Wextra -Werror -std=c++17`
- [ ] `NOTES.md` explains the full flow: C++ → system() → bridge.mjs → SDK → Claude → JSON → C++

### Can you explain it?

- [ ] I can explain why C++ doesn't call the SDK directly and needs the bridge
- [ ] I can explain exactly what `system()` does and its risks
- [ ] I can explain why I limit to `allowedTools: ["Read"]`

### Bonus

- [ ] `Stop` hook from ex02 that runs `CodeReviewer` automatically and logs to `logs/review.log`
- [ ] I replaced `system()` with `fork()/exec()` and can explain the difference
- [ ] **Final bonus:** review result arrives via Telegram/Slack via curl

---

## Final verdict (fill it in yourself)

| Exercise | Mandatory complete | NOTES.md | Bonus | Can I explain everything? |
|----------|:-----------------:|:--------:|:-----:|:-------------------------:|
| ex00     |                   |          |       |                           |
| ex01     |                   |          |       |                           |
| ex02     |                   |          |       |                           |
| ex03     |                   |          |       |                           |
| ex04     |                   |          |       |                           |

> If you've checked ✅ on all Mandatory and all "Can you explain it?" across the 5 exercises,
> you've mastered Module 00. You haven't learned to use Claude Code: you've learned to **control it**.
>
> If you have ⚠️ anywhere, go back to that point. The goal wasn't to finish — it was to understand.

---

© 2026 Mikel Zabal – CodingWithZabal
