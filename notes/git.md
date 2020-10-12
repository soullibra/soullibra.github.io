# Git commands

```shell
git config --global user.name "[name]"
git config --global user.email "[email address]"

git init [repository path]
git clone [url]
```

**Connect** your local repository to the remote server:

```shell
git remote add [variable name] [Remote Server Link]
```

```shell
git add [file]
git add *

git rm [file]

git commit -m "[Type in the commit message]"
git commit -a

git tag [commitID]

git reset [file]
git reset [commit]
git reset –hard [commit]
```

```shell
git status

git log
git log --follow [file]

git show [commit]

git diff
git diff –staged
git diff [first branch] [second branch]
```

**List** all the local branches:

```shell
git branch
```

**Create** a new branch:

```shell
git branch [branch name]
```

**Create** a new branch and also **switch** to it:

```shell
git checkout -b [branch name]
```

**Delete** the feature branch:

```shell
git branch -d [branch name]
```

**Switch** branch to:

```shell
git checkout [branch name]
```

**Merge** the specified branch’s history into the current branch:

```shell
git merge [branch name]
```

**Send** the committed changes of master branch to your remote repository:

```shell
git push [variable name] master
```

**Send** the branch commits to your remote repository:

```shell
git push [variable name] [branch]
```

**Push** all branches to your remote repository:

```shell
git push –all [variable name]
```

**Fetch** and **merge** changes on the remote server to your working directory:

```shell
git pull [Repository Link]
```

### Log

```shell
git log -10
git log --pretty=oneline
git log --oneline
git log --oneline --abbrev-commit
git log --graph
git log --name-status
```

Show last commit changes

```shell
git diff HEAD^ HEAD
git diff HEAD^ HEAD -- [file name]
```

### Stash

Temporarily stores all the modified tracked files:

```shell
git stash save
git stash pop
git stash list
git stash drop
```

Stash diff

```shell
git stash show -p stash@{0}
```

Stash diff one file

```shell
git diff stash@{0} -- [file name]
```

Stash apply one file

```shell
git checkout stash@{0} -- [file name]
```

### Reverts

Revert last commit (not pushed)

```shell
git reset HEAD~1 --soft
```

Revert file changes (not committed)

```shell
git checkout -- [file name]
git checkout -- *
```

### Tags

List tags

```shell
git tag
git tag -l <*pattern*>
```

List tags with their commits

```shell
git log --oneline --tags --no-walk
```

List tags with their commits' references

```shell
git show-ref --tags -d
```

Create tag

```shell
git tag <tag name>
git push --tags
```

Delete tag

```shell
git tag -d <tag name>
git push origin :refs/tags/<tag name>
```

### Gitk

```shell
gitk
gitk --follow [filename]
```
