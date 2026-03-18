# Update Context Command

Capture information after betting sessions or strategic events and update living context files.

## What to do:

1. **Ask questions one at a time (conversationally):**

   **Question 1:** "What event or meeting just happened?" (e.g., "Cycle 4 betting session")
   - Store this as SOURCE for all updates

   **Question 2:** "Did any strategic priorities change? If yes, what changed? If no, type 'skip'"
   - If not skip: Ask follow-up: "Why did this change?" and "What impact will this have on product decisions?"

   **Question 3:** "Which bets were chosen in this cycle? List them with their appetite (2 weeks or 6 weeks). If none, type 'skip'"
   - If not skip: For each bet, ask: "Why was [bet name] chosen?" and "What's the expected outcome?"

   **Question 4:** "Which bets were considered but rejected? For each, briefly explain why. If none, type 'skip'"
   - If not skip: Ask: "When should we revisit these?"

   **Question 5:** "Were any major decisions made? If yes, describe them. If no, type 'skip'"
   - If not skip: Ask: "What alternatives were considered?" and "What impact will this have?"

   **Question 6:** "Any important learnings or discoveries? If yes, describe them. If no, type 'skip'"
   - If not skip: Ask: "Why does this matter for future decisions?" and "What action should we take?"

2. **Update files based on answers:**

   ### If strategy changed (Q2 not skip):
   **File:** `context/living/strategy-current.md`
   - Read file first
   - Add to "Recent Strategic Shifts" section (after existing entries)
   - Format:
   ```
   - **[Today's Date YYYY-MM-DD]**: [What changed]
     - Why: [from user's answer]
     - Impact: [from user's answer]
     - Source: [event from Q1]
   ```
   - Update "Last updated" date at top of file

   ### If bets were chosen (Q3 not skip):
   **File:** `context/living/bets-rationale.md`
   - Read file first
   - Add to "Active Bets (Current 6-week cycle)" section
   - For EACH bet listed, format:
   ```
   ### [Bet Name] (Cycle [infer or ask], 2026)
   - **Appetite:** [2 weeks or 6 weeks from user]
   - **Why we chose it:** [from user's answer]
   - **Expected outcome:** [from user's answer]
   - **Status:** Week 1 of [2 or 6 based on appetite]
   - **Bet pitch:** [[to be linked later]]
   ```
   - Place ABOVE the "---" separator before "Past Bets"

   ### If bets were rejected (Q4 not skip):
   **File:** `context/living/bets-rationale.md`
   - Read file first
   - Add to "Rejected Bet Candidates (Worth Tracking)" section
   - For EACH rejected bet, format:
   ```
   ### [Bet Name] - Rejected [Today's Date YYYY-MM-DD]
   - **Why rejected:** [from user's answer]
   - **Alternative chosen instead:** [reference to chosen bets from Q3]
   - **Revisit when:** [from user's answer or "TBD"]
   ```
   - Place ABOVE the "---" separator before templates

   ### If decisions were made (Q5 not skip):
   **File:** `context/living/decisions-log.md`
   - Read file first
   - Add ABOVE the "Template for New Decisions" section
   - Format:
   ```
   ## [Today's Date YYYY-MM-DD]: [Generate decision title from description]
   **Decision:** [from user's answer]
   **Rationale:**
   - [extract bullet points from user's answer]

   **Alternatives considered:**
   - [from Q4 rejected bets and Q5 answer]

   **Evidence:**
   - [reference event from Q1]
   - [any other context from conversation]

   **Impact:**
   - [from user's answer]

   **Sources:**
   - [event from Q1]
   - [[link to related synthesis files if relevant]]

   ---
   ```

   ### If learnings were shared (Q6 not skip):
   **File:** `context/living/learnings.md`
   - Read file first
   - Create section "## [Current Month YYYY-MM] Learnings" if doesn't exist
   - Add AFTER the month header, BEFORE "Recurring Patterns":
   ```
   ### [Generate learning title from description]
   - **Situation:** [from Q1 event + context]
   - **Discovery:** [from user's answer]
   - **Why it matters:** [from user's answer]
   - **Action:** [from user's answer]
   - **Source:** [event from Q1]
   ```

3. **IMPORTANT UPDATE RULES:**
   - ALWAYS read the file BEFORE updating
   - ALWAYS append (never overwrite existing content)
   - Use today's date
   - Follow exact markdown formatting from templates
   - Maintain proper section ordering
   - Keep existing content intact

4. **After all updates, show:**
   ```
   ✅ Living context updated!

   Files modified:
   [list each file path that was updated]

   Summary of changes:
   - [file name]: [brief description of what was added]
   - [file name]: [brief description of what was added]

   Your living context is now current. Next time you run /synthesize, it will use this updated information!
   ```

## Tone:
- Conversational and efficient
- Ask one question at a time
- Accept "skip" to move on quickly
- Infer details when obvious
- Generate good titles/summaries from user input

## Example Flow:
```
User: /update-context
Claude: What event or meeting just happened?
User: Cycle 4 betting session
Claude: Did any strategic priorities change? If yes, what changed? If no, type 'skip'
User: skip
Claude: Which bets were chosen in this cycle? List them with their appetite.
[continues through all questions]
```
