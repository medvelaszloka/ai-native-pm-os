# Prompting Frameworks

Effective prompts and approaches for AI-assisted PM work.

---

## Core Principles

### 1. Be Specific
Bad: "Help me with this bet"
Good: "Draft a 6-week appetite bet pitch for mobile analytics dashboard based on the 3 customer requests in this week's synthesis"

### 2. Provide Context
Bad: "Write a Slack message"
Good: "Write a Slack message to the design team requesting feedback on the dashboard mockups. Tone should be collaborative, not urgent. Tag Sarah and Mike."

### 3. Define Output Format
Bad: "Summarize this feedback"
Good: "Summarize this feedback as: 1) Key themes (3-5 bullets), 2) Quotes to use, 3) Gaps to investigate"

### 4. Include Constraints
Bad: "Make this better"
Good: "Make this executive summary shorter (max 3 paragraphs) while keeping the business impact clear"

---

## PM-Specific Prompts

### Bet Candidate Analysis
```
Analyze this signal for bet potential:
- Customer demand evidence (1-5)
- Strategic alignment (1-5)
- Feasibility concerns
- Similar past attempts
- Recommended appetite (2-week or 6-week)
```

### Stakeholder Communication
```
Write a [Slack message/email/update] to [audience] about [topic].
Tone: [collaborative/urgent/celebratory/informative]
Include: [specific points]
Avoid: [what not to say]
Length: [short/medium/detailed]
```

### Meeting Prep
```
Prepare me for a meeting about [topic] with [attendees].
Give me:
1. Key questions to ask
2. Potential objections and responses
3. Decision points to drive toward
4. Context I should review first
```

### Synthesis Request
```
Review [these files/this data] and identify:
1. Patterns (what keeps coming up)
2. Tensions (conflicting signals)
3. Gaps (what's missing)
4. Recommendations (what to do next)
```

---

## Framework: RICE for Prompts

**R**ole: Who should Claude be?
**I**nput: What information does it have?
**C**onstraints: What limits apply?
**E**xpected output: What format/length?

Example:
```
Role: You're a senior PM reviewing bet candidates
Input: This week's synthesis report (attached)
Constraints: We can only pick 2 bets, max 6-week appetite each
Expected output: Ranked list with rationale for top 3, reasons to reject others
```

---

## Anti-Patterns to Avoid

- **Vague requests**: "Make it better" → Be specific about what "better" means
- **Missing context**: Assuming Claude knows your situation → Provide background
- **No format guidance**: Getting essays when you need bullets → Specify structure
- **Asking for opinions**: "What should I do?" → Ask for analysis, decide yourself

---

## My Best Prompts

*Add prompts that work well for you here*

---

*Last updated: January 25, 2026*
