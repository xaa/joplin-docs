---
title: 'Restoring deleted note'
date: '17:06 15-11-2021'
taxonomy:
    category:
        - docs
media_order: 'restore-note (1).png,restore-note (2).png,restore-note (3).png,restore-note (4).png,restore-note (5).png'
custom:
    git_note_source: 'https://discourse.joplinapp.org/t/restoring-deleted-notes/21304'
---

This is a step-by-step instructional guide on how to restore accidentally deleted notes in Joplin using the restoreNoteRevision command as well as how to find your missing notes in the Joplin database.
This assumes that you do not have a note backup of any kind (other clients, profile backups, JEX export etc.) and you have otherwise run out of options to get the data back.

If you are familiar with Joplin commands and have the ability to open the sqlite database then the more concise instructions can be found in the [Joplin FAQ](https://joplinapp.org/faq/#i-deleted-some-notes-by-accident-and-don-t-have-a-backup).

## Prerequisites
- Joplin desktop newer than v2.0.8 (ideally latest released version)
- A method of opening and browsing SQLite databases. This guide will focus on using [SQLiteStudio](https://sqlitestudio.pl/), available for Windows, macOS and Linux, but you can use any other tools you like if you are more comfortable with them.
- You have note history enabled and are within the configured keep period - see [Joplin Help](https://joplinapp.org/help/#note-history)

## Step-by-step

If you know the note ID of your missing notes (for example if you have backlinks or have copied the internal Joplin reference at some point then you can skip the database steps and go straight to step 7). Otherwise follow as below:

1. Locate and open a file browser to your Joplin profile directory Help `> Open Profile Directory`.  
You should have a `database.sqlite` file.  
Take a copy of this file and save with a new name as we don't want to make accidental changes to the live copy.
3. Open SQLiteStudio and `click Database > Add a database`.  
Leave the database type as SQLite3 and press the folder icon on the File box.  
Navigate to the file you created in step 1 and select it. Press `OK`.  
Right click the database you added in the Databases panel and click `Connect to the Database`. 
You should see it expand into the Joplin database schema.
![restore-note%20%281%29](restore-note%20%281%29.png "restore-note%20%281%29")
4. Double click the revisions table in this panel and then click the Data tab on the newly opened page.
5. Sort the database by clicking the created\_time column twice so it looks like this:  
![restore-note%20%283%29](restore-note%20%283%29.png "restore-note%20%283%29")
This will sort the table in order of updates so any changes you made most recently should now be at the top of the table.
6. Now comes the manual step, you will need to look carefully at the data contained in the title\_diff and body\_diff columns in order to identify your missing notes. If you can't see all of it then you can resize the column and hit the small double arrows to load the rest of the content. You can even copy that field and paste into an editor of your choice to see the data more clearly.  
Once you have identified your note you need to look towards the left side and find the item\_id column (should be the 4th column). Copy that ID (it should be a long string of characters like 0133246cb05f406586f4e4b9fcde92fd ).
7. Back in Joplin press `Tools > Command Palette` (Windows/Linux) or `Joplin > Command Palette` (macOS).  
Alternatively press `Ctrl + Shift + P` (Windows/Linux) or `Cmd + Shift + P` (macOS).  
Type restoreNoteRevision followed by a space and then paste your item\_id you copied and hit return.
![restore-note%20%284%29](restore-note%20%284%29.png "restore-note%20%284%29")
If successful you should see something similar to the following:
![restore-note%20%285%29](restore-note%20%285%29.png "restore-note%20%285%29")
And as the popup says, you should now find your note in a new notebook named Restored Notes.
8. Repeat the process for any other notes you have lost.

## Further Comments

- To avoid having to do this in the future you should make sure you always have a recent backup of your data. The [Simple Backup](https://discourse.joplinapp.org/t/backup-plugin/13964) plugin is highly recommended for this as it can create scheduled backups of not only your profile directory but also automate a full lossless JEX export containing all your notes.
- If your only client is a mobile one then the above may still be possible but you will need to export your profile, copy it to a computer and use the mobile database in place of the desktop one. This is currently only possible on Android but that is beyond the scope of this revision of the guide.
- If you have more than one client connected to your sync target and the other client has not yet synced the deleted notes then it will probably be easier to work from that client by preventing it from syncing (ideally just disconnect from the network) and exporting the note(s) in question where you can easily import it again afterwards.

## Other Resources

### Guides
[Joplin FAQ 2](https://joplinapp.org/faq/#i-deleted-some-notes-by-accident-and-don-t-have-a-backup)  
[How-to by @theCollectiv](https://discourse.joplinapp.org/t/please-document-better-how-to-recover-notes/19619) with focus on Snap and Sqlite command line tools  
[How-to by @ridgeway 1](https://discourse.joplinapp.org/t/how-to-recover-deleted-notes/17907/7) with focus on Sqlite command line tools  

### Downloads
[SQLiteStudio](https://sqlitestudio.pl/)  
[DB Browser for SQLite](DB Browser for SQLite)
