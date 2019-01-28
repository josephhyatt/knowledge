# Github Basics

![](https://cdn-images-1.medium.com/max/800/1*Exha3gygzS64WvrfjUVj-Q.jpeg)

If you want to be a developer then you should get used to git. Here are a few basic commands to get you started.

## Current State

`git status` list which \(unstaged\) files have changed  
`git diff` list \(unstaged\) changes to files  
`git log` list recent commits

## Adding Files to Repo

`git add fn` stage file  
`git commit -m 'message'` commit file  
`git commit -am 'message'` add/commit all changes from all tracked files \(no untracked files\) in one go

## Undoing Previous Actions

`git reset filename` unstage file  
`git commit --amend -m 'message'` alter the last commit \(add any staged files, new comment\)  
`git reset --soft HEAD^` undo the previous commit, put changes in staging  
`git reset --hard HEAD^` Undo last commit and all changes  
`git reset --hard HEAD^^` Undo two \(^^\) last commits and all changes  
`git checkout -- cats.html index.html` Undo all changes that were made to files cats.html and index.html  
`git rebase --onto <commit-id>\^ <commit-id> HEAD` remove specific commit from the repository. the \ in ^ is just an escape char to make zsh play nice and is not necessary if using bash.

## Remote Repositories

`git remote add origin git@example.com:example/petshop.git` add a remote repository  
`git push -u origin master` push current local repo to remote. -u sets it to default for the future  
`git remote -v show` show the available remote repositories that have been added  
`git pull` checkout and merge remote changes in one go  
`git fetch origin` update the local cache of the remote repository  
`git remote -v update` bring remote refs up to date \(and -v show which branches were updated\)  
`git status -uno` will tell you whether the branch you are tracking is ahead, behind or has diverged. If it says nothing, the local and remote are the same.  
`git show-branch *master` will show you the commits in all of the branches whose names end in master \(eg master and origin/master\).  
`git show remote origin` show local&lt;-&gt;remote branch tracking and sync status

## Examine Changes on Remote, Without Pulling Them

`git fetch origin`  
`git log HEAD..origin/master --oneline` shows commit messages  
`git diff HEAD..origin/master` shows all changes on remote compared to local HEAD

## Branches

`git branch` list currently existing branches  
`git branch [branchname]` create new branch  
`git checkout branchname` move to that branch  
`git checkout -b branchname` create and check out new branch in one go  
`git branch -d branchname` remove branch

## **merging a branch back to master**

`git checkout master; git merge branchname;` conditions for fast-forwarding merge - nothing new on master between branch start/end points

## Branches on Remote

```git fetch origin``git branch -r``` list remote branches \(after a fetch\)  
`git push origin :branchname` delete remote branch 'branchname'  
`git remote prune origin` clean up deleted remote branches \(let's say someone else deleted a branch on the remote\)  
`git show remote origin` show local&lt;-&gt;remote branch tracking and sync status \(duplicate info under "remote repositories"\)

## **push local branch to differently named remote branch. Eg Heroku only deploys master**

`git push heroku yourbranch:master` simple form  
`git push heroku-staging staging:master` \(localBranchName:remoteBranchName\)

## Tagging

`git tag` list all tags  
`git checkout v0.0.1` checkout code  
`git tag -a v0.0.3` -m 'Version 0.0.3' add new tag  
`git push --tags` push new tags to remote

## Dealing With Large Files — Keep them outside the repo on an ssh machine.

`git annex add mybigfile`  
`git commit -m 'add mybigfile'`  
`git push myremote` `git annex copy --to myremote mybigfile` this command copies the actual content to my remote  
`git annex drop mybigfile` remove content from local repo  
`git annex get mybigfile` retrieve the content  
`git annex copy --from myremote mybigfile`specify the remote from which to get the file

