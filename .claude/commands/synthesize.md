# Synthesize Command

Analyze all collected intelligence and generate bet candidates with evidence, informed by living context from past decisions and strategy.

## What to do:

### STEP 1: Load Living Context FIRST

**Read all 4 living context files** (fail gracefully if they don't exist or are empty):
- `context/living/strategy-current.md`
- `context/living/decisions-log.md`
- `context/living/bets-rationale.md`
- `context/living/learnings.md`

**Extract and store:**
- Current strategic priorities (Q# goals)
- Recent strategic shifts (last 30 days)
- Recent decisions (last 30 days) and their rationale
- Active bets and their status (current cycle)
- Past bets and outcomes (what worked/didn't)
- Rejected bets and why
- Documented learnings and patterns

**If files don't exist or are empty:** Continue without them, but note in output: "⚠️ No living context found - synthesis based on intelligence only"

### STEP 2: Scan Intelligence Sources

**Read intelligence from past 7 days:**
- `intelligence/slack-daily/*.md` (primary source)
- `intelligence/analytics/*.md` (if exists)
- `intelligence/meeting-notes/*.md` (if exists)
- `intelligence/research/*.md` (if exists)

**Count and track:**
- Total signals collected
- Date range covered
- Sources represented

### STEP 3: Pattern Analysis (Enhanced with Living Context)

**Identify patterns across intelligence:**
- Look for repeated themes across multiple days
- Count frequency of each theme
- Identify trends (increasing/stable/decreasing)
- Note which stakeholders are discussing what

**Cross-reference with living context:**
- Does this pattern relate to current strategic priorities?
- Have we seen this pattern before? (check learnings.md)
- Did we try addressing this before? (check bets-rationale.md)
- Is there a past decision that's relevant? (check decisions-log.md)

**Pattern strength rating:**
- ⭐⭐⭐⭐⭐ (5 stars) = 5+ mentions, multiple sources, strategic alignment
- ⭐⭐⭐⭐ (4 stars) = 3-4 mentions, multiple sources
- ⭐⭐⭐ (3 stars) = 3 mentions, single source or emerging theme
- ⭐⭐ (2 stars) = 2 mentions, needs validation
- ⭐ (1 star) = Single mention, worth tracking

### STEP 4: Generate Smart Bet Candidates

**For HIGH confidence patterns** (3+ mentions, multiple sources):

Create detailed bet candidate and evaluate against living context:

**Strategy Alignment Check:**
- Rate: ⭐⭐⭐⭐⭐ (5 stars = perfect alignment, 1 star = diverges)
- Explain: "Directly supports [specific priority from strategy-current.md]"
- OR flag: "⚠️ Diverges from current strategy focus on [X], but worth considering because..."

**Learning from Past:**
- Have we tried something similar? (check bets-rationale.md)
- What did we learn? (reference learnings.md)
- What are we doing differently? (show evolution)
- Any relevant decisions? (reference decisions-log.md)

**Check Against Active Work:**
- Does this complement active bets?
- Does this conflict with current cycle work?
- Recommend: "Pursue now" OR "Defer to Cycle [X] because..."

**For EMERGING patterns** (2 mentions):
- List in "Additional Observations" section
- Note what's needed to make it bet-worthy
- Track for next synthesis

### STEP 5: Create Enhanced Synthesis Report

**File location:** `intelligence/synthesis-weekly/[YYYY-MM-DD]-synthesis.md`

**Use this exact format:**

```markdown
# Weekly Synthesis - [Week of Date]

## 📋 Context Check
*What I know from living context*

### Current Strategy
**From:** context/living/strategy-current.md
**Last updated:** [date from file]

**Q[#] 2026 Priorities:**
- [Priority 1]: [brief context]
- [Priority 2]: [brief context]
- [Priority 3]: [brief context]

**Recent Strategic Shifts:**
- [Date]: [what changed and why]

*[If file empty/missing: "⚠️ No current strategy documented"]*

### Recent Decisions
**From:** context/living/decisions-log.md

*Decisions from the past 30 days that inform this week's synthesis:*
- [Date]: [Decision title] - [1-line why it matters]
- [Date]: [Decision title] - [1-line why it matters]

*[If none: "No recent decisions logged"]*

### Active Bets
**From:** context/living/bets-rationale.md

**Current Cycle [#]:**
- [Bet 1]: Week [X] of [Y] - [appetite]
- [Bet 2]: Week [X] of [Y] - [appetite]

*[If none: "No active bets tracked"]*

### Relevant Learnings
**From:** context/living/learnings.md

*Learnings that apply to this week's signals:*
- [Learning title]: [why it's relevant now]

*[If none: "No documented learnings yet"]*

---

## 📊 Intelligence This Week
*Patterns identified from past 7 days*

**Intelligence scanned:**
- [X] files from intelligence/slack-daily/
- [X] files from intelligence/analytics/
- [X] files from intelligence/meeting-notes/
- [X] files from intelligence/research/
- **Date range:** [oldest] to [newest]
- **Total signals:** [count]

### Pattern 1: [Pattern Name]
**Strength:** ⭐⭐⭐⭐ (4/5)

**What we're seeing:**
[Description of pattern - 2-3 sentences]

**Evidence:**
- 📊 Analytics: [specific finding with date]
- 💬 Slack: [signal with date and source]
- 🤝 Meeting: [input with date]
- 🔬 Research: [discovery with date]

**Frequency:** Seen [X] times across [Y] days

**Living Context Connection:**
- [How this relates to strategy/past decisions/learnings]

[Repeat for each major pattern...]

---

## 🎲 Bet Candidates

### Bet #1: [Name]

**Strategy Alignment:** ⭐⭐⭐⭐⭐ (5/5)
- Directly supports: [specific priority from strategy-current.md]
- Aligns with strategic shift: [recent shift if applicable]
- OR: ⚠️ Diverges from [priority], but valuable because: [reason]

**Learns From Past:**
- Similar to: [past bet name from Cycle X] - [outcome]
- Key learning applied: [specific learning from learnings.md]
- What we're doing differently: [evolution from past attempt]
- Informed by decision: [relevant decision from decisions-log.md]
- OR: First time addressing this - no past precedent

**Check Against Active Work:**
- Complements: [active bet name] - [how they work together]
- OR: ⚠️ Conflicts with: [active bet] - Recommend: [defer/pursue with caution]
- Recommendation: **Pursue now** | **Defer to Cycle [X]**

**Evidence Strength:** ⭐⭐⭐⭐ (4/5)
- 📊 Analytics: [specific data point - source and date]
- 💬 Slack: [X customer mentions - dates and channels]
- 🤝 Meeting: [stakeholder input - who and when]
- 🔬 Research: [findings - source and date]

**Problem:**
[Clear problem statement - 2-3 sentences max]

**Appetite:** [2 weeks | 6 weeks]
[1 sentence explaining why this appetite]

**Solution:**
[High-level solution approach - 3-4 bullet points max]

**Rabbit Holes:**
[Potential scope creep to avoid - 2-3 bullets]

**No-Gos:**
[Explicitly out of scope - 2-3 bullets]

**Expected Outcome:**
[Specific, measurable success criteria - 2-3 bullets]

**Evidence Sources:**
- [[link to slack-daily file 1]]
- [[link to slack-daily file 2]]
- [[link to analytics file if applicable]]

---

[Repeat for each HIGH confidence bet candidate...]

---

## 🚩 Flags & Tensions

*Things worth discussing with stakeholders*

### Tension 1: [Description]
- **The conflict:** [Intelligence suggests X, but strategy says Y]
- **Why this matters:** [Impact of this tension]
- **Context from living memory:** [Related past decision or learning]
- **Recommendation:** [What to do - discuss with team/pivot strategy/wait for more data]

[Repeat for other tensions...]

*[If none: "No major tensions identified this week"]*

---

## 💭 Additional Observations

*Signals that don't warrant full bet candidates yet but worth tracking*

### Emerging Pattern: [Name] (⭐⭐)
- **What we're seeing:** [Description]
- **Frequency:** [X mentions]
- **What's needed:** [To make this bet-worthy - more evidence/stakeholder input/etc]
- **Track for:** Next synthesis

[Repeat for other emerging patterns...]

---

## 📈 Recommended Next Steps

1. **Bet candidates ready for pitching:** [list bet names]
2. **Tensions to discuss:** [list tension topics]
3. **Emerging patterns to track:** [list pattern names]
4. **Intelligence gaps to fill:** [what's missing - more customer data/analytics/etc]

---

*Generated by /synthesize command*
*Living context version: [timestamp]*
*Intelligence analyzed: [date range]*
```

### STEP 6: Output to User

After creating synthesis file, print:

```
✅ Weekly synthesis complete!

**Living Context Loaded:**
- Strategy: [✓ Loaded | ⚠️ Empty | ✗ Not found]
- Decisions: [✓ Loaded | ⚠️ Empty | ✗ Not found]
- Bets: [✓ Loaded | ⚠️ Empty | ✗ Not found]
- Learnings: [✓ Loaded | ⚠️ Empty | ✗ Not found]

**Intelligence Analyzed:**
- [X] files scanned
- [X] signals analyzed
- [X] patterns identified

**Bet Candidates Generated:** [count]
1. [Bet name] - Strategy alignment: [stars] - Evidence: [stars]
2. [Bet name] - Strategy alignment: [stars] - Evidence: [stars]

**Synthesis saved to:** intelligence/synthesis-weekly/[date]-synthesis.md

**Next steps:**
- Review bet candidates for next betting session
- Address flagged tensions with stakeholders
- Track emerging patterns for next synthesis
```

---

## Analysis Criteria (Enhanced):

**High-confidence bet signals (warrant full bet candidate):**
- Mentioned 3+ times across multiple days
- Multiple stakeholder types (customer + internal)
- Strategic alignment confirmed (via strategy-current.md)
- Technical feasibility discussed
- Business impact quantified or strongly implied
- No conflicts with active work OR conflict is addressable

**Emerging pattern signals (list in observations):**
- Mentioned 2 times
- Single stakeholder type
- Needs more validation
- May conflict with current priorities

**Red flags (call out in tensions section):**
- Intelligence contradicts current strategy
- Conflicts with recent decisions
- Repeats a failed past bet without new approach
- Competes with active bets for resources

---

## Special Cases:

**If living context is empty/missing:**
- Note this in Context Check section
- Continue with intelligence analysis
- Still generate bet candidates but mark: "⚠️ Not validated against strategy - recommend review"
- Suggest: "Consider running /update-context to build living memory"

**If no intelligence found:**
- Report: "No intelligence files found in past 7 days"
- Suggest: "Run /capture to collect Slack intelligence first"

**If patterns conflict with strategy:**
- Always call this out in Flags & Tensions
- Provide recommendation: update strategy OR wait for more evidence OR reject signal

---

## Tone:
- Evidence-based and analytical
- Clear confidence levels with star ratings
- Explicit connections to living context
- Actionable recommendations
- Link to all supporting intelligence
- Flag tensions directly (don't hide conflicts)

---

## Quality Checklist:

Before finalizing synthesis, verify:
- [ ] All 4 living context files attempted to load
- [ ] Living context status shown in output
- [ ] Every bet candidate has strategy alignment rating
- [ ] Every bet candidate checked against past work
- [ ] Every bet candidate checked against active work
- [ ] All evidence has sources and dates
- [ ] Tensions are explicitly called out
- [ ] File saved to intelligence/synthesis-weekly/
- [ ] User summary printed
