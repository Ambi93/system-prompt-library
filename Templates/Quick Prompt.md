---
category: <% tp.system.prompt("Category") %>
tags: [prompt]
created: <% tp.date.now("YYYY-MM-DD") %>
---

# <% tp.file.title %>

```
<% tp.system.prompt("Enter prompt") %>
```
