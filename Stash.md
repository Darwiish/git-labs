#  Git Stash Guide

```
         Start working on main
               |
               v
     Create / modify files
               |
               v
      git add <file> (optional)
               |
               v
   More changes (not staged yet)
               |
               v
     🔹 Need to switch task (hotfix)
               |
               v
 git stash push -m "WIP changes"
               |
               v
     Working directory clean
               |
               v
        Do other work
     (e.g. create hotfix file)
               |
               v
     git add hotfix.txt
               |
               v
     git commit -m "hotfix"
               |
               v
           git push
               |
               v
     Return to previous work
               |
               v
     git stash apply
        OR
     git stash pop
               |
               v
   Changes restored (same state)
               |
               v
   Continue working or commit
```
-----

## Example Changes

- Before stash:
  - "incomplete work"
  - "more changes not staged"

- During hotfix:
  - "hotfix applied"

- After restore:
  - "incomplete work"
  - "more changes not staged"

-----

## Visual Diagram

```
        ┌─────────────┐
        │   Working   │
        │ "incomplete work"
        │ "more changes"
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │    STASH    │
        │ saved state │
        └──────┬──────┘
               │
       (clean working dir)
               │
               ▼
        ┌─────────────┐
        │   Hotfix    │
        │ "hotfix applied"
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │ Restore     │
        │ apply / pop │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │   Working   │
        │ restored WIP│
        └─────────────┘
```

- git stash push -m "message"   # Save changes
- git stash -u                  # Include untracked files
- git stash list                # View stashes
- git stash apply               # Restore (keep stash)
- git stash pop                 # Restore + delete
- git stash drop stash@{0}      # Delete one stash
- git stash clear               # Delete all

---
Summary
- stash → save work
- apply → restore (keep)
- pop → restore + delete
