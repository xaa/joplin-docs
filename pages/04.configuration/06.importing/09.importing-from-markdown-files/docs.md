---
title: 'Importing from Markdown files'
date: '15:06 15-11-2021'
taxonomy:
    category:
        - docs
---

Joplin can import notes from plain Markdown file. You can either import a complete directory of Markdown files or individual files.

In the **desktop application**:
* **File import**: Go to File > Import > MD - Markdown (file) and select the Markdown file. This file will then be imported to the currently selected Notebook.
* **Directory import**: Go to File > Import > MD - Markdown (directory) and select the top level of the directory that is being imported. Directory (folder) structure will be preserved in the Notebook > Subnotebook > Note structure within Joplin.

In the **terminal application**, in [command-line mode](https://github.com/laurent22/joplin/blob/dev/readme/terminal.md#command-line-mode), type `import --format md /path/to/file.md` or `import --format md /path/to/directory/`.

