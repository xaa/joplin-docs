---
title: 'Notes deleted by accident'
date: '17:06 15-11-2021'
taxonomy:
    category:
        - docs
---

## I deleted some notes by accident and don't have a backup

If you know the `NOTE_ID` and have note history enabled you can run the command `restoreNoteRevision` from the command palette e.g. `restoreNoteRevision 66457326a6ba4adeb4be8ce05e37af0d`. 

Joplin will then confirm if the restore was successful and place the note in a "Restored Note" notebook.

If you do not know the `NOTE_ID` then you can find this within the Joplin sqlite database as the `item_id` within the `deleted_items` or `revisions` tables. It will require some manual checking of the `title_diff` and `body_diff` fields to check if the `ITEM/NOTE_ID` you are targeting is the correct one.

You should first take a copy of the database to avoid making any accidental changes in the live one.

For further information go [here](https://discourse.joplinapp.org/t/restoring-deleted-notes/21304).