# Today Command

Generate the daily command center dashboard for this morning.

## What to do:

1. **Check if today's daily note exists** in the `daily/` folder
   - If not, create it using the template from `.templates/daily-template.md`
   - Replace {{date}} placeholders with today's date

2. **Collect overnight intelligence** (if available)
   - Check `intelligence/slack-daily/` for yesterday's file
   - Check `intelligence/f2f-meetings/` for recent meeting captures
   - Summarize any new signals from yesterday and today
   - Add to "Overnight Intelligence" section
   - **ALWAYS include source links:**
     - For Slack signals: Add both Slack thread URL AND wiki link to intelligence file
     - Format: `🔗 [Slack thread](URL) | [[intelligence/slack-daily/YYYY-MM-DD|Daily capture]]`
     - For F2F meetings: Add wiki link to meeting notes
     - Format: `🔗 [[intelligence/f2f-meetings/YYYY-MM-DD-person|Full meeting notes]]`

3. **Check for recent synthesis**
   - Look in `intelligence/synthesis-weekly/` for this week's synthesis
   - If Friday synthesis exists, highlight bet candidates needing action

4. **Review active bets** (manual for now, will automate with Notion later)
   - Placeholder section for now
   - User will fill in manually until we set up Notion API

5. **Generate focus question**
   - Based on recent intelligence, suggest what to think about for bets today
   - Example: "Should we prioritize BET-001 (bulk upload) or explore mobile patterns more?"

6. **Add quick links**
   - Links to common Notion pages (user will provide these)
   - Link to yesterday's dashboard
   - Link to this week's synthesis if available

7. **Show intelligence summary**
   - Count files in `intelligence/slack-daily/` this week
   - Count files in `intelligence/f2f-meetings/` this week
   - List any emerging themes from recent intelligence
   - **For Strong Signals section:** Always include source links using arrow notation
     - Format: `→ [[intelligence/path/to/file|Source]]`

## Output location:
Create/update file at: `daily/[YYYY-MM-DD].md`

## Tone:
- Concise and actionable
- Morning-friendly (encouraging but realistic)
- Prioritize what matters most

## After generation:
- Open the file in Obsidian for user to review
- Print summary: "Dashboard ready for [date]. Key focus: [top priority]"
