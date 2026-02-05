---
name: reviewable-commits
description: Use only when asked to restructure Git commits to be easily reviewable by humans
---

# Reviewable Commits

## Overview

Restructure Git commit history on the current branch to make this branch easily
reviewable by humans, one commit at a time.

**Announce at start:** "I'm using the reviewable-commits skill."

## The Process

### Step 1: Safety Checks

**Step 1.1: Check for uncommitted changes**

First check whether there are any uncommitted changes on the current branch.

```bash
# Check for uncommitted, unstaged changes.
git diff --stat
# Check for uncommitted staged changes.
git diff --staged --stat
```

If there are **ANY** uncommitted changes. Stop immediately and say: "I can't
apply this skill when there are uncommitted changes on the current branch."

**Step 1.2: Check which branch we're on**

```bash
# Get the current branch name, store it in BRANCH_NAME.
BRANCH_NAME=$(git rev-parse --abbrev-ref HEAD)
```

If we are on `main`/`master`, stop immediately and say: "I can't apply this
skill to the default branch."

### Step 2: Make a backup of the current branch

```bash
# Try to create a backup branch.
BACKUP_BRANCH_NAME=backup-${BRANCH_NAME}
git checkout -b ${BACKUP_BRANCH_NAME}
```

If this fails, stop immediately and say: "The backup branch already exists."

### Step 3: Switch back to the branch

```bash
# Switch back to our original branch.
git checkout ${BRANCH_NAME}
```

### Step 4: Inspect the current branch's commit history

```bash
# Inspect the Git commits on the current branch relative to its most logical
# parent (usually `main`).
git log main..HEAD
```

If there are any merge commits, stop immediately and say: "I can't restructure
branches with merge commits."

**Only if there are NO merge commits, continue.**

### Step 5: Inspect the code changes and devise a plan

Inspect the code changes in the branch's history relative to its parent.
Develop a plan to restructure the Git commits such that each commit is easily
reviewable by a human reviewer.

**Core principles:**

- Each commit should ideally only change one logical thing
- Good commits are usually at most 200-300 lines of code (excluding auto-generated code)
- Subsequent commits should never change the contents of earlier commits
- Commit messages should be short and meaningful
- **Always use Conventional Commits**

Show the plan to your human partner before continuing and ask whether to
continue, or whether changes are needed.

**DO NOT CHANGE ANY COMMITS UNTIL THE HUMAN HAS APPROVED.**

### Step 6: Execute if approved

If the human has approved of the plan to restructure the current branch's Git
commit history, execute on it.

**Stop here** and ask the human to review the commit history. If it looks good,
ask: "Should I delete the backup branch?" (yes/no)

### Step 7: Delete the backup branch if approved

If the human approved deleting the backup branch (from step 6), delete it.

```bash
# Delete the backup branch we created.
git branch -D ${BACKUP_BRANCH_NAME}
```
