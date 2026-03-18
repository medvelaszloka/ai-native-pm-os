# Note Command

Quick capture for daily observations, questions, and to-dos. Stored in daily notes file with automatic categorization and tagging.

## What to do:

1. **Get the note from user arguments or prompt:**
   - If user provided text in the command args, use that
   - If no args, ask: "What do you want to note?"

2. **Smart categorization:**
   - Detect category based on keywords and context:
     - **Questions**: "why", "how", "should we", "check with", "ask", "?"
     - **To-Dos**: "need to", "remember to", "must", "action", "follow up"
     - **Observations**: "noticed", "interesting", "found", "realized", "pattern"
     - **Links**: Contains URLs
     - **Meeting Notes**: "meeting with", "discussed", "call with", "sync"

3. **Auto-tag intelligently:**
   - Extract relevant tags from content (project names, team names, tech terms)
   - Add standard tags: #question, #todo, #observation, #link, #meeting
   - Add domain tags: #database, #frontend, #design, #stakeholder, etc.

4. **Check for today's notes file:**
   - Look in `notes/daily/` for today's date (YYYY-MM-DD.md)
   - If doesn't exist, create it using template from `.templates/daily-notes-template.md`

5. **Add entry with timestamp:**
   Format:
   ```
   - **HH:MM** [Note text] #tag1 #tag2
   ```

6. **Confirm to user:**
   - Show: "✅ Noted in notes/daily/[date].md under [section]"
   - Show the formatted entry that was added
   - Ready for next note (don't ask)

## Examples:

**Input:** "Why did the DB team choose MySQL over Postgres for accounts table?"
**Output:**
- Category: Questions to Follow Up
- Entry: `- **14:23** Why did the DB team choose MySQL over Postgres for accounts table? #database #question #accounts #team-sync`

**Input:** "Need to review the new dashboard design with Sarah before Friday"
**Output:**
- Category: Quick To-Dos
- Entry: `- **09:15** Need to review the new dashboard design with Sarah before Friday #todo #design #dashboard #review`

**Input:** "Noticed that portfolio health requests coming from both PMs and CPMs - pattern emerging"
**Output:**
- Category: Observations & Insights
- Entry: `- **16:42** Noticed that portfolio health requests coming from both PMs and CPMs - pattern emerging #observation #portfolio-management #pattern`

## Tone:
- Lightning fast
- Minimal friction
- Smart defaults
- No unnecessary questions

## After capture:
User can immediately run another `/note` or continue working.
