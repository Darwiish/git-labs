# About Page Git Workflow

This document explains the workflow for adding the `about.md` page using Git.

---

## Feature Branch Workflow

```text
         Start on main
               |
               v
   git checkout -b feature/add-about-page
               |
               v
        Create about.md
               |
               v
          git add about.md
               |
               v
       git commit -m "Add about page"
               |
               v
git push --set-upstream origin feature/add-about-page
               |
               v
         Create Pull Request
               |
               v
          Merge into main
               |
               v
        Delete feature branch
