# Dataview Query Examples

This file demonstrates the various Dataview queries available in this vault. When opened in Obsidian with the Dataview plugin enabled, these queries will dynamically display your prompt library.

## Simple List Queries

### All Coding Prompts
```dataview
LIST
FROM "Prompts/Coding"
SORT file.name ASC
```

### All Writing Prompts
```dataview
LIST
FROM "Prompts/Writing"
SORT file.name ASC
```

## Table Queries

### All Prompts with Metadata
```dataview
TABLE category, difficulty, use_case, created
FROM "Prompts"
SORT category ASC, file.name ASC
```

### Beginner-Friendly Prompts
```dataview
TABLE category, use_case
FROM "Prompts"
WHERE difficulty = "Beginner"
SORT category ASC
```

### Advanced Prompts
```dataview
TABLE category, use_case
FROM "Prompts"
WHERE difficulty = "Advanced"
SORT category ASC
```

## Filter by Tags

### Code Review Related
```dataview
TABLE difficulty, use_case
FROM "Prompts"
WHERE contains(tags, "code-review")
```

### Documentation Related
```dataview
TABLE difficulty, use_case
FROM "Prompts"
WHERE contains(tags, "documentation")
```

### Problem Solving
```dataview
TABLE category, difficulty
FROM "Prompts"
WHERE contains(tags, "problem-solving") OR contains(tags, "debugging")
```

## Grouped Queries

### Count by Category
```dataview
TABLE length(rows) as "Number of Prompts"
FROM "Prompts"
GROUP BY category
SORT category ASC
```

### Count by Difficulty
```dataview
TABLE length(rows) as "Number of Prompts"
FROM "Prompts"
GROUP BY difficulty
```

## Date-Based Queries

### Recently Created (Last 30 Days)
```dataview
TABLE category, difficulty, created
FROM "Prompts"
WHERE date(created) > date(today) - dur(30 days)
SORT created DESC
```

### Recently Modified (Last 7 Days)
```dataview
TABLE category, modified
FROM "Prompts"
WHERE date(modified) > date(today) - dur(7 days)
SORT modified DESC
```

## Task Queries

### Find Prompts Missing Notes
```dataview
TABLE category, difficulty
FROM "Prompts"
WHERE !contains(file.text, "## Notes")
```

## Custom Search Queries

### Find by Use Case Keyword
To search for prompts containing "testing" in use_case:
```dataview
TABLE category, difficulty, use_case
FROM "Prompts"
WHERE contains(use_case, "testing")
```

### Find by Category and Difficulty
```dataview
TABLE file.link as "Prompt", use_case
FROM "Prompts"
WHERE category = "Coding" AND difficulty = "Intermediate"
```

## Statistics

### Total Prompts
```dataview
LIST "Total: " + length(rows)
FROM "Prompts"
```

### Breakdown by Category and Difficulty
```dataview
TABLE length(rows) as "Count"
FROM "Prompts"
GROUP BY category, difficulty
SORT category ASC, difficulty ASC
```

## Tips for Using Dataview

1. **WHERE clauses** - Filter results based on conditions
2. **SORT** - Order results by field(s)
3. **GROUP BY** - Aggregate data
4. **FLATTEN** - Expand array fields
5. **contains()** - Check if text exists in a field
6. **length()** - Count items
7. **date()** - Work with dates
8. **dur()** - Time durations

## Example Custom Queries You Can Create

### Find Unlinked Prompts
```dataview
TABLE category
FROM "Prompts"
WHERE !contains(file.text, "[[")
```

### Most Tagged Prompts
```dataview
TABLE length(tags) as "Tag Count", tags
FROM "Prompts"
SORT length(tags) DESC
```

---

*These queries are examples. Modify them to fit your specific needs!*
