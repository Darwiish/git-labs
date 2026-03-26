# Undoing in Git

This document explains how to undo changes in Git, including file-level, staging-level, and commit-level operations.

```

Working Directory   →   Staging Area (Index)   →   Git Repository (Commits)
     file changes            git add                 git commit
         ↑                      ↑                        ↑
         |                      |                        |
   git restore             git restore --staged       git reset / git revert

git restore <file>          → undo changes in working directory
git restore --staged <file> → unstage a file
git reset                   → undo commits (soft/mixed/hard)
git revert                  → create a new commit that reverses a previous one

```

```
HEAD -> Commit history
Index -> Staging area
WD   -> Working directory

          Before reset:
Commit1 - Commit2 - Commit3 (HEAD)
Index:   fileA fileB
WD:      fileA fileB

git reset --soft Commit1
HEAD -> Commit1
Index: fileA fileB    (staged)
WD:    fileA fileB    (unchanged)

git reset --mixed Commit1
HEAD -> Commit1
Index: (empty)        (unstaged)
WD:    fileA fileB    (unchanged)

git reset --hard Commit1
HEAD -> Commit1
Index: (empty)        (staged changes lost)
WD:    (empty)        (all working changes lost)

```

---
# Command Summary
- Command	Effect
- git restore <file>	Undo changes in working directory
- git restore --staged <file>	Unstage a file without discarding changes
- git reset --soft <commit>	Undo commits, keep changes staged
- git reset --mixed <commit>	Undo commits, unstage changes, keep working directory
- git reset --hard <commit>	Undo commits and discard all changes
- git revert <commit>	Create a new commit that reverses a previous commit
- git log --oneline	View commit history concisely


---
Conclusion

Understanding Git’s undo commands is essential for safe and efficient version control.

- Use git restore for working directory changes.
- Use git restore --staged to unstage files without losing work.
- Use git reset carefully to move HEAD and manage commits (soft/mixed/hard).
- Use git revert to safely undo commits in public branches.
- Always check git log --oneline before undoing to avoid losing important work.

By mastering these commands, you can confidently fix mistakes, manage staged changes, and maintain a clean Git history.
