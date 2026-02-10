# Compound Engineering

> Each unit of engineering work should make subsequent units easier — not harder.

A project-agnostic AI workflow system for engineers. Add it to any project and get structured workflows: **Plan → Work → Review → Compound**.

Works with Cursor, Claude Code, GitHub Copilot, Codex, or any AI assistant that can read markdown.

---

## Quick install

Add to **any existing project** (one command):

```bash
cd your-project
git clone https://github.com/ConiqProduct/compound-engineering.git .ai
```

That’s it. The `.ai` folder is now in your project. Plans go in `docs/plans/`, solutions in `docs/solutions/`.

### New project from scratch

```bash
mkdir my-app && cd my-app
git init
git clone https://github.com/ConiqProduct/compound-engineering.git .ai
# Start building — .ai is ready from day one
```

### Optional: Make Cursor use it automatically

Add a rule in `.cursor/rules/compound-engineering.mdc` (or your project's rules):

```
When the user says "plan", "work", "review", or "compound", use the corresponding workflow from .ai/commands/ in this project. Reference .ai/agents/ for sub-agent behavior when doing parallel research or review.
```

---

## The Loop

```
Plan → Work → Review → Compound → Repeat
```

| Phase        | What happens                                          |
|-------------|-------------------------------------------------------|
| **Plan**    | Research the codebase, gather context, write a plan   |
| **Work**    | Execute the plan systematically, test as you go        |
| **Review**  | Multi-angle code review (security, perf, architecture)|
| **Compound**| Document what you learned so future work is faster    |

---

## Folder structure

```
.ai/
├── README.md           ← You are here
├── commands/           ← The 4 core workflows
│   ├── plan.md         ← Turn ideas into actionable plans
│   ├── work.md         ← Execute plans systematically
│   ├── review.md       ← Multi-angle code review
│   └── compound.md     ← Document learnings
├── agents/             ← Specialized sub-agent instructions
│   ├── researcher.md   ← Gathers context from codebase + past learnings
│   ├── reviewer.md     ← Reviews code for quality, security, performance
│   └── planner.md      ← Analyzes specs for gaps and edge cases
├── templates/          ← File templates
├── tutorial/           ← Full HTML tutorial
└── docs/               ← Living knowledge base (grows over time)
    ├── plans/          ← Implementation plans
    └── solutions/      ← Documented solutions
```

---

## The compounding effect

The magic is in `docs/solutions/`. Every time you solve a non-trivial problem:

1. **First time**: Research, debug, figure it out (30+ min)
2. **Document it**: Capture the problem, root cause, and fix (5 min)
3. **Next time**: AI searches `docs/solutions/` and finds the answer (2 min)

Knowledge compounds. The codebase gets easier to work with over time, not harder.

---

## Tutorial

**[Open the full tutorial →](tutorial/index.html)** — An HTML guide that walks through the workflow, all four phases, and how to use this with AI assistants.

---

## Philosophy

- **80% planning and review, 20% execution** — think before you code
- **Follow existing patterns** — search the codebase before inventing new ones
- **Test as you go** — don’t wait until the end
- **Document non-trivial fixes** — your future self will thank you
- **YAGNI** — build what you need now, not what you might need later

---

## License

MIT
