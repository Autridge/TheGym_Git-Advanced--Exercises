# GIT ADVANCED EXERCISES

Exercises on essential Git Skills

## Challenges

### Part 1: Refining Git History

1. Missing File Fix

```
git add test4.md
git commit -- amend -m "chore: Added third and fourth files"
```

2. Editing Commit History

```
git log --oneline
git rebase -i HEAD~3
```

In vi, **_pick_** was changed to **reword** which enabled me to edit the commit.

3. Keeping History Tidy - Squashing Commits:

```
git rebase -i --root
```

In vi, **_pick_** was changed to **squash** on the second commit after the oldest.

4. Splitting a Commit:

```
git rebase -i HEAD~4
git reset --soft
git reset HEAD^
git add test3.md
git commit -m 'chore: Create third file'
git add test4.md
git commit -m 'chore: Create fourth file'
git rebase --continue
git push --force-with-lease
```

5. Advanced Squashing

```
git rebase -i HEAD~5
git push --force-with-lease
```

6. Dropping a Commit

```
touch unwanted.txt
git add unwanted.txt
git commit -m 'Unwanted file'
git reset --hard HEAD~1
```

7. Reordering Commits:

```
git rebase -i --root

```

In vi, **dd** was used to cut the line that was moved above and **p** pasted it.

8. Cherry-Picking Commits

```
git checkout -b ft/branch
touch test5.md
git add test5.md
git commit -m 'Implemented test 5'
git log --oneline
git switch main
git cherry-pick --no-commit caa08a7
```

9. Visualizing Commit History

```
git log --graph
```

### Part 2: Branching Basics

1. Feature Branch Creation

```
git checkout -b ft/new-feature
```

2. Working on the Feature Branch

```
touch feature.txt
git add feature.txt
git commit -m 'Implemented core functionality for new feature'
```

3. Switching Back and Making More Changes

```
git switch main
echo 'This is an advanced git learning document.' > readme.txt
git add readme.txt && git commit -m "Updated project file"
```

5. Branch Deletion

```
git switch main
git merge ft/new-feature
git branch -d ft/new-feature
```

6. Creating a Branch from a Commit

```
git log --oneline --graph
git checkout -b ft/new-branch-from-commit 48035b0
```
