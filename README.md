# System Prompt Library for Obsidian

A comprehensive, well-organized library of AI system prompts for use with various AI assistants. Designed as an Obsidian vault with powerful integrations for Templater, Dataview, and property-based organization.

## 🎯 Features

- **50+ Curated System Prompts** organized by category (Coding, Writing, Analysis, General)
- **Templater Integration** for creating new prompts with consistent structure
- **Dataview Queries** for powerful searching, filtering, and visualization
- **Metadata Properties** for easy categorization and filtering (category, tags, difficulty, use_case)
- **Cross-linking** between related prompts
- **Easy to Extend** with new prompts and categories

## 📁 Structure

```
system-prompt-library/
├── Index.md                    # Main hub with Dataview queries
├── README.md                   # This file
├── Templates/                  # Templater templates
│   ├── New Prompt.md          # Full template for detailed prompts
│   └── Quick Prompt.md        # Minimal template for quick entries
├── Prompts/                    # All system prompts
│   ├── Coding/                # Code-related prompts
│   ├── Writing/               # Content creation prompts
│   ├── Analysis/              # Data & research prompts
│   └── General/               # General-purpose prompts
└── .obsidian/                  # Obsidian configuration
    ├── app.json               # App settings
    └── plugins.json           # Plugin configuration
```

## 🚀 Quick Start

### 1. Setup in Obsidian

1. Clone or download this repository
2. Open the folder as a vault in Obsidian
3. Install required plugins:
   - [Dataview](https://github.com/blacksmithgu/obsidian-dataview)
   - [Templater](https://github.com/SilverLightning/Templater)
4. Enable the plugins in Settings → Community Plugins
5. Open `Index.md` to start browsing prompts

### 2. Browse Prompts

The `Index.md` file provides multiple ways to explore prompts:

- **By Category**: Coding, Writing, Analysis, General
- **By Difficulty**: Beginner, Intermediate, Advanced
- **By Tag**: Find specific use cases
- **Recently Modified**: See latest updates
- **Statistics**: Overview of your library

### 3. Use a Prompt

1. Browse to find a relevant prompt
2. Open the prompt file
3. Copy the system prompt from the code block
4. Paste it into your AI assistant's system prompt field
5. Customize as needed for your specific use case

### 4. Create New Prompts

Using Templater:

1. Press `Ctrl/Cmd + P` to open command palette
2. Search for "Templater: Create new note from template"
3. Choose either:
   - `Templates/New Prompt.md` - For detailed prompts with full metadata
   - `Templates/Quick Prompt.md` - For simple, quick prompts
4. Fill in the prompted information
5. Save your new prompt

## 📊 Dataview Queries

The vault includes powerful Dataview queries for:

- Listing all prompts by category
- Filtering by difficulty level
- Finding recently modified prompts
- Grouping by tags
- Statistical overviews
- Custom searches by use case

Example queries are pre-configured in `Index.md`.

## 🏷️ Metadata Properties

Each prompt includes frontmatter with these properties:

- `category`: Main category (Coding, Writing, Analysis, General)
- `tags`: Multiple tags for filtering (e.g., code-review, documentation)
- `created`: Creation date
- `modified`: Last modification date
- `difficulty`: Beginner, Intermediate, or Advanced
- `use_case`: Brief description of when to use this prompt

## 📝 Example Prompts Included

### Coding
- **Code Review Assistant** - Thorough code review with best practices
- **Code Refactoring Assistant** - Improve code structure and maintainability

### Writing
- **Technical Documentation Writer** - Create clear technical docs
- **Blog Post Writer** - Engaging content creation

### Analysis
- **Data Analysis Expert** - Analyze data and provide insights
- **Research Assistant** - Conduct thorough research

### General
- **Project Planning Assistant** - Plan and organize projects
- **Problem Solving Coach** - Systematic problem-solving guidance

## 🔧 Customization

### Adding Categories

1. Create a new folder under `Prompts/YourCategory/`
2. Add prompts to the new folder
3. Use the templates to maintain consistency
4. Update the Index.md with new Dataview queries if desired

### Modifying Templates

Edit the template files in the `Templates/` folder to:
- Add new metadata fields
- Change the structure
- Customize prompts for your workflow

### Custom Dataview Queries

Add your own queries to `Index.md` or create separate query pages:

```dataview
TABLE category, difficulty
FROM "Prompts"
WHERE contains(tags, "your-tag")
SORT file.name ASC
```

## 🌟 Best Practices

1. **Consistent Metadata**: Always fill in all property fields
2. **Clear Naming**: Use descriptive file names
3. **Cross-linking**: Link related prompts together
4. **Version Control**: Keep this vault in git for history
5. **Regular Updates**: Update the `modified` date when editing prompts
6. **Tag Strategically**: Use tags for easy discovery

## 🤝 Contributing

To add your own prompts:

1. Use one of the Templater templates
2. Follow the existing structure and naming conventions
3. Include complete metadata
4. Write clear, detailed system prompts
5. Add example usage scenarios
6. Link to related prompts

## 📚 Resources

- [Obsidian Documentation](https://help.obsidian.md/)
- [Dataview Plugin](https://blacksmithgu/obsidian-dataview)
- [Templater Plugin](https://github.com/SilverLightning/Templater)
- [System Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)

## 📄 License

This prompt library is provided as-is for personal and commercial use. Feel free to modify and adapt to your needs.

## 🎓 Learn More

For tips on writing effective system prompts:
- Start with a clear role definition
- Provide specific instructions and constraints
- Include examples when helpful
- Define the expected output format
- Test and iterate on your prompts

---

**Happy Prompting! 🚀**

*This vault helps you build, organize, and maintain a powerful library of AI system prompts for any use case.*