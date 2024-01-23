# Git Commands

## Commit Message

> Good commit message guide: https://hashnode.com/post/which-commit-message-convention-do-you-use-at-work-ck3e4jbdd00zyo4s1h7mc7e0g

## SSH Key

> Guide: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

> Guide: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

## Basic

> Basic git commands: https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html

### 1. To update local repo to the state of remote

```bash
git fetch origin

# is the best utility for cleaning outdated branches. It will connect to a shared remote repository remote and fetch all remote branch refs. It will then delete remote refs that are no longer in use on the remote repository

git fetch --prune
```

### 2. Delete all remote branches that have already been merged:

```
git branch --merged | grep -v \* | xargs git branch -D
```

### 3. Delete all tracking branches whose remote equivalent no longer exists:

```
git fetch -p && for branch in $(git for-each-ref --format '%(refname) %(upstream:track)' refs/heads | awk '$2 == "[gone]" {sub("refs/heads/", "", $1); print $1}'); do git branch -D $branch; done
```

### 4. Cherry-pick commit:

```
git cherry-pick <commit_hash>
```

### 5. Reset repo to a particular commit (this deletes the changes made):

```
 git reset --hard <commit_hash>
 git push -f <remote_name> main
```

### 6. Rename a local branch:

```bash
git branch -m <new_name>
```

### 7. Viewing the difference in current code:

```bash
git diff
```

### 8. Undo last commit:

```bash
git reset HEAD~
```

## Git bisect

> Guide: https://www.metaltoad.com/blog/beginners-guide-git-bisect-process-elimination

## Git Stash

TODO

## Git hunk

TODO

## Git amend in VSCode

TODO
