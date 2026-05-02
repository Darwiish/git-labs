# Git Key Commands


## ===== CORE WORKFLOW =====
git status                  # Check current state
git add .                   # Stage all changes
git commit -m "message"     # Commit changes
git push                    # Push to remote
git pull                    # Pull latest changes

# ===== BRANCHING =====
git branch                  # List branches
git branch <name>           # Create branch
git checkout -b <name>      # Create & switch (classic)
git switch -c <name>        # Create & switch (modern)

# ===== MERGING =====
git merge <branch>          # Merge into current branch

# ===== DEVOPS FLOW =====
git pull
git switch -c feature/my-feature
git add .
git commit -m "Add: feature"
git push -u origin feature/my-feature
git merge feature/my-feature

# ===== FLOW =====
Local → add → commit → push → Remote
  ↑                              ↓
  └──────────── pull ────────────┘

# ===== USEFUL =====
git log                     # Commit history
git diff                    # Show changes
git reset --soft HEAD~1     # Undo last commit (keep changes)
git checkout .              # Discard local changes
