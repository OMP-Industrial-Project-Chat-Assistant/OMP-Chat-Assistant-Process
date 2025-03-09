# Contribution Guidelines

This document outlines the process for contributing to [OMP Chat Assistant repository](https://github.com/OMP-Industrial-Project-Chat-Assistant/OMP-Chat-Assistant), including branch naming conventions, issue association, pull request (PR) workflows, and branch cleanup. 

Follow these guidelines to ensure consistency and efficiency in collaborative development.

All developers are strongly recommended to use Github Desktop

---

## Table of Contents
1. [Branch Naming Convention](#branch-naming-convention)
2. [Assigning Branches to Issues](#assigning-branches-to-issues)
3. [Creating Pull Requests](#creating-pull-requests)
4. [Merging and Cleanup](#merging-and-cleanup)
5. [Best Practices](#best-practices)
6. [Pull Request Template](#pull-request-template)
7. [Example Workflow](#example-workflow)

---

## Branch Naming Convention <a name="branch-naming-convention"></a>

### Format
Non-release branches must follow this naming structure:  
`<type>/chat-<issue-number>/<short-description>`

- **`<type>`**: Either `feature` (for new functionality) or `bug` (for bug fixes).
- **`chat-<issue-number>`**: The GitHub issue number prefixed with `chat-` (e.g., `chat-42`).
- **`<short-description>`**: A brief, hyphen-separated description of the task (e.g., `add-message-timestamp`).

Release branches must follow this naming structure:
`release/<version>`

### Examples
- `feature/chat-45/add-file-upload`
- `bug/chat-12/fix-message-duplication`
- `release/1.0`

### Rules
- Use lowercase letters and hyphens (no spaces or underscores).
- Keep descriptions concise (3–5 words).

---

## Assigning Branches to Issues <a name="assigning-branches-to-issues"></a>

1. **Link Branches to Issues**  
   - Add a comment to the issue with a link to the branch (e.g., `Working on this in [branch-name]`)
   - Add the branch in the Development category of sidebar on the right of the issue preview
---

## Creating Pull Requests <a name="creating-pull-requests"></a>

### Timing
- **Before the wrap-up meeting**: Create a PR targeting the **latest release branch** (e.g., `release/1.2.0`).  
- Ensure PRs are created early enough for review and discussion.

### Steps
1. **Push Changes**  
   Commit and push your branch to the remote repository.
2. **Create a PR**  
   - Base branch: Latest release branch (e.g., `release/1.2.0`).  
   - Compare branch: Your feature/bug branch.  
3. **PR Description**  
   - Use the [Pull Request Template](#pull-request-template) (see below).  
   - Include screenshots, testing steps, and a link to the issue.  
4. **Assign Reviewers**  
   Tag relevant team members for code review.  

---

## Merging and Cleanup <a name="merging-and-cleanup"></a>

### After Approval
1. **Merge into Release Branch**  
2. **Delete the Branch**  
   - Check the "Delete branch" option in GitHub after merging.  
   - Confirm deletion locally:  
     ```bash
     git branch -d <branch-name>
     git fetch --prune
     ```
3. **Close the Issue**  

---

## Best Practices <a name="best-practices"></a>

1. **Sync with Release Branch**  
   Regularly rebase your branch with the latest release branch to avoid conflicts:  
   ```bash
   git checkout release/[latest-version]
   git pull
   git checkout your-branch
   git rebase release/[latest-version]
   ```
2. **Small, Focused PRs**  
   Keep PRs small and limited to one feature/bug fix.  
3. **Test Locally**  
   Verify functionality and ensure no regressions before creating a PR.  

---

## Pull Request Template <a name="pull-request-template"></a>

```markdown
### Description
<!-- Explain the purpose of this PR and link to the issue (e.g., Fix #45). -->

### Changes
- Change 1
- Change 2

### Testing Steps
1. Step 1 to test
2. Step 2 to test

### Screenshots/GIFs (if applicable)

### Checklist
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] Code linted
- [ ] Reviewed by at least 1 team member
```

---

## Example Workflow <a name="example-workflow"></a>

1. **Create a Branch**  
   ```bash
   git checkout -b feature/chat-45/add-message-reactions
   ```
2. **Work on Changes**  
   Commit and push:  
   ```bash
   git add .
   git commit -m "Add emoji reactions to messages"
   git push origin feature/chat-45/add-message-reactions
   ```
3. **Create a PR**  
   - Target: `release/[latest-version]`  
   - Description: "Fixes #45: User can now use feature 1 and feature 2."  
4. **Review and Merge**  
   - Address feedback, then merge into `release/[latest-version]`.  
5. **Cleanup**  
   Delete the branch locally and remotely.

---
