# Capture Command

Capture Slack feedback and file it properly in today's intelligence file.

## What to do:

1. **Ask the user for information:**
   - "Paste the Slack message text"
   - "Paste the Slack link"
   - "Who sent it? (name and role if you know)"
   - "Which channel/thread?"
   - (Optional) "Any additional context?"

2. **Analyze the message:**
   - Determine type: Customer request, Stakeholder decision, Bug, Idea, Question, or Technical discussion
   - Extract key insight
   - Identify any patterns or themes

3. **Check for today's intelligence file:**
   - Look in `intelligence/slack-daily/` for today's date (YYYY-MM-DD.md)
   - If doesn't exist, create it using the template from `.templates/slack-intelligence-template.md`

4. **Add to appropriate section:**
   - Place in correct category based on message type
   - Fill in all fields:
     - Title (generate from message)
     - From (name and role)
     - Channel
     - Message (full text)
     - Link
     - Insight (your analysis)

5. **Update pattern analysis:**
   - Add theme to "Today's Themes"
   - Note if related to known patterns
   - Identify any new patterns emerging

6. **Confirm to user:**
   - Show which file was updated
   - Show which section it was added to
   - Ask if they want to capture another message

## Tone:
- Quick and efficient
- Ask minimal questions
- Smart categorization
- Generate good insights

## After capture:
Print: "✅ Captured in intelligence/slack-daily/[date].md under [section]"
