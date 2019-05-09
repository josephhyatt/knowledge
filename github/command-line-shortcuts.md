# Command Line Shortcuts

## Aliases

| **Alias** | **Command** |
| :--- | :--- |
| g | git |
| ga | git add |
| gaa | git add --all |
| gapa | git add --patch |
| gau | git add --update |
| gb | git branch |
| gba | git branch -a |
| gbda | git branch --merged \| command grep -vE "^\(\*\|\s_master\s_$\)" \| command xargs -n 1 git branch -d |
| gbl | git blame -b -w |
| gbnm | git branch --no-merged |
| gbr | git branch --remote |
| gbs | git bisect |
| gbsb | git bisect bad |
| gbsg | git bisect good |
| gbsr | git bisect reset |
| gbss | git bisect start |
| gc | git commit -v |
| gc! | git commit -v --amend |
| gca | git commit -v -a |
| gcam | git commit -a -m |
| gca! | git commit -v -a --amend |
| gcan! | git commit -v -a -s --no-edit --amend |
| gcb | git checkout -b |
| gcf | git config --list |
| gcl | git clone --recursive |
| gclean | git clean -df |
| gcm | git checkout master |
| gcd | git checkout develop |
| gcmsg | git commit -m |
| gco | git checkout |
| gcount | git shortlog -sn |
| gcp | git cherry-pick |
| gcpa | git cherry-pick --abort |
| gcpc | git cherry-pick --continue |
| gcs | git commit -S |
| gd | git diff |
| gdca | git diff --cached |
| gdt | git diff-tree --no-commit-id --name-only -r |
| gdw | git diff --word-diff |
| gf | git fetch |
| gfa | git fetch --all --prune |
| gfo | git fetch origin |
| gg | git gui citool |
| gga | git gui citool --amend |
| ggf | git push --force origin $\(current\_branch\) |
| ghh | git help |
| ggpull | ggl |
| ggpur | ggu |
| ggpush | ggp |
| ggsup | git branch --set-upstream-to = origin/$\(current\_branch\) |
| gpsup | git push --set-upstream origin $\(current\_branch\) |
| gignore | git update-index --assume-unchanged |
| gignored | git ls-files -v \| grep "^[:lower:](https://github.com/robbyrussell/oh-my-zsh/wiki/%3Alower%3A)" |
| git-svn-dcommit-push | git svn dcommit && git push github master:svntrunk |
| gk | \gitk --all --branches |
| gke | \gitk --all $\(git log -g --pretty = format:%h\) |
| gl | git pull |
| glg | git log --stat --color |
| glgg | git log --graph --color |
| glgga | git log --graph --decorate --all |
| glgm | git log --graph --max-count = 10 |
| glgp | git log --stat --color -p |
| glo | git log --oneline --decorate --color |
| glog | git log --oneline --decorate --color --graph |
| glol | git log --graph --pretty = format:'%Cred%h%Creset -%C\(yellow\)%d%Creset %s %Cgreen\(%cr\) %C\(bold blue\)&lt;%an&gt;%Creset' --abbrev-commit |
| glola | git log --graph --pretty = format:'%Cred%h%Creset -%C\(yellow\)%d%Creset %s %Cgreen\(%cr\) %C\(bold blue\)&lt;%an&gt;%Creset' --abbrev-commit --all |
| glp | \_git\_log\_prettily |
| gm | git merge |
| gmom | git merge origin/master |
| gmt | git mergetool --no-prompt |
| gmtvim | git mergetool --no-prompt --tool = vimdiff |
| gmum | git merge upstream/master |
| gp | git push |
| gpd | git push --dry-run |
| gpoat | git push origin --all && git push origin --tags |
| gpristine | git reset --hard && git clean -dfx |
| gpu | git push upstream |
| gpv | git push -v |
| gr | git remote |
| gra | git remote add |
| grb | git rebase |
| grba | git rebase --abort |
| grbc | git rebase --continue |
| grbi | git rebase -i |
| grbm | git rebase master |
| grbs | git rebase --skip |
| grh | git reset HEAD |
| grhh | git reset HEAD --hard |
| grmv | git remote rename |
| grrm | git remote remove |
| grset | git remote set-url |
| grt | cd $\(git rev-parse --show-toplevel \|\| echo "."\) |
| gru | git reset -- |
| grup | git remote update |
| grv | git remote -v |
| gsb | git status -sb |
| gsd | git svn dcommit |
| gsi | git submodule init |
| gsps | git show --pretty = short --show-signature |
| gsr | git svn rebase |
| gss | git status -s |
| gst | git status |
| gsta | git stash save |
| gstaa | git stash apply |
| gstd | git stash drop |
| gstl | git stash list |
| gstp | git stash pop |
| gstc | git stash clear |
| gsts | git stash show --text |
| gsu | git submodule update |
| gts | git tag -s |
| gunignore | git update-index --no-assume-unchanged |
| gunwip | git log -n 1 \| grep -q -c "--wip--" && git reset HEAD~1 |
| gup | git pull --rebase |
| gupv | git pull --rebase -v |
| gupa | git pull --rebase --autostash |
| gupav | git pull --rebase --autostash -v |
| glum | git pull upstream master |
| gvt | git verify-tag |
| gwch | git whatchanged -p --abbrev-commit --pretty = medium |
| gwip | git add -A; git rm $\(git ls-files --deleted\) 2&gt; /dev/null; git commit -m "--wip--" |

### Deprecated Aliases

These are aliases that have been removed, renamed, or otherwise modified in a way that may, or may not, receive further support.

| Alias | Command | Modification |
| :--- | :--- | :--- |
| gap | git add --patch | new alias `gapa` |
| gcl | git config --list | new alias `gcf` |
| gdc | git diff --cached | new alias `gdca` |
| gdt | git difftool | no replacement |
| ggpull | git pull origin $\(current\_branch\) | new alias `ggl` \(`ggpull` still exists for now though\) |
| ggpur | git pull --rebase origin $\(current\_branch\) | new alias `ggu` \(`ggpur` still exists for now though\) |
| ggpush | git push origin $\(current\_branch\) | new alias `ggp` \(`ggpush` still exists for now though\) |
| gk | gitk --all --branches | now aliased to `\gitk --all --branches` |
| glg | git log --stat --max-count = 10 | now aliased to `git log --stat --color` |
| glgg | git log --graph --max-count = 10 | now aliased to `git log --graph --color` |
| gwc | git whatchanged -p --abbrev-commit --pretty = medium | new alias `gwch` |
| gwip | git add -A; git ls-files --deleted -z \| xargs -r0 git rm; git commit -m "--wip--" | now aliased to `git add -A; git rm $(git ls-files --deleted) 2> /dev/null; git commit -m "--wip--"` |

### Functions

#### Current

| Command | Description |
| :--- | :--- |
| current\_branch | Return the name of the current branch |
| current\_repository | Return the names of the current remotes |
| git\_current\_user\_name | Returns the `user.name` config value |
| git\_current\_user\_email | Returns the `user.email` config value |

#### WiP

These features allow to pause a branch development and switch to another one \(_"Work in Progress"_, or wip\). When you want to go back to work, just unwip it.

| Command | Description |
| :--- | :--- |
| work\_in\_progress | Echoes a warning if the current branch is a wip |
| gwip | Commit wip branch |
| gunwip | Uncommit wip branch |

