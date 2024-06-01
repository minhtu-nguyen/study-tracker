##   Git Get Started
```bash
git config --global user.name "test"
git config --global user.email "test@email.com"
git init 
```
If you want to set the username/e-mail for just the current repo, you can remove global
##   Git New Files
`git status`
##   Git Staging Environment
```bash
git add index.html
git add --all
```
##   Git Commit
`git commit -a -m "Updated index.html with a new line"`
##   Git Help
`git commit -help`
##   Git Branch
```js
git branch hello-world-images // new branch
git branch // list branches
git checkout hello-world-images // swtich branch
git checkout -b emergency-fix // create a new branch to deal with the emergency
```
##   Git Branch Merge
```js
git checkout master
git merge emergency-fix // merge the current branch (master) with emergency-fix 
git branch -d emergency-fix // Deleted branch emergency-fix
```
##   GitHub Get Started
```js
git remote add origin URL // adding a remote repository, with the specified URL, as an origin to your local Git repo
git push --set-upstream origin master
```
##   Pull from GitHub
```js
git fetch origin // updates to see what has changed on GitHub
git diff origin/master // differences between our local master and origin/master
git merge origin/master // merge our current branch (master) with origin/master

// pull is a combination of fetch and merge
git pull origin // keep your local Git up to date from a remote repository
```
##   Push to GitHub
```js
git push origin // push our changes to our remote origin
```
##   Pull Branch from GitHub
```js
git branch -a  // -a option to see all local and remote branches
git branch -r  // remote branches only
```
##   Push Branch to GitHub
`git push origin update-readme`
Push the branch from our local Git repository, to GitHub
##   Git Clone from GitHub
`git clone URL`
Configuring Remotes
`git remote -v`
Rename
`git remote rename origin upstream`, rename the original `origin` to `upsteam`
`git remote add origin URL`
According to Git naming conventions, it is recommended to name your own repository origin, and the one you forked for upstream
##   GitHub Send Pull Request
`git push origin`
##   Git .gitignore
It is also possible to ignore files or folders but not show it in the distributed .gitignore file.

These kinds of ignores are specified in the .git/info/exclude file. It works the same way as .gitignore but are not shown to anyone else.
##   Git Security SSH
`ssh-keygen -t rsa -b 4096 -C "test@w3schools.com"`
`ssh-add /Users/user/.ssh/id_rsa` --> add to SSH-Agent
##   Git Revert
`revert` is the command we use when we want to take a previous `commit` and add it as a new `commit`, keeping the `log` intact.
`git log --oneline` --> find the point we want to return to
`git revert HEAD --no-edit` --> We revert the latest commit using git revert HEAD (revert the latest change,  and then commit), adding the option --no-edit to skip the commit message editor (getting the default revert message)
To revert to earlier commits, use `git revert HEAD~x` (`x` being a number. 1 going back one more, 2 going back two more, etc.)
##   Git Reset
`reset` is the command we use when we want to move the repository back to a previous `commit`, discarding any changes made after that `commit`.
`git reset 9a9add8`
Even though the commits are no longer showing up in the log, it is not removed from Git. If you know the `commit` hash you can undo the reset to it.
##   Git Amend
commit --amend is used to modify the most recent commit.

It combines changes in the staging environment with the latest commit, and creates a new commit.

This new commit replaces the latest commit entirely.   
`git commit --amend -m "Added lines to README.md"`
##   Git Exercises",
##   Git Quiz",
##   Git Certificate"