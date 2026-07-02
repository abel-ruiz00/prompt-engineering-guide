# Coding & Development: Debugging, Refactoring & Architecture

## Prompt 1 — Systematic Debugging

**Best with**: Claude, GPT-4, Gemini

```
You are a senior software engineer debugging a production issue. I will share code that is producing unexpected behavior.

Context:
- Language/framework: [e.g., Python/FastAPI, TypeScript/Next.js]
- Expected behavior: [what should happen]
- Actual behavior: [what actually happens]
- Error message (if any): [paste error]

Your task:
1. Read the code carefully and identify the root cause (not symptoms)
2. Explain WHY the bug occurs, not just WHERE — trace the execution path
3. Provide the minimal fix (smallest change that solves the problem)
4. Flag any other issues you notice that could cause problems later
5. If the bug is environmental (config, dependency, race condition), say so

Do not rewrite the entire file. Show only the lines that need to change with before/after.

Code:
[PASTE CODE HERE]
```

**Why it works**: "Root cause, not symptoms" prevents shallow answers. "Minimal fix" stops the model from rewriting everything. "Trace the execution path" forces step-by-step reasoning.

**Variations**:
- Add "This is a multi-threaded application" for concurrency bugs
- Add "The bug only appears under high load" for performance-related issues
- Add "Include a regression test for this fix" if you want test coverage

---

## Prompt 2 — Architecture Review

**Best with**: Claude, GPT-4

```
You are a principal engineer reviewing a system design. I'll describe the current architecture and the problem we're trying to solve.

System context:
- Tech stack: [e.g., React + Node.js + PostgreSQL + Redis]
- Scale: [e.g., 10k DAU, 500 req/s peak]
- Team size: [e.g., 3 backend engineers]
- Current pain point: [e.g., API response times degrading, deployment takes 45min]

Review the architecture for:
1. Bottlenecks and single points of failure
2. Over-engineering (complexity that isn't justified by the scale)
3. Missing pieces (monitoring, caching, error handling, auth)
4. Scalability ceiling — what breaks first if traffic 10x's?
5. One concrete recommendation you'd prioritize this sprint

Be direct. Skip compliments. If something is fine, say "this is fine" and move on.

Architecture:
[DESCRIBE OR PASTE DIAGRAM]
```

**Why it works**: "Skip compliments" and "be direct" eliminates filler. Specifying team size prevents suggestions that require 20 engineers. "What breaks first at 10x" is a forcing function for prioritization.

**Variations**:
- Add "We have zero test coverage" for quality-focused review
- Add "Budget is limited, prefer open-source solutions" for cost constraints
- Replace "principal engineer" with "SRE" for reliability-focused review
