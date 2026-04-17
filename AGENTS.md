# Repo AGENTS.md

Inherit the global `AGENTS.md`. This file only adds repo-local rules to reduce token usage while keeping execution quality high.

## 1. Execution Mode

- Restate the goal in 1 line.
- State only assumptions that change implementation risk.
- Define "done" as observable behavior or a passed verification step.
- Read the minimum set of files needed; avoid loading long files unless they are directly relevant.
- Prefer `rg`, targeted file reads, and focused diffs over broad scans.

## 2. Change Strategy

- Prefer the smallest correct change.
- Reuse the existing stack, libraries, build scripts, and patterns before proposing new tech.
- Add a dependency only when the standard library or current stack is clearly worse.
- Avoid speculative abstractions, broad refactors, and style-only edits.
- Keep functions small, names explicit, and control flow obvious.

## 3. Technology Selection

- Choose technology by local context, not by trend.
- Prefer:
  - existing project stack first
  - standard library/framework features second
  - new dependency last
- When multiple options are viable, pick the one with the lowest maintenance cost and simplest verification path.

## 4. Code Quality

- Preserve the existing code style unless it is actively harmful.
- Favor straightforward code over clever code.
- Handle invalid input, missing configuration, I/O failure, and timeouts at boundaries.
- Never hide errors; add context and keep stack traces intact.
- Write comments only when intent is not obvious from the code.

## 5. Testing Discipline

- Verify every meaningful batch.
- Start with the smallest targeted test, then widen scope only if needed.
- For non-trivial changes, cover happy path, edge case, and failure path.
- If behavior changes, add or update tests where the project already keeps them.
- If no tests exist, provide a short manual verification checklist with exact commands.
- Do not claim success without running at least one relevant verification step, unless tooling is unavailable; if unavailable, say so explicitly.

## 6. Token Discipline

- Do not repeat repository context, tool output, or obvious reasoning.
- Summarize large outputs; quote only the lines that matter.
- Do not inspect unrelated files "just in case".
- Prefer concrete conclusions over long deliberation.

## 7. Final Response

- Report:
  - files changed and why
  - commands run and result
  - remaining risks or follow-ups
