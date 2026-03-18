# TODO Command

Manage a single, organized TODO list with automatic categorization by due date. Supports adding, completing, and organizing tasks.

## CRITICAL: PRESERVE MANUAL EDITS
- **NEVER rewrite the entire file** - user may have made manual edits
- **ONLY append new lines** to appropriate sections
- **ONLY use Edit tool** to make surgical changes (mark complete, etc.)
- Read file to find section boundaries, then append within section

## What to do:

### ADDING A TODO:

1. **Parse the user input:**
   - Extract the task description
   - Extract due date if provided (formats: "today", "tomorrow", "friday", "jan 25", "2026-01-30", "next week")
   - Extract tags from hashtags in the text
   - If no due date provided, ask: "When is this due? (today/tomorrow/friday/next week/later)"

2. **Determine category:**
   - **Overdue**: Due date is in the past
   - **TODAY**: Due date is today
   - **Next 7 Days**: Due date is within next 7 days (tomorrow through 7 days from now)
   - **Later**: Due date is beyond 7 days OR no specific date

3. **Check for TODO file:**
   - Look for `todos.md` in root directory
   - If doesn't exist, create it using template from `.templates/todos-template.md`

4. **Add entry with checkbox (APPEND ONLY):**
   - **Read the file** to find the correct section
   - **Use Edit tool** to add a new line in that section
   - Find the section ending (next `---` or `##` line)
   - Insert BEFORE the section ending

   Format:
   ```
   - [ ] [Task description] (due: YYYY-MM-DD) #tag1 #tag2
   ```

   For "Later" items without specific date:
   ```
   - [ ] [Task description] #tag1 #tag2
   ```

5. **Confirm to user:**
   - Show: "✅ Added to [section]: [task preview]"
   - **DO NOT reorganize** or move other tasks
   - **DO NOT update timestamp** automatically

### COMPLETING A TODO:

When user says "done [task]" or "complete [task]":

1. **Find the task:**
   - Read the file
   - Search for task by keywords in description
   - If multiple matches, show options and ask which one

2. **Mark complete (EDIT ONLY):**
   - **Use Edit tool** to change that specific line only
   - Change `- [ ]` to `- [x]`
   - Add completion timestamp: `(completed: YYYY-MM-DD)`
   - **DO NOT move** to completed section (user can do manually)
   - **ONLY edit that one line**, nothing else

3. **Confirm:**
   - Show: "✅ Completed: [task description]"

### NO AUTO-REORGANIZING:

**DO NOT:**
- Move items between sections automatically
- Reorder tasks
- Update timestamps
- Archive completed items
- Sort anything

**User manages organization manually.** We only add new items or mark specific items complete.

## Examples:

**Input:** "/todo Review portfolio health mockups with design team tomorrow"
**Output:**
- Category: Next 7 Days
- Entry: `- [ ] Review portfolio health mockups with design team (due: 2026-01-24) #design #review #portfolio-health`
- Confirm: "✅ Added to Next 7 Days: Review portfolio health mockups with design team"

**Input:** "/todo Follow up with DB team about MySQL choice"
**Prompt:** "When is this due? (today/tomorrow/friday/next week/later)"
**User:** "friday"
**Output:**
- Entry: `- [ ] Follow up with DB team about MySQL choice (due: 2026-01-26) #database #team-sync`

**Input:** "/todo done review mockups"
**Output:**
- Finds: "Review portfolio health mockups with design team"
- Changes to: `- [x] Review portfolio health mockups with design team (due: 2026-01-24) (completed: 2026-01-23) #design #review #portfolio-health`
- Moves to: Completed section
- Confirm: "✅ Completed: Review portfolio health mockups with design team"

## Smart date parsing:

- "today" → Today's date
- "tomorrow" → Tomorrow's date
- "friday" → Next Friday
- "next week" → 7 days from now
- "jan 25" → 2026-01-25
- "later" → No specific date, goes to "Later" section

## Auto-tagging:

Extract tags from:
- Explicit hashtags in text
- Project/product names (project names, features, etc.)
- Team names (design, DB, engineering, etc.)
- Action types (review, follow-up, sync, etc.)

## Obsidian Integration:

- File is `todos.md` in root (easy to find)
- Uses standard markdown checkboxes (clickable in Obsidian)
- Tags work with Obsidian tag search
- Can be pinned in Obsidian sidebar

## Tone:

- Fast and frictionless
- Smart date parsing
- Auto-organize everything
- Minimal questions

## Notes:

- Single source of truth: `todos.md`
- **Append-only for new tasks** - never rewrite file
- **Edit single line only** when marking complete
- **No auto-reorganization** - user manages manually
- Preserve all manual edits and organization
