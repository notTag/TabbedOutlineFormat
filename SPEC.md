# Tabbed Outline Format (TOF) Specification

**Version:** 0.1.0-alpha
**Status:** Alpha (pre-beta, breaking changes possible)
**Canonical URL:** https://tabbedoutlineformat.com

These instructions describe the **Tabbed Outline Format** (TOF) — a plain-text, tab-indented note-taking style. Follow these rules when creating or editing files that have been explicitly requested in this format.

---

## Core Principle

Content is organized as a hierarchy using **literal tab characters** for indentation. Each tab level represents one deeper layer of detail. The format prioritizes scannability, density, and zero formatting overhead.

---

## Indentation Rules

- Use **real tab characters** (not spaces) for every indentation level.
- Root level (0 tabs) is reserved for top-level topics, section headers, or standalone descriptions.
- Each additional tab = one deeper level of nesting. There is no hard limit on depth, but most content lives within 1-3 tab levels.

---

## Entry Patterns

### Pattern 1: Description-then-Content (most common)

A plain-text description sits at one level. The command, code, or value it describes is indented one tab deeper directly below it.

```
Check Docker Version:
	docker --version
```

### Pattern 2: Category Nesting

Group related entries under a shared parent label. Nest as many levels deep as needed.

```
Basic Docker Commands
	Images
		List Images:
			docker images
		Pull an Image from Docker Hub:
			docker pull <image-name>
	Containers
		List Running Containers:
			docker ps
```

### Pattern 3: Inline Key-Value

For mappings like keyboard shortcuts or flag references, place the key and its description on the same line separated by tab(s).

```
mode select
	esc 	normal mode
	i   	insert mode
	a   	(append) moves the cursor one character over and switches to insert mode.
```

### Pattern 4: Sub-Explanations

Explain individual flags or parts of a command by nesting them below the command itself.

```
Initialize a new repo on github.
	git init
	git add .
	git commit -m "initial commit"
	gh repo create my-repo-name --private --source=. --push
		--source=.
			set the current directory as the directory you want to create in github.
```

---

## Section Headers

Section headers appear at root level (0 tabs). Several styles are acceptable:

- **Bordered**: `#--- Title ---#`
- **Underlined**: Title on one line, `===` or `---` on the next
- **ALL CAPS**: `HOOK EVENTS`
- **Plain text**: Just the title as a line at root level (e.g., `Basics`, `Convert`, `Search`)
- **File title**: The first line of the file can serve as the document title

A blank line should appear before and/or after section headers to visually separate groups.

---

## Formatting Rules

1. **Plain text only.** Do not use markdown syntax (`#`, `**`, backticks, bullet points) inside Tabbed Outline files. The hierarchy comes entirely from tab indentation.
2. **Terse descriptions.** Use short, direct phrases rather than full sentences. Just enough context to understand the entry.
3. **Blank lines** separate logical groups or sections. Use them to give breathing room between unrelated topics.
4. **Placeholders** use `<angle-brackets>` for variable or user-supplied values (e.g., `<image-name>`, `<container-name>`).
5. **No trailing explanatory prose.** Don't add paragraphs of explanation. If something needs more context, nest it one level deeper.
6. **Code/commands live at leaf level.** The actual command or code snippet should be at the deepest indentation for its entry, with its description one level above.

---

## File Naming

- Use **camelCase** for file names.
- Suffix with `Cheat` or `CheatSheet` (e.g., `gitCheat.txt`, `dockerCheatSheet.txt`).
- Use `.txt` extension.

---

## Complete Example

```
#-----------tmux Cheat Sheet-----------#

Session Management
	Start a new named session
		tmux new -s mysession
	List sessions
		tmux ls
	Attach to a session
		tmux attach -t mysession
	Kill a session
		tmux kill-session -t mysession

Window Management
	Create new window
		ctrl+b c
	Rename window
		ctrl+b ,
	Next/previous window
		ctrl+b n		next
		ctrl+b p		previous

Pane Management
	Split vertically
		ctrl+b %
	Split horizontally
		ctrl+b "
	Navigate panes
		ctrl+b arrow-key
	Close pane
		exit
```

---

## Summary Checklist

- [ ] Uses real tab characters, not spaces
- [ ] Descriptions above, content indented below
- [ ] Section headers at root level with blank line separation
- [ ] No markdown syntax — plain text only
- [ ] Terse, scannable descriptions
- [ ] Placeholders in `<angle-brackets>`
- [ ] File named in camelCase with Cheat/CheatSheet suffix and .txt extension
