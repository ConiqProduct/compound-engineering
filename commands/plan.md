# /plan — Turn ideas into actionable plans

Transform a feature description, bug report, or improvement idea into a well-structured plan.

## Input

The user provides a description of what they want to build or fix.

**If the description is empty or vague**, ask: "What would you like to plan? Describe the feature, bug fix, or improvement."

Do not proceed until you have a clear description.

---

## Step 1: Refine the Idea

Ask 2-3 focused questions to understand:
- **What** is the goal? What problem does this solve?
- **Who** is affected? End users, developers, ops?
- **What constraints** exist? Timeline, compatibility, dependencies?

Use multiple-choice questions when natural options exist. If the description is already detailed, offer to skip: "Your description is clear. Should I proceed with research?"

---

## Step 2: Research (parallel)

Run these in parallel using the agent instructions from `.ai/agents/researcher.md`:

**Codebase research:**
- Search the repo for existing patterns related to this feature
- Read project config to understand the stack
- Identify conventions and related files

**Learnings research:**
- Search `.ai/docs/solutions/` for previously documented solutions
- Surface any gotchas, warnings, or relevant patterns

**External research (conditional):**
- Only if the task involves unfamiliar APIs, security-sensitive changes, or new technology
- Skip if the codebase has clear patterns to follow

---

## Step 3: Analyze Specification

Use the planner agent (`.ai/agents/planner.md`) approach to:
- Map user flows (happy path, error paths, edge cases)
- Identify gaps in the specification
- Flag technical challenges
- Recommend MVP scope

---

## Step 4: Write the Plan

Create a plan file at: `.ai/docs/plans/YYYY-MM-DD-<type>-<short-description>-plan.md`

**Naming examples:**
- `.ai/docs/plans/2026-02-10-feat-user-auth-flow-plan.md`
- `.ai/docs/plans/2026-02-10-fix-checkout-race-condition-plan.md`
- `.ai/docs/plans/2026-02-10-refactor-api-client-plan.md`

Use the template from `.ai/templates/plan.md` and fill it with:
- Research findings from Step 2
- Specification analysis from Step 3
- Actionable tasks with checkboxes

**Choose the right detail level:**

| Level | When to use | What's included |
|-------|-------------|-----------------|
| **Minimal** | Simple bugs, small changes | Problem + acceptance criteria + context |
| **Standard** | Most features | Above + technical approach + risks + success metrics |
| **Comprehensive** | Major features, architecture changes | Above + phased implementation + alternatives considered |

---

## Step 5: Next Steps

After writing the plan, ask:

> Plan ready at `.ai/docs/plans/[filename]`. What next?
>
> 1. **Start working** — begin implementing this plan
> 2. **Deepen the plan** — research each section further
> 3. **Review and refine** — improve the plan through self-review
> 4. **Create an issue** — push to GitHub/Linear

---

## Rules

- **Never write code** during planning. Research and write the plan only.
- **Date all plans** with today's date in the filename.
- **Reference specific files** (with paths) — don't be vague.
- **Include past learnings** from `docs/solutions/` prominently.
- **Keep it actionable** — every task should be completable and checkboxable.
