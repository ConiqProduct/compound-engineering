# /work — Execute plans systematically

Take a plan file and execute it, shipping a complete feature with quality.

## Input

A path to a plan file (from `/plan`), a specification, or a task description.

**If no input**, ask: "Which plan should I work on?" and list files in `.ai/docs/plans/`.

---

## Phase 1: Quick Start

### 1. Read and Understand

- Read the plan file completely
- Review any referenced files or links
- If anything is unclear, ask clarifying questions **now** — better to ask than build the wrong thing
- Get user approval to proceed

### 2. Set Up Branch

Check the current branch:

- **If already on a feature branch**: Ask "Continue on `[branch]`, or create a new one?"
- **If on main/master**: Create a feature branch with a meaningful name

```bash
git checkout -b feat/short-description
# or: fix/short-description, refactor/short-description
```

### 3. Create Task List

Break the plan into actionable tasks:
- Include dependencies between tasks
- Prioritize what needs to be done first
- Include testing tasks
- Keep tasks specific and completable

---

## Phase 2: Execute

### Task Loop

For each task in priority order:

1. Mark task as in-progress
2. Read any referenced files from the plan
3. Look for similar patterns in the codebase
4. Implement following existing conventions
5. Write tests for new functionality
6. Run tests after changes
7. Mark task as completed
8. Check off the corresponding `[ ]` in the plan file (in `.ai/docs/plans/`)
9. Evaluate for incremental commit

### Incremental Commits

| Commit when... | Don't commit when... |
|----------------|---------------------|
| Logical unit complete (model, service, component) | Small part of a larger unit |
| Tests pass + meaningful progress | Tests failing |
| About to switch contexts (backend → frontend) | Would need a "WIP" message |

```bash
# Stage only related files (not `git add .`)
git add <related files>
git commit -m "feat(scope): description of this unit"
```

### Follow Existing Patterns

- The plan should reference similar code — read those files first
- Match naming conventions exactly
- Reuse existing components and utilities
- When in doubt, search for similar implementations

### Test Continuously

- Run relevant tests after each significant change
- Don't wait until the end to test
- Fix failures immediately
- Add new tests for new functionality

---

## Phase 3: Quality Check

Before creating a PR:

- [ ] All tasks marked completed
- [ ] All plan checkboxes checked off
- [ ] Tests pass
- [ ] Linting passes
- [ ] Code follows existing patterns
- [ ] No console errors or warnings

**For complex or risky changes**, consider running a review using the reviewer agent approach (`.ai/agents/reviewer.md`):
- Security-sensitive changes
- Performance-critical code paths
- Large refactors affecting many files

---

## Phase 4: Ship It

### 1. Final Commit

```bash
git add .
git status          # Review what's being committed
git diff --staged   # Check the changes
git commit -m "feat(scope): what and why"
```

### 2. Create Pull Request

```bash
git push -u origin HEAD

gh pr create --title "feat: [Description]" --body "## Summary
- What was built
- Why it was needed
- Key decisions made

## Testing
- Tests added/modified
- Manual testing performed
"
```

### 3. Notify

- Summarize what was completed
- Link to PR
- Note any follow-up work needed

---

## Key Principles

- **Start fast, execute faster** — clarify once at the start, then build
- **The plan is your guide** — follow referenced patterns, don't reinvent
- **Test as you go** — continuous testing prevents big surprises
- **Ship complete features** — finish what you start, don't leave things 80% done
- **Commit incrementally** — small focused commits, not one giant commit

## Common Pitfalls

- **Analysis paralysis** — read the plan and execute, don't overthink
- **Skipping clarifying questions** — ask now, not after building the wrong thing
- **Ignoring plan references** — the plan links to files for a reason
- **Testing at the end** — test continuously or suffer later
- **80% done syndrome** — finish the feature, don't move on early
