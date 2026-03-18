# Living Context System

The Living Context system gives Claude persistent memory of your product strategy, decisions, bets, and learnings. This makes synthesis and bet generation smarter over time by learning from past decisions and outcomes.

## The 4 Files

### strategy-current.md
**What goes here:** Current quarterly priorities and recent strategic shifts (last 30 days).

Update this when quarterly planning completes, executive decisions change priorities, or major strategic pivots occur. This is the "current truth" that informs all bet decisions.

### decisions-log.md
**What goes here:** Major product decisions with full context - what was decided, why, what alternatives were considered, and what impact it had.

Update this after betting sessions (which bets chosen/rejected), major feature decisions (build vs. buy vs. defer), strategic pivots, and resource allocation decisions. This helps avoid revisiting settled decisions.

### bets-rationale.md
**What goes here:** All bets over time - active bets with status, past bets with outcomes, and rejected bets worth tracking.

Update this when betting sessions complete (add chosen and rejected bets), when cycles end (move active to past with learnings), and weekly during active cycles (update status).

### learnings.md
**What goes here:** Accumulated wisdom from building products - what worked, what didn't, and recurring patterns.

Update this when bets complete (what we learned), after betting sessions (decision-making insights), when patterns emerge from customer feedback, and when unexpected discoveries happen.

---

## Weekly Workflow

1. **Capture intelligence** → Use `/capture` throughout the week to log Slack signals
2. **Synthesize** → Run `/synthesize` weekly to generate bet candidates (reads living context first)
3. **Betting session** → Review synthesis, choose bets with your team
4. **Update context** → Run `/update-context` to capture decisions and learnings

The system gets smarter with each cycle as living context accumulates.

---

## When to Update Each File

| File | Update Trigger | Frequency |
|------|---------------|-----------|
| `strategy-current.md` | Quarterly planning, strategic pivots | Quarterly + as needed |
| `decisions-log.md` | Betting sessions, major decisions | After each betting session |
| `bets-rationale.md` | Betting sessions, cycle ends | Weekly during cycle + cycle end |
| `learnings.md` | Completed bets, discoveries | After bets complete + ongoing |

---

## Commands Reference

### `/update-context`
**Use after:** Betting sessions or major strategic events

Asks you 6 questions conversationally, then updates the appropriate living context files based on your answers. Handles the tedious work of formatting and filing information correctly.

**Example flow:**
```
You: /update-context
Claude: What event or meeting just happened?
You: Cycle 4 betting session
Claude: Did any strategic priorities change? If yes, what changed? If no, type 'skip'
[... continues through 6 questions ...]
Claude: ✅ Living context updated! [shows summary]
```

### `/synthesize`
**Use:** Weekly to generate bet candidates from intelligence

Reads all 4 living context files first, then analyzes intelligence from the past 7 days. Every bet candidate is evaluated against current strategy, past decisions, active work, and documented learnings. Creates a synthesis report in `intelligence/synthesis-weekly/`.

**Output includes:**
- Context Check (what it knows from living context)
- Pattern analysis from intelligence
- Bet candidates with strategy alignment ratings
- Flags & tensions (when intelligence conflicts with strategy)

---

## Example Entries

### strategy-current.md
```markdown
## Current Quarter Priorities
1. **Increase enterprise adoption** - Focus on features that reduce implementation time
2. **Improve mobile experience** - 40% of users now mobile-first
3. **Strengthen analytics offering** - Key differentiator vs competitors

## Recent Strategic Shifts
- **2026-01-15**: Shifted from SMB to enterprise focus
  - Why: Enterprise customers have 10x LTV and better retention
  - Impact: All bets should consider enterprise use cases first
  - Source: Board meeting + Q4 data review
```

### decisions-log.md
```markdown
## 2026-01-20: Prioritize mobile dashboard over desktop redesign
**Decision:** Build mobile dashboard for Cycle 4, defer desktop redesign to Cycle 5
**Rationale:**
- 40% of users now mobile-first (up from 25% last quarter)
- Enterprise clients specifically requested mobile access
- Desktop works well enough, mobile is a gap

**Alternatives considered:**
- Desktop redesign first - Why rejected: Less urgent based on usage data
- Build both - Why rejected: Exceeds 6-week appetite

**Evidence:**
- Analytics showing 40% mobile traffic
- 8 customer requests in past 2 weeks

**Impact:**
- Mobile team can focus fully on dashboard
- Desktop redesign pushed to Q2

**Sources:**
- [[2026-01-18-synthesis]]
- Cycle 4 betting session
```

### bets-rationale.md
```markdown
## Active Bets (Current 6-week cycle)

### Mobile Analytics Dashboard (Cycle 4, 2026)
- **Appetite:** 6 weeks
- **Why we chose it:** 40% of users mobile-first, 8 customer requests, aligns with enterprise strategy
- **Expected outcome:** Mobile users can view key metrics without desktop access
- **Status:** Week 2 of 6
- **Bet pitch:** [[mobile-dashboard-bet]]

---

## Past Bets

### Automated Report Exports (Cycle 3, 2026) - ✅ Success
- **Original rationale:** Customers spending 2+ hours/week on manual exports
- **Actual outcome:** 85% adoption, average time saved 90 minutes/week
- **Learning:** Export features have high ROI for minimal effort
- **Would we bet on this again?** Yes - look for similar "time saver" opportunities

---

## Rejected Bet Candidates (Worth Tracking)

### Advanced Filtering System - Rejected 2026-01-20
- **Why rejected:** Good idea but conflicts with mobile dashboard work (same team)
- **Alternative chosen instead:** Mobile Analytics Dashboard
- **Revisit when:** Cycle 5 after mobile dashboard ships
```

### learnings.md
```markdown
## 2026-01 Learnings

### Time-saver features have outsized impact
- **Situation:** Built Automated Report Exports in Cycle 3
- **Discovery:** 85% adoption within 2 weeks, saved users 90 min/week average
- **Why it matters:** Small features that save time get immediate adoption and create goodwill
- **Action:** Look for other "time saver" opportunities in synthesis
- **Source:** Cycle 3 retrospective

### Mobile users are a distinct segment
- **Situation:** Analyzed usage patterns for mobile dashboard bet
- **Discovery:** Mobile users behave differently - shorter sessions, different features used
- **Why it matters:** Can't just make desktop responsive, need mobile-first thinking
- **Action:** Consider mobile use cases separately in future bets
- **Source:** [[2026-01-18-synthesis]]

---

## Recurring Patterns

### Pattern: Scope creep in "simple" features
- **Seen in:** User permissions (Cycle 1), Dashboard widgets (Cycle 2), Report exports (Cycle 3)
- **The pattern:** Features that seem simple expand when we discover edge cases
- **Root cause:** Not defining "No-Gos" clearly enough in bet pitches
- **How to avoid:** Always include explicit No-Gos section in every bet pitch
```

---

## Getting Started

**First time setup:**

1. **Populate strategy-current.md** with your current Q# priorities
2. **Run `/update-context`** after your next betting session to start building history
3. **Run `/synthesize`** weekly - it will get smarter as context accumulates

**Week 1:** Living context is empty → synthesis works from intelligence alone
**Week 2+:** Context accumulates → synthesis references strategy, decisions, past bets
**Month 2+:** Rich context → synthesis avoids past mistakes, builds on successes

The system learns as you use it.

---

## Success Metrics

You'll know the system is working when:

- ✅ `/synthesize` explicitly references your current strategy in bet candidates
- ✅ Bet candidates mention past similar attempts and learnings
- ✅ Tensions are flagged when intelligence contradicts strategy
- ✅ You avoid re-discussing decisions you've already made
- ✅ New team members can read living context and understand your product direction
- ✅ Betting sessions are faster because context is already documented

---

## Troubleshooting

**Problem:** `/synthesize` shows "⚠️ No living context found"
**Solution:** Run `/update-context` to populate the files, or manually add content to strategy-current.md

**Problem:** Bet candidates don't reference strategy
**Solution:** Ensure strategy-current.md has content in the "Current Quarter Priorities" section

**Problem:** Too much information, hard to maintain
**Solution:** Focus on the essentials. Each file should be scannable in 2-3 minutes. Archive old content quarterly.

**Problem:** Forgot to update after betting session
**Solution:** Add "Run /update-context" as the last step in your betting session agenda

---

*Living Context System v1.0*
*Part of PM OS powered by Claude Code*
