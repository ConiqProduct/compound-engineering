# /review — Multi-angle code review

Perform a thorough code review from multiple perspectives: architecture, security, performance, simplicity, and pattern consistency.

## Input

A PR number, branch name, or "latest" for the most recent changes.

**If no input**, review the current branch's changes against main/master.

---

## Step 1: Understand the Change

- Get the diff (`git diff main...HEAD` or `gh pr diff`)
- Read the PR description or plan file
- Identify which files changed and what the intent is
- List the affected components

---

## Step 2: Multi-Angle Review

Review the changes from all of these angles (use the approach in `.ai/agents/reviewer.md`):

### Architecture
- Do changes align with existing architecture?
- Component boundaries respected?
- No new circular dependencies?
- Separation of concerns maintained?

### Security
- All user inputs validated?
- No hardcoded secrets?
- Endpoints properly authenticated?
- No injection risks (SQL, XSS, command)?
- Error messages don't leak sensitive info?

### Performance
- No O(n²) algorithms without justification?
- No N+1 queries?
- No unbounded data structures?
- Appropriate caching where needed?
- Bundle size impact reasonable?

### Simplicity (YAGNI)
- Can any code be removed?
- Are there premature abstractions?
- Is there dead code or unused imports?
- Could complex logic be simplified?

### Pattern Consistency
- Follows existing naming conventions?
- File structure is consistent?
- Similar problems solved the same way?

---

## Step 3: Synthesize Findings

Categorize all findings by severity:

| Severity | Meaning | Action |
|----------|---------|--------|
| **Critical** | Security vulnerability, data loss risk, breaking change | Must fix before merge |
| **Important** | Performance issue, architectural concern, significant quality problem | Should fix |
| **Minor** | Style improvement, minor optimization, documentation | Nice to have |

---

## Step 4: Present Results

```markdown
## Review Summary

**Change**: [brief description]
**Risk Level**: [Low / Medium / High]
**Verdict**: [Approve / Request Changes / Needs Discussion]

### Critical (blocks merge)
- [issue]: [description + file:line] → [fix]

### Important (should fix)
- [issue]: [description + file:line] → [fix]

### Minor (nice to have)
- [issue]: [description + file:line] → [fix]

### What looks good
- [positive observations]
```

---

## Step 5: Next Steps

After presenting findings:

> Review complete. What next?
>
> 1. **Fix critical issues** — address blockers now
> 2. **Fix all issues** — address everything found
> 3. **Discuss** — talk through specific findings
> 4. **Approve as-is** — proceed despite findings

---

## Rules

- **Be specific**: Always include file paths and line numbers
- **Be actionable**: Every finding needs a suggested fix
- **Be proportional**: Thorough on large PRs, light on small ones
- **Prioritize**: Security and data issues first, style nits last
- **Acknowledge good work**: Note what's done well
- **Never flag** `docs/plans/` or `docs/solutions/` files for removal — these are knowledge artifacts
