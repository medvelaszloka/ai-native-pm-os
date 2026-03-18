# Claude Code Workflows

Your documented patterns for using Claude Code effectively as a PM.

## Overview

Claude Code is your AI-powered terminal companion. This file captures workflows, building blocks, and patterns that work well for your PM work.

---

## The 6 Building Blocks

Claude Code has six core components. Choose based on: *who invokes it*, *where it works*, and *whether it bundles code*.

| Building Block | What It Does | When to Use |
|----------------|--------------|-------------|
| **Markdown Files** | Store persistent context across conversations | Always - your memory layer |
| **Slash Commands** | Named prompts triggered by `/command` | Workflows YOU explicitly invoke |
| **Agents** | Sub-agents with their own context windows | Parallel tasks, research, context preservation |
| **Skills** | Portable bundles (prompts + code) | Cross-platform sharing |
| **Hooks** | Event-driven automation | Deterministic tasks at session start |
| **Plugins** | Shareable packages via GitHub | Team distribution |

---

## Context Management Strategy

### Three-Layered Memory
1. **Global** (`~/.claude/CLAUDE.md`) - Your preferences, style, universal rules
2. **Project** (`.claude/CLAUDE.md`) - Project-specific context, workflows
3. **Referenced files** - Linked in CLAUDE.md, loaded when needed

**Key principle:** Only give Claude what it needs for the current task. Don't overload.

### Context Window Tips
- Claude Code auto-compacts at 75% capacity
- Pre-emptively offload work to sub-agents to avoid interruptions
- Each sub-agent has its own fresh context window

---

## Agent Strategy

### When to Use Sub-Agents
- **Research tasks** - Searching/filtering pollutes your main context
- **Parallel work** - Multiple independent tasks simultaneously
- **Context preservation** - Keep main thread clean for decision-making

### How It Works
- Deploy sub-agents for exploration, fact-checking, analysis
- Results return to main agent without context pollution
- Batch similar parallel tasks for speed (e.g., researching multiple competitors)

**Note:** High token consumption on parallel tasks - use judiciously.

---

## AI-Native PM Practices

From Olivia Meng's analysis of Cursor's PM workflow:

### The 5 Unconventional Practices
1. **Work inside the codebase** - Explore logic, generate diagrams, understand systems
2. **Demos > Memos** - Deliver working demos; specs become supporting material
3. **AI as validator** - Cross-reference code, data, and requirements automatically
4. **Process encoded in tooling** - Team-specific prompts become the process
5. **PM repos as living systems** - Documentation stored and versioned like code

### Key Insight
"The work will increasingly focus on your due diligence and judgment" - automation increases the importance of PM discernment, not decreases it.

Source: [AI-Native PM Article](https://open.substack.com/pub/oliviaxmeng/p/i-cant-unsee-this-what-ai-native)

---

## Your Slash Commands

### Morning Dashboard
```
/today
```
- Generates daily focus dashboard
- Pulls from overnight intelligence
- Shows bet candidates needing action

### Slack Intelligence Collection
```
/capture
```
- Quick capture of important Slack signals
- Auto-categorizes by type
- Feeds into weekly synthesis

### Weekly Synthesis
```
/synthesize
```
- Analyzes past 7 days of intelligence
- Generates bet candidates with evidence
- Cross-references with strategy

### Context Updates
```
/update-context
```
- Run after betting sessions
- Updates living context files
- Makes synthesis smarter over time

---

## Effective Patterns

### Pattern: Quick Research
When you need to understand something fast:
1. Ask Claude to explore the codebase/files
2. Let it synthesize findings
3. Ask follow-up questions

### Pattern: Document Generation
When creating PM artifacts:
1. Provide clear constraints (audience, format, length)
2. Include examples of what you want
3. Iterate with feedback

### Pattern: Analysis Tasks
When analyzing data or patterns:
1. Be specific about what you're looking for
2. Ask for evidence and sources
3. Request structured output

### Pattern: Parallel Research
When exploring multiple topics:
1. Deploy sub-agents for each research thread
2. Let them work in parallel
3. Synthesize results in main context

---

## Tips & Tricks

- **Be direct**: Claude prefers clear, actionable requests
- **Provide context**: Reference relevant files or history
- **Iterate**: Don't expect perfection on first try
- **Use commands**: Slash commands are faster than explaining
- **Offload research**: Use sub-agents to keep your context clean
- **Batch parallel tasks**: Faster than sequential when independent

---

## Decision Matrix

**Need to store persistent info?** → Markdown Files

**Need a repeatable workflow YOU trigger?** → Slash Commands

**Need parallel work or context preservation?** → Agents

**Need cross-platform portability?** → Skills

**Need deterministic automation on events?** → Hooks

**Need to share with team?** → Plugins

---

## Resources

- [ProductTalk: How to Use Claude Code Features](https://www.producttalk.org/how-to-use-claude-code-features/)
- [Claude Code Documentation](https://docs.anthropic.com/claude-code)

---

## My Usage Notes

*Add your own discoveries and patterns here as you use Claude Code*

---

*Last updated: January 25, 2026*
