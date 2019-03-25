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

## Cheat Sheet

| Command | Usage |
| :--- | :--- |
| git init | Creates an empty Git repository in the specified directory. |
| git clone &lt;repository name&gt; | Clones a repository located at &lt;repository name&gt; onto your local machine. |
| git add &lt;directory&gt; | Stages only the specified changes for the next commit. Replace &lt;directory&gt; with a &lt;file&gt; to change a specific file. |
| git add . | Stages new files and modifications without deletions |
| git add -A | Stages all changes |
| git add -all | Equivalent to git add -A |
| git add -u | Stages modifications and deletions without adding new files |
| git add --update | Equivalent to git add -u |
| git commit -m ”&lt;message&gt;” | Commits the staged snapshot. replace &lt;message&gt; with the commit message. |
| git status | List which files are staged unstaged and untracked. |
| git log | Displays the entire commit history using the default format. |
| git diff | Shows unstaged changes between your index and working directory. |
| git pull | Fetchs the remote copy of the current branch. |
| git pull --rebase &lt;remote&gt; | Fetchs the remote copy of current branch and rebases it into the local copy. Use git rebase instead of merge to integrate the branches. |
| git push origin master | Push all of your commits to master branch. |
| git push &lt;remote&gt; --all | Push all of your local branches to the specified remote. |
| git push &lt;remote&gt; --tags | Tags aren’t automatically pushed when you push a branch or use the --all flag. The --tags flag sends all of your local tags to the remote repo. |
| git push &lt;remote&gt; --force | Forces the git push even if it results in a non-fast-forward merge. Do not use the --force flag unless you’re absolutely sure you know what you’re doing. |
| git revert &lt;commit&gt; | Creates new commit that undoes all of the changes made in &lt;commit&gt; and then applys it to the current branch. |
| git reset &lt;file&gt; | Removes &lt;file&gt; from the staging area but leaves the working directory unchanged - This unstages a file without overwriting any changes. |
| git clean -n | Shows which files would be removed from working directory. Use the -f flag in place of the -n flag to execute the clean. |
| git commit --amend | Replaces the last commit with the staged changes and last commit combined. Use with nothing staged to edit the last commit’s message. |
| git rebase &lt;base&gt; | Rebase the current branch onto &lt;base&gt;. &lt;base&gt; can be a commit ID a branch name a tag or a relative reference to HEAD. |
| git reflog | Show a log of changes to the local repository’s HEAD. Add --relative-date flag to show date info or --all to show all refs. |
| git branch | Lists all of the branches in your repo. |
| git branch &lt;branch name&gt; | Creates a new branch with the name &lt;branch name&gt;. |
| git checkout -b &lt;branch name&gt; | Creates and check out a new branch named &lt;branch name&gt;. |
| git checkout &lt;branch name&gt; | Checkout an existing branch. |
| git merge &lt;branch&gt; | Merge &lt;branch&gt; into the current branch. |
| git remote add &lt;name&gt; &lt;url&gt; | Creates a new connecti |
| git log --stat | Include which files were altered and the relative number of lineson to a remote repo. After adding a remote you can use &lt;name&gt; as a shortcut for &lt;url&gt; in other commands. |
| git fetch &lt;remote&gt; &lt;branch&gt; | Fetches a specific &lt;branch&gt; from the repo. Leave off &lt;branch&gt; to fetch all remote refs. |
| git pull &lt;remote&gt; | Fetches the specified remote’s copy of current branch and immediately merge it into the local copy. |
| git push &lt;remote&gt; &lt;branch&gt; | Pushes the branch to &lt;remote&gt; along with necessary commits and objects. Creates named branch in the remote repo if it doesn’t exist. |
| git config --global user.name &lt;name&gt; | Defines the author name to be used for all commits by the current user. |
| git config --global user.email &lt;email&gt; | Defines the author email to be used for all commits by the current user. |
| git config --global alias. &lt;alias-name&gt; &lt;git-command&gt; | Creates shortcut for a Git command. E.g. alias.p push will set git p equivalent to git push. |
| git config --system core.editor &lt;editor&gt; | Set text editor used by commands for all users on the machine. &lt;editor&gt; arg should be the command that launches the desired editor \(e.g; vi\). |
| git config --global --edit | Opens the global configuration file in a text editor for manual editing. |
| git log -&lt;limit&gt; | Limits the number of git rebase -i E.g. git log -5 will limit to 5 commits. |
| git log --oneline | Condenses each commit to a single line. |
| git log -p | Displays the full diff of each commit. |
| git log --stat | Include which files were altered and the relative number of lines that were added or deleted from each of them. |
| git log --author= ”&lt;pattern&gt;” | Searchs for commits by a particular author. |
| git log --grep=”&lt;pattern&gt;” | Searchs for commits with a commit message that matches &lt;pattern&gt;. |
| git log &lt;since&gt;..&lt;until&gt; | Shows commits that occur between &lt;since&gt; and &lt;until&gt;. Args can be a any kind of revision reference. |
| git log -- &lt;file&gt; | Only display commits that have the specified file. |
| git log --graph --decorate | --graph flag draws a text based graph of commits on left side of commit msgs. --decorate adds names of branches or tags of commits shown. |
| git diff HEAD | Shows difference between working directory and last commit. |
| git diff --cached | Shows difference between staged changes and last commit |
| git reset | Resets the staging area to match most recent commit but leaves the working directory unchanged. |
| git reset --hard | Resets the staging area and working directory to match most recent commit and overwrites all changes in the working directory. |
| git reset &lt;commit&gt; | Moves the current branch tip backward to &lt;commit&gt; resets the staging area to match but leaves the working directory unchanged. |
| git reset --hard &lt;commit&gt; | Same as previous but resets both the staging area & working directory to match. Deletes uncommitted changes and all commits after &lt;commit&gt;. |
| git rebase -i &lt;base&gt; | Interactively rebase current branch onto &lt;base&gt;. Launches editor to enter commands for how each commit will be transferred to the new base. |

