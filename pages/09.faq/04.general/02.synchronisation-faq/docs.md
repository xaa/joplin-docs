---
title: 'Synchronisation FAQ'
date: '17:06 15-11-2021'
taxonomy:
    category:
        - docs
page-toc:
    active: true
---

## How can I check the sync status?

Go to the synchronisation page. You can find it on the desktop application under `Help > Synchronisation Status` and on the mobile app under `Configuration > SYNC STATUS`.

`total items` = How many items there are in total to sync.  
`synced items` = How many items have already been uploaded or downloaded.

If `total items` and `synced items` are equal, all data has been synced. Also all devices should have the same `total items`.

## The initial sync is very slow, how to speed it up?
Whenever importing a large number of notes, for example from Evernote, it may take a very long time for the first sync to complete. There are various techniques to speed thing up (if you don't want to simply wait for the sync to complete), which are outlined in [this post](https://discourse.joplinapp.org/t/workaround-for-slow-initial-bulk-sync-after-evernote-import/746?u=laurent).

## Not all notes, folders, or tags are displayed on the mobile app

Joplin does not have a background sync on mobile devices. When Joplin is closed, sent to the background or the device is put into sleep (display off), the sync is interrupted.

## Is it possible to use real file and folder names in the sync target?

Unfortunately it is not possible. Joplin synchronises with file systems using an open format however it does not mean the sync files are meant to be user-editable. The format is designed to be performant and reliable, not user friendly (it cannot be both), and that cannot be changed. Joplin sync directory is basically just a database.