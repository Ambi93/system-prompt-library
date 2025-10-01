---
category: <% tp.system.prompt("Enter category (Coding/Writing/Analysis/General)") %>
tags: [prompt, <% tp.system.prompt("Enter tags (comma-separated)") %>]
created: <% tp.date.now("YYYY-MM-DD") %>
modified: <% tp.date.now("YYYY-MM-DD") %>
difficulty: <% tp.system.suggester(["Beginner", "Intermediate", "Advanced"], ["Beginner", "Intermediate", "Advanced"]) %>
use_case: <% tp.system.prompt("Enter use case") %>
---

# <% tp.file.title %>

## Purpose
<% tp.system.prompt("Enter the purpose of this prompt") %>

## System Prompt
```
<% tp.system.prompt("Enter your system prompt here") %>
```

## Example Usage
<% tp.system.prompt("Enter example usage") %>

## Notes
- 

## Related Prompts
- 
