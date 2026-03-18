# first-principles-thinking

A Claude Code skill that forces decomposition to fundamental facts before reasoning — not analogy, convention, or "how others do it."

## What It Does

When you face any analysis, design, debugging, or decision task, this skill enforces a structured four-step process:

1. **Identify assumptions** — list everything you're taking for granted
2. **Ask "why" (3+ layers)** — challenge each assumption at its root
3. **Restore basic facts** — what remains after stripping all assumptions?
4. **Rebuild from zero** — derive the optimal solution from those facts, not from history

## When to Use

Invoke this skill when:

- Analyzing a problem or bug
- Making architectural or design decisions
- Explaining a concept to others
- Debugging unexpected behavior
- Evaluating technology choices

## Installation

Copy `SKILL.md` into your `.claude/skills/first-principles-thinking/` directory:

```bash
mkdir -p .claude/skills/first-principles-thinking
cp SKILL.md .claude/skills/first-principles-thinking/
```

Or install globally (available across all projects):

```bash
mkdir -p ~/.claude/skills/first-principles-thinking
cp SKILL.md ~/.claude/skills/first-principles-thinking/
```

## Usage

In Claude Code, invoke with the Skill tool:

```
/first-principles-thinking
```

Or reference it in your `CLAUDE.md`:

```markdown
Before any technical analysis or design decision, invoke the first-principles-thinking skill.
```

## Key Principles

### Forbidden Thinking Patterns

| Pattern | Why harmful | Replace with |
|---------|-------------|--------------|
| "Industry standard is X" | Convention may be outdated or wrong for your constraints | Verify the constraint exists in your context |
| "We solved it with X last time" | Context differs; solutions don't transfer directly | Re-analyze current constraints |
| "Framework Y does it this way" | Frameworks have their own constraints | Identify the core problem the framework solves |
| "Experts say you should" | Expert advice is based on their constraints | Understand the preconditions behind the advice |
| "Just ship it, fix later" | Wrong direction compounds exponentially | Define problem boundaries first |

### Red Flags (Stop and Re-derive)

If you catch yourself thinking:

- "This is obviously an X-type problem..."
- "Just follow [product/paper/framework]"
- "I know this domain, no need to analyze"
- "Time pressure, use the standard approach"

**Time pressure is not a reason to skip analysis.** Fast execution in the wrong direction wastes more time than slow derivation.

## Quick Reference

```
What is the actual problem? (Not the symptom — the root contradiction)
    ↓
What are the constraints? (Physical / logical / resource)
    ↓
What is the ideal solution if constraints didn't exist?
    ↓
Which constraints are real vs. "we've always done it this way"?
    ↓
What is the closest-to-ideal solution under real constraints?
```

## License

MIT
