# AI-Native PM OS

A Claude Code-powered operating system for product managers running Shape Up cycles. Collects signals, synthesizes patterns, generates evidence-based bet candidates, and learns from past decisions.

Built and used daily by [Bence Damjanovics](https://github.com/medvelaszloka), PM building with AI.

## What This Does

**Problem:** Information about what to build is scattered across Slack, meetings, and docs. Synthesizing this into clear bets for 6-week cycles takes hours.

**Solution:** An automated intelligence layer powered by Claude Code that:
1. **Collects** signals from Slack throughout the week
2. **Synthesizes** patterns weekly with evidence-based analysis
3. **Generates** bet candidates validated against strategy
4. **Learns** from past decisions and outcomes over time

Inspired by Teresa Torres' Continuous Discovery framework and Shape Up by Basecamp.

## How It Works

### 6 Slash Commands

| Command | What It Does | When to Use |
|---------|-------------|-------------|
| `/today` | Morning dashboard with priorities, overnight intelligence, active bets | Every morning |
| `/capture` | Quick Slack signal capture with auto-categorization | When you spot important signals |
| `/synthesize` | Weekly bet candidate generation from collected intelligence | Every Friday |
| `/update-context` | Update living context after betting sessions | After choosing bets |
| `/note` | Quick thought capture with smart tagging | Throughout the day |
| `/todo` | Task management with due dates and auto-categorization | When tasks come up |

### The Learning Loop

```
Week 1: Collect signals -> Synthesize -> Choose bets -> Update context
Week 2: Collect signals -> Synthesize (now references Week 1 decisions)
Week 3: Collect signals -> Synthesize (learns from Weeks 1-2)
Week 4+: System gets increasingly intelligent about your product
```

### Living Context System

4 files that give Claude persistent memory across conversations:

| File | Purpose | Update When |
|------|---------|-------------|
| `strategy-current.md` | Current priorities, strategic shifts | Quarterly + pivots |
| `decisions-log.md` | Major decisions with rationale | After betting sessions |
| `bets-rationale.md` | Active, past, and rejected bets | Weekly + cycle ends |
| `learnings.md` | Product wisdom and patterns | After bets complete |

## Directory Structure

```
ai-native-pm-os/
├── .claude/                    <- Claude Code configuration
│   ├── CLAUDE.md               <- Global instructions
│   └── commands/               <- 6 slash commands
├── templates/                  <- All templates (dashboards, synthesis, bets)
├── context/
│   ├── living/                 <- Living Context System (4 files)
│   ├── ai-tools/              <- AI workflow documentation
│   ├── company/               <- Your team's process (customize this)
│   └── pm-skills/             <- Communication style guide
├── intelligence/               <- Signal collection & analysis
│   ├── slack-daily/            <- Daily Slack captures
│   ├── synthesis-weekly/       <- Weekly synthesis reports
│   ├── f2f-meetings/          <- Meeting intelligence
│   ├── patterns/              <- Pattern analysis
│   └── research/              <- Deep-dive research
├── bets/
│   └── candidates/            <- Generated bet pitches
├── daily/                     <- Morning dashboards
├── notes/                     <- Quick notes
├── meetings/                  <- Meeting notes
└── todos.md                   <- Task list
```

## Getting Started

### Prerequisites
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed
- A text editor (Obsidian recommended for wiki-links, but any editor works)

### Setup (15 minutes)

1. **Fork this repo** and clone it locally

2. **Customize your context:**
   - `context/company/betting-process.md` -- your team's Shape Up process, stakeholders, betting table
   - `context/pm-skills/communication-style.md` -- your writing style so Claude matches your voice
   - `context/living/strategy-current.md` -- your current quarterly priorities

3. **Test it:**
   ```bash
   cd ai-native-pm-os
   claude
   # Then type: /today
   ```

4. **Start collecting:** Use `/capture` when you see important Slack messages this week

5. **Run your first synthesis:** `/synthesize` on Friday

### Daily Routine (5 minutes)

**Morning:** `/today` to get your dashboard

**During the day:** `/capture` for signals, `/note` for thoughts, `/todo` for tasks

### Weekly Routine (30 minutes)

**Friday:** `/synthesize` to generate bet candidates

**After betting session:** `/update-context` to capture decisions

## What to Customize First

1. **`context/company/betting-process.md`** -- Replace placeholders with your team's actual process, stakeholders, and Slack channels
2. **`context/living/strategy-current.md`** -- Add your current quarterly priorities
3. **`context/pm-skills/communication-style.md`** -- Add examples of your writing so Claude matches your voice

## The AI Tools Playbook

The `context/ai-tools/` folder contains reusable frameworks for AI-assisted PM work:
- **Claude Code Workflows** -- Building blocks, context strategy, agent patterns
- **Prompting Frameworks** -- Effective prompts for PM tasks
- **Tool Selection Guide** -- When to use which AI tool

These work independently of the rest of the system.

## Built With

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) -- AI coding agent with slash commands
- [Shape Up](https://basecamp.com/shapeup) -- Product development methodology
- [Continuous Discovery](https://www.producttalk.org/2021/08/continuous-discovery-habits/) -- Teresa Torres' framework
- Markdown -- All files are plain text, no vendor lock-in

## License

MIT
