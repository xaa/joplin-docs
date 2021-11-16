---
title: 'Create a Pull Request'
date: '23:14 20-11-2021'
taxonomy:
    category:
        - docs
custom:
    git_note_source: 'https://discourse.joplinapp.org/t/how-to-create-a-pull-request-pr/15052'
page-toc:
    active: true
---

This topic is for people who never used Git before or are not familiar with GitHub's PR concept. This information is about how to use the git command, but there are also UI tools available and other commandline tools like gh and hub which make using Git a bit easier.

## Initial setup

First you have to fork the Joplin repository. Go to https://github.com/laurent22/joplin 2 and click on the Fork button.

After this is done, you will have a new repo under your gh user:  
`https://github.com/YOURUSERNAME/joplin` (replace YOURUSERNAME with your gh username).

Now you have to clone this new repository to be able to make code changes:
`git clone git@github.com:YOURUSERNAME/joplin.git`

This will create a joplin directory where you ran the clone command. Your source tree is now available. To update the source tree later on, you'll have to add the upstream remote. Change into your source tree directory and run the following command:
`git remote add upstream https://github.com/laurent22/joplin.git`

## Creating a new branch

Every time you want to submit a PR, your code changes should be based on the latest commit in the dev branch.

(Right after forking and cloning the repository you don't have to do the following step. But it definitely does not hurt doing so anyway.)

The following commands will pull the latest changes of the dev branch from upstream:
```
git checkout dev
git pull upstream dev
```
Now you can create a new branch based off the dev branch.
Please note that you either have to use a new branch name, or in case you want to re-use a branch name you will have to delete the previous local and remote branch names.

For the following commands, replace BRANCHNAME with the name you want to use. e.g. translation/xx_XX

`git checkout -b BRANCHNAME`

Time for coding...

Do your code changes. When you are done, add the file(s) to your index and commit the files.

Make sure that when you are using git add -A that you don't add unwanted files to the index.

```
git add FILNAME1 FILENAME2
git commit -m "Add a nice commit message here."
```

Almost done. The last step before creating a PR is pushing your changes to your fork:

git push origin BRANCHNAME`

## Creating the PR
Go to [https://github.com/laurent22/joplin](https://github.com/laurent22/joplin) and a message should tell you that a new branch has been pushed to a fork. There is a also a button to create a Pull Request. Guess what. 😉 Click it.