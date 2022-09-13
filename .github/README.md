# Contributing

## Entries

Start every new entry with
```markdown
---
title: An Important Entry ✅
---

Content
```

NOT

```markdown
---
title: An Important Entry
---

# An Important Entry ❌

Content
```

## Entry Config

```markdown
---
title: string
weight: number
---
```

#### `title`

A pretty title that will be displayed to the user.

#### `weight`

Entries and directories are sorted by their weights. Higher number = Higher up.

## File and directory names

Use Kebab case for filenames
| ❌ | ✅ |
| - | - |
| `an_important_entry.mdx`, `An Important Entry.mdx` | `an-important-entry.mdx` |

## Directories

Do not create directories any deeper than 1. Only top level directories for different projects.

### `.config.yaml`

Create a .config.yaml for every directory. See [Entry Config](#entry-config)
