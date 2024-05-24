# Git advanced exercises solutions

This is the solution repository for the [git advanced exercise](https://github.com/HIRWA13/Git-exercise), it constists of three different parts if you are done solving them please feel free to check the solutions here.

## Part 1: Refining Git History

### Missing File Fix:

```
   24  git clone https://github.com/peninah98/git-exercises.git
   25  cd git-exercises/
   26  touch test{1..4}.md
   27  git add test1.md && git commit -m "chore: Create initial file"
   28  git add test2.md && git commit -m "chore: Create another file"
   29  git add test3.md && git commit -m "chore: Create third and fourth files"
   30  git status
   31  git log
   32  git add test4.md && git commit --amend
   33  history
```

### Editing Commit History:

```
   35  git rebase -i HEAD~3
   36  git commit --amend
   37  git rebase --continue
   38  git rebase -i HEAD~3
   39  git rebase --continue
   40  git rebase -i HEAD~3
   41  git commit --amend
   42  git log
   43  git status
   44  git rebase -i HEAD~3
   45  git commit --amend
   46  git rebase --continue
   47  history
```

### Keeping History Tidy - Squashing Commits:

```
   48  git rebase -i HEAD~3
   49  history
```

### Splitting a Commit:

```
   50  git reset HEAD~
   51  git add test3.md
   52  git commit -m "created third file"
   53  git add test4.md
   54  git commit -m "created fourth file"
   55  git log
   56  history
```

### Advanced Squashing:

```
  57  git rebase -i HEAD~3
  58  history
```

### Dropping a Commit:

```
   59  touch unwanted.txt
   60  git add .
   61  git commit -m "Unwanted commit"
   62  git rebase -i
   63  git log
   64  history
```

### Reordering Commits:

```
   65  git rebase -i
   66  git rebase -i HEAD~3
   67  git rebase -i HEAD~2
   68  history
```

### Cherry-Picking Commits:

```
   25  git checkout -b ft/branch
   26  touch test5.md
   27  git commit -a -m "Implemented test 5"
   28  git add test5.md
   29  git commit -m "Implemented test 5"
   30  git log
   31  git cherry-pick 07dd898e0bc3c5dc5376c7c5365928dfee5f8586
   32  git checkout main
   33  git cherry-pick 07dd898e0bc3c5dc5376c7c5365928dfee5f8586
   34  git add test5.md
   35  git cherry-pick --continue
   36  history
```

### Visualizing Commit History (Bonus)

```
   37  git log --graph
   38  git log
   39  git log --graph --oneline --color
   40  git log --graph --oneline --color --all
   41  git log --graph --oneline --color
   42  history
```

### Understanding Reflogs (Bonus)

```
   43  git reflog
   44  history
```

## Part 2: Branching Basics (10 Challenges)

### Feature Branch Creation:

```
   45  git branch
   46  git checkout -b ft/new-feature
   47  history
```

### Working on the Feature Branch:

```
   65  git checkout ft/new-feature
   66  touch feature.txt
   67  git add .
   68  git commit -m "Implemented core functionality for new feature"
```

### Switching Back and Making More Changes:

```
   69  git checkout main
   70  touch readme.txt
   71  git add .
   72  git commit -m "Updated project readme"
   73  history
```

### Branch Deletion:

```
   74  git branch
   75  git branch -d ft/new-feature
   76  git branch -D ft/new-feature
   77  git branch
   78  history
```

### Creating a Branch from a Commit:

```
   88  git log
   89  git checkout -b ft/new-branch-from-commit c6e511ee77e46449a65dcd61a13f36d29d39ac5a
   90  history
```

### Branch Merging:

```
   91  git checkout main
   92  git merge ft/new-branch-from-commit
   93  history
```

### Branch Rebasing:

```
   94  git rebase ft/new-branch-from-commit
   95  history
```

### Renaming Branches:

```
   98  git checkout main
   99  git branch -m ft/new-branch-from-commit ft/improved-branch-name
  100  history
```

### Checking Out Detached HEAD:

```
  101  git log
  102  gti checkout 1ee2b11641a7661a85dec5b959e1dbf48faa5294
  103  git checkout 1ee2b11641a7661a85dec5b959e1dbf48faa5294
  104  git switch -
  105  git checkout 1ee2b11641a7661a85dec5b959e1dbf48faa5294
  106  git switch -
  107  history
```

## Part 3: Advanced Workflows (10+ Challenges)

### Stashing Changes:

```
  124  git checkout main
  125  touch test5.md
  126  git stash
  127  history
```

### Retrieving Stashed Changes

```
  128  git stash pop
  129  git add .
  130  git commit -m "new file"
  131  history
```

### Branch Merging Conflicts (Continued):

```
  132  git add .
  133  git commit -m "updated test1.md"
  134  git branch
  135  git checkout ft/improved-branch-name
  136  git add .
  137  git commit -m "updated test1.md"
  138  git checkout main
  139  git status
  140  git merge ft/improved-branch-name
  141  git merge ft/improved-branch-name
  142  history
```

### Understanding Detached HEAD State:

```
  143  git mergetool
  144  git branch
  145  git checkout ft/branch
  146  history
```

### Ignoring Files/Directories:

```
  147  touch .gitignore
  148  history
```

### Working with Tags:

```
  149  git tag v1.0
  150  history
```

### Listing and Deleting Tags:

```
  151   git tag
  152  git tag -d v1.0
  153  history
```

### Pushing Local Work to Remote Repositories:

```
  154  git pull
  155  git status
  156  git add .gitignore
  157  git commit -m "created ignore file"
  158  git push
  159  history
```

### Pulling Changes from Remote Repositories:

```
  160  git pull origin main
  161  history
```
