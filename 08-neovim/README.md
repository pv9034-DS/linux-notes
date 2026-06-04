# Neovim Basics

## Introduction

Neovim is a modern, extensible text editor based on Vim. It is lightweight, fast, keyboard-driven, and widely used by developers, system administrators, and DevOps engineers.

---

## Starting Neovim

Open a file:

```bash
nvim file.txt
```

Open Neovim without a file:

```bash
nvim
```

---

## Modes in Neovim

Neovim works in different modes.

### Normal Mode

Default mode used for navigation and commands.

Press:

```text
Esc
```

to return to Normal Mode.

---

### Insert Mode

Used for typing and editing text.

Enter Insert Mode:

```text
i
```

Insert before cursor.

```text
a
```

Insert after cursor.

```text
o
```

Create a new line below.

---

### Visual Mode

Used to select text.

```text
v
```

Character selection.

```text
V
```

Line selection.

```text
Ctrl + v
```

Block selection.

---

### Command Mode

Used to execute commands.

Press:

```text
:
```

Examples:

```vim
:w
:q
:wq
```

---

## Saving and Quitting

Save file:

```vim
:w
```

Quit:

```vim
:q
```

Save and quit:

```vim
:wq
```

Quit without saving:

```vim
:q!
```

---

## Navigation

Move cursor:

```text
h → Left
j → Down
k → Up
l → Right
```

Move by words:

```text
w → Next word
b → Previous word
```

Go to start of line:

```text
0
```

Go to end of line:

```text
$
```

Go to beginning of file:

```text
gg
```

Go to end of file:

```text
G
```

---

## Copy, Cut, and Paste

Copy line:

```text
yy
```

Copy multiple lines:

```text
5yy
```

Delete line:

```text
dd
```

Delete multiple lines:

```text
5dd
```

Paste below:

```text
p
```

Paste above:

```text
P
```

---

## Undo and Redo

Undo:

```text
u
```

Redo:

```text
Ctrl + r
```

---

## Search

Search text:

```text
/search_term
```

Example:

```text
/python
```

Next result:

```text
n
```

Previous result:

```text
N
```

---

## Replace Text

Replace first occurrence in current line:

```vim
:s/old/new/
```

Replace all occurrences in current line:

```vim
:s/old/new/g
```

Replace entire file:

```vim
:%s/old/new/g
```

---

## Line Numbers

Show line numbers:

```vim
:set number
```

Hide line numbers:

```vim
:set nonumber
```

---

## Split Windows

Horizontal split:

```vim
:split
```

Vertical split:

```vim
:vsplit
```

Switch windows:

```text
Ctrl + w
```

---

## Useful Shortcuts

Save:

```text
:w
```

Save and quit:

```text
:wq
```

Undo:

```text
u
```

Redo:

```text
Ctrl + r
```

Search:

```text
/
```

Copy:

```text
yy
```

Paste:

```text
p
```

Delete line:

```text
dd
```

---

## Summary

Important concepts:

- Normal Mode
- Insert Mode
- Visual Mode
- Command Mode

Common commands:

- :w
- :q
- :wq
- yy
- dd
- p
- u
- gg
- G
- /search

Neovim is one of the most powerful terminal-based editors and is widely used in Linux, DevOps, and software development workflows.
