---
name: git-commit
description: >-
  How to commit changes in this repo. Always squash all history into a single
  orphan commit — no prior git history should exist. Use when committing any
  change in the cicd repo.
---

# Git Commit for cicd Repo

This repo is kept as a **single-commit history** at all times. Every commit
replaces the entire history with one fresh orphan commit.

## Steps

1. Create an orphan branch off the current branch:
   ```bash
   git checkout --orphan fresh
   ```

2. Stage everything:
   ```bash
   git add -A
   ```

3. Commit with a meaningful message:
   ```bash
   git commit -m "<your message>"
   ```

4. Delete the old `main` branch and rename `fresh` to `main`:
   ```bash
   git branch -D main
   git branch -m main
   ```

5. Force-push to remote:
   ```bash
   git push --force origin main
   ```

> **Result:** `git log --oneline` shows exactly one commit. No old history.
