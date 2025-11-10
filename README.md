# GIT ADVANCED EXERCISES

Exercises on essential Git Skills

## Challenges

### Part 1: Refining Git History (10 challenges)

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

In vim, **_pick_** was changed to **reword** which enabled me to changed the commit.

3. Keeping History Tidy - Squashing Commits:

```
git rebase -i --root
```

In vim, **_pick_** was changed to **squash** on the second commit after the oldest.

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
