# Getting Started Guide

Welcome to your System Prompt Library! This guide will help you set up and start using the vault effectively.

## Initial Setup

### Step 1: Open in Obsidian

1. Download and install [Obsidian](https://obsidian.md/) if you haven't already
2. Open Obsidian
3. Click "Open folder as vault"
4. Select the `system-prompt-library` folder
5. Click "Trust author and enable plugins" when prompted

### Step 2: Install Required Plugins

The vault requires two community plugins:

#### Dataview Plugin
1. Go to Settings (gear icon)
2. Click "Community plugins"
3. Click "Browse" 
4. Search for "Dataview"
5. Install and Enable it
6. Go to Dataview settings and ensure these are enabled:
   - Enable Inline Queries: ON
   - Enable Inline JavaScript Queries: OFF (optional)

#### Templater Plugin
1. In Settings → Community plugins
2. Click "Browse"
3. Search for "Templater"
4. Install and Enable it
5. Go to Templater settings:
   - Template folder location: `Templates`
   - Trigger Templater on new file creation: ON (optional)
   - Enable System Commands: ON

### Step 3: Explore the Vault

Open these files to get started:

1. **Index.md** - Your main hub for browsing prompts
2. **README.md** - Complete documentation
3. **Dataview Examples.md** - Learn more about querying
4. **This file** - You're reading it!

## Basic Usage

### Finding a Prompt

#### Method 1: Browse by Category
1. Open `Index.md`
2. Scroll to "Browse Prompts"
3. Click on any category (Coding, Writing, Analysis, General)
4. Click on a prompt name to open it

#### Method 2: Use Quick Switcher
1. Press `Ctrl+O` (or `Cmd+O` on Mac)
2. Start typing the prompt name
3. Press Enter to open

#### Method 3: Use Search
1. Press `Ctrl+Shift+F` (or `Cmd+Shift+F` on Mac)
2. Search for keywords in prompts
3. Click on results to open

### Using a Prompt

1. Open any prompt file (e.g., `Code Review Assistant.md`)
2. Find the "System Prompt" section
3. Copy the text inside the code block
4. Paste it into your AI assistant (ChatGPT, Claude, etc.)
5. Start your conversation with context!

### Creating a New Prompt

#### Using the Full Template

1. Press `Ctrl+P` (or `Cmd+P`) to open Command Palette
2. Type "Templater: Create new note from template"
3. Select "Templates/New Prompt"
4. Choose or create a folder for your prompt
5. Fill in the interactive prompts:
   - Category (Coding/Writing/Analysis/General)
   - Tags (comma-separated)
   - Difficulty (Beginner/Intermediate/Advanced)
   - Use case
   - Purpose
   - System prompt text
   - Example usage
6. Save the file

#### Using the Quick Template

1. Open Command Palette (`Ctrl+P` or `Cmd+P`)
2. Type "Templater: Create new note from template"
3. Select "Templates/Quick Prompt"
4. Fill in:
   - Category
   - Prompt text
5. Save and expand later

#### Manual Creation

1. Create a new note in the `Prompts` folder (or subfolder)
2. Copy the structure from an existing prompt
3. Fill in the frontmatter properties
4. Write your system prompt

## Understanding Metadata

Each prompt has frontmatter (YAML) at the top:

```yaml
---
category: Coding
tags: [prompt, code-review, quality]
created: 2025-01-01
modified: 2025-01-01
difficulty: Intermediate
use_case: Code review and analysis
---
```

**Why this matters:**
- **category**: Groups related prompts (used in Index.md queries)
- **tags**: Multiple labels for filtering
- **created/modified**: Track when prompts were added/updated
- **difficulty**: Helps find appropriate prompts for your skill level
- **use_case**: Quick description of when to use this prompt

### Editing Metadata

You can edit frontmatter in two ways:

1. **Source Mode**: Edit the YAML directly at the top of the file
2. **Properties View**: Click on the properties panel in Obsidian

## Working with Dataview

Dataview queries automatically update based on your vault content.

### Example: Find All Beginner Prompts

In any note, add:
```
​```dataview
TABLE category, use_case
FROM "Prompts"
WHERE difficulty = "Beginner"
​```
```

When you view the note, you'll see a table of all beginner-level prompts!

See `Dataview Examples.md` for more query examples.

## Tips for Success

### Organization Tips

1. **Use Tags Wisely**: Add specific tags to make prompts easier to find
2. **Update Modified Dates**: Change the `modified` field when you update a prompt
3. **Link Related Prompts**: Use `[[Prompt Name]]` to create connections
4. **Keep Consistent Structure**: Follow the template format for all prompts

### Workflow Tips

1. **Start Simple**: Use existing prompts before creating new ones
2. **Customize as Needed**: Adapt prompts for your specific use case
3. **Keep Notes**: Use the "Notes" section to track what works
4. **Version Your Prompts**: If a prompt evolves significantly, consider creating a new version

### AI Assistant Tips

1. **Set Context First**: Paste the system prompt before starting your conversation
2. **Be Specific**: Give the AI clear, specific instructions
3. **Iterate**: Refine prompts based on what works
4. **Save Successful Variations**: If you modify a prompt and it works well, save it!

## Common Tasks

### Adding a New Category

1. Create a folder in `Prompts/YourNewCategory/`
2. Add prompts to that folder with `category: YourNewCategory`
3. Update `Index.md` to add a Dataview query for the new category:
   ```
   #### YourNewCategory Prompts
   ​```dataview
   LIST
   FROM "Prompts/YourNewCategory"
   SORT file.name ASC
   ​```
   ```

### Exporting a Prompt

1. Open the prompt file
2. Copy the system prompt text
3. Save it to a text file, or
4. Share it directly with your team

### Backing Up Your Library

This vault is just a folder on your computer:
- **Git**: Initialize a git repository and push to GitHub
- **Cloud Sync**: Use Obsidian Sync, Dropbox, or Google Drive
- **Manual**: Copy the entire folder regularly

## Keyboard Shortcuts

Essential Obsidian shortcuts:

- `Ctrl/Cmd + O`: Quick switcher (find files)
- `Ctrl/Cmd + P`: Command palette
- `Ctrl/Cmd + N`: New note
- `Ctrl/Cmd + E`: Toggle edit/preview mode
- `Ctrl/Cmd + F`: Search in current file
- `Ctrl/Cmd + Shift + F`: Search in all files
- `Ctrl/Cmd + Click`: Open link in new pane

## Troubleshooting

### Dataview Queries Not Working

1. Check that Dataview plugin is installed and enabled
2. Verify the query syntax (no typos)
3. Make sure you're in Reading View (not Source Mode)
4. Check that files have proper frontmatter

### Templater Not Working

1. Ensure Templater plugin is enabled
2. Check that template folder is set to "Templates"
3. Verify templates have the correct Templater syntax (`<% %>`)

### Prompts Not Appearing in Queries

1. Check the file is in the `Prompts/` folder
2. Verify frontmatter is properly formatted (YAML)
3. Ensure category and other fields are spelled correctly
4. Refresh the note (close and reopen)

## Next Steps

1. **Explore existing prompts**: Open each prompt and read through them
2. **Try one with your AI assistant**: Pick a relevant prompt and test it
3. **Create your first prompt**: Use the template to add a custom prompt
4. **Customize the Index**: Modify `Index.md` to show what's most useful to you
5. **Build your library**: Add prompts as you discover what works!

## Resources

- **Obsidian Help**: https://help.obsidian.md/
- **Dataview Documentation**: https://blacksmithgu.github.io/obsidian-dataview/
- **Templater Documentation**: https://silentvoid13.github.io/Templater/
- **Prompt Engineering Guide**: https://www.promptingguide.ai/

---

**You're all set!** Start exploring your prompt library and build your collection of powerful AI system prompts. 🚀
