# System Prompt Library

Welcome to your AI System Prompt Library! This vault contains a collection of carefully crafted system prompts for various use cases, integrated with Templater and Dataview for easy management and discovery.

## 📚 Quick Navigation

- [[Templates/New Prompt|Create New Prompt]] - Use the full template
- [[Templates/Quick Prompt|Create Quick Prompt]] - Use the minimal template

## 📊 Browse Prompts

### By Category

```dataview
TABLE difficulty, use_case, tags
FROM "Prompts"
WHERE category = "Coding"
SORT file.name ASC
```

#### Coding Prompts
```dataview
LIST
FROM "Prompts/Coding"
SORT file.name ASC
```

#### Writing Prompts
```dataview
LIST
FROM "Prompts/Writing"
SORT file.name ASC
```

#### Analysis Prompts
```dataview
LIST
FROM "Prompts/Analysis"
SORT file.name ASC
```

#### General Prompts
```dataview
LIST
FROM "Prompts/General"
SORT file.name ASC
```

### By Difficulty

#### Beginner
```dataview
TABLE category, use_case
FROM "Prompts"
WHERE difficulty = "Beginner"
SORT file.name ASC
```

#### Intermediate
```dataview
TABLE category, use_case
FROM "Prompts"
WHERE difficulty = "Intermediate"
SORT file.name ASC
```

#### Advanced
```dataview
TABLE category, use_case
FROM "Prompts"
WHERE difficulty = "Advanced"
SORT file.name ASC
```

### Recently Modified
```dataview
TABLE category, difficulty, modified
FROM "Prompts"
SORT modified DESC
LIMIT 10
```

### By Tag
```dataview
TABLE category, difficulty, use_case
FROM "Prompts"
FLATTEN tags
GROUP BY tags
```

## 🔍 Search by Use Case

Find prompts by their use case:

```dataview
TABLE category, difficulty, file.link as "Prompt"
FROM "Prompts"
SORT use_case ASC
```

## 📈 Statistics

```dataview
TABLE length(rows) as "Count"
FROM "Prompts"
GROUP BY category
```

### Total Prompts
```dataview
LIST length(rows.file.link)
FROM "Prompts"
```

## 💡 How to Use

1. **Browse**: Use the Dataview queries above to find relevant prompts
2. **Create**: Use Templater templates to create new prompts with consistent structure
3. **Customize**: Modify existing prompts for your specific needs
4. **Organize**: Use tags and properties for easy filtering and search

## 🏷️ Tags Reference

- `#prompt` - All system prompts
- `#code-review` - Code review related
- `#documentation` - Documentation and writing
- `#analysis` - Analysis and research
- `#productivity` - Productivity and planning
- `#refactoring` - Code improvement
- `#writing` - Content creation

## ⚙️ Configuration

This vault uses:
- **Templater**: For creating new prompts with dynamic fields
- **Dataview**: For querying and displaying prompts
- **Properties**: For structured metadata (category, tags, difficulty, etc.)

## 📝 Contributing

When adding new prompts:
1. Use one of the templates from the Templates folder
2. Fill in all metadata fields (category, tags, difficulty, use_case)
3. Write clear, detailed system prompts
4. Include example usage and notes
5. Link related prompts

---

*This vault is designed for efficient prompt management and discovery. Happy prompting! 🚀*
