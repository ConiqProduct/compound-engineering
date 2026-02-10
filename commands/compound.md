# /compound — Document what you learned

Capture a recently solved problem as searchable documentation. This is what makes the system compound — each documented solution makes future work faster.

## When to Use

After solving a non-trivial problem:
- Debugging that took multiple attempts
- Non-obvious solution
- Tricky configuration or setup
- A gotcha that would bite someone again

**Don't document:**
- Simple typos or syntax errors
- Obvious fixes
- Trivial one-line changes

---

## Step 1: Gather Context

Extract from the conversation/session:

- **What was the problem?** (exact error messages, observable symptoms)
- **What was tried?** (failed attempts and why they didn't work)
- **What was the root cause?** (technical explanation)
- **What fixed it?** (the actual solution with code)
- **How to prevent it?** (what to do differently next time)

If any critical context is missing, ask the user before proceeding.

---

## Step 2: Categorize

Determine the category based on the problem type:

| Category | When to use |
|----------|-------------|
| `build-errors` | Compilation, bundling, dependency issues |
| `test-failures` | Flaky tests, test configuration, mocking issues |
| `runtime-errors` | Crashes, unhandled exceptions, type errors |
| `performance` | Slow queries, memory leaks, rendering issues |
| `database` | Migration issues, query problems, schema design |
| `security` | Auth bugs, data exposure, vulnerability fixes |
| `ui-bugs` | Layout issues, state bugs, styling problems |
| `integration` | API issues, third-party service problems |
| `config` | Environment setup, deployment, infrastructure |
| `logic-errors` | Business logic bugs, edge cases, race conditions |

---

## Step 3: Check for Related Docs

Search `.ai/docs/solutions/` for similar issues:

```
Search by keywords, error messages, module names
```

If a similar doc exists:
- Cross-reference it (link both ways)
- Consider updating it instead of creating a duplicate

---

## Step 4: Write the Documentation

Create the file at: `.ai/docs/solutions/<category>/<descriptive-name>.md`

Use the template from `.ai/templates/solution.md`.

**Naming examples:**
- `.ai/docs/solutions/performance/n-plus-one-user-dashboard.md`
- `.ai/docs/solutions/build-errors/nextjs-turbopack-css-modules.md`
- `.ai/docs/solutions/runtime-errors/prisma-connection-pool-exhaustion.md`

---

## Step 5: Next Steps

After documenting:

> Solution documented at `.ai/docs/solutions/[path]`. What next?
>
> 1. **Continue working** — documentation complete
> 2. **Link related docs** — connect to similar solutions
> 3. **View the doc** — review what was captured
> 4. **Refine** — add more detail or examples

---

## What Good Documentation Looks Like

**Do:**
- Include exact error messages (copy-paste)
- Include specific file paths and line numbers
- Show code examples (before/after)
- Explain WHY the fix works, not just what changed
- Document failed attempts (helps avoid wrong paths)
- Add prevention guidance

**Don't:**
- Write vague descriptions ("something was wrong")
- Skip technical details ("fixed the code")
- Omit context (which version? which file? what config?)
- Create code dumps without explanation

---

## The Compounding Effect

```
First occurrence:   Research → Debug → Fix → Document  (30 min)
Second occurrence:  Search docs → Apply fix             (2 min)
Third occurrence:   AI finds it automatically            (30 sec)
```

Knowledge compounds. The `.ai/docs/solutions/` folder is your team's institutional memory. (When using the standalone clone, paths are under `.ai/docs/`.)

---

## Auto-trigger

This workflow can be triggered automatically when the user says things like:
- "that worked"
- "it's fixed"
- "problem solved"
- "working now"

When detected, offer: "Want me to document this solution for future reference?"
