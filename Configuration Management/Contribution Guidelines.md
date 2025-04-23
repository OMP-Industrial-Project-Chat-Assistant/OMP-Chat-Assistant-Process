# Introduction

**Version:** 1.1

**Last Edit:** 16.04.2025

**Last Editor:** Yaroslav Kim

**Owner:** Yaroslav Kim

**Approval Status:** N/A

**Type:** Process

**Description:** This document describes how to contribute to the project.

**Dependencies:**
- [Business Context](<../Context and Requirements Management/EN/Context/Business Context.md>)
- [Software Product Requirements](<../Context and Requirements Management/EN/Requirements/Software Product Requirements.md>) 

# Justifications
- The project requires consistent rules on contribution and changes. This is necessary to maintain [Maintainability](<../Context and Requirements Management/EN/Requirements/Software Product Requirements.md#22-maintainability>) requirement.
- [Innopolis University](<../Context and Requirements Management/EN/Context/Business Context.md>) requires a certain level of [analyzability](<../Context and Requirements Management/EN/Requirements/Software Product Requirements.md#22-maintainability>) of the process.

# Content
## Contribution Guidelines

This document outlines the process for contributing to [OMP Chat Assistant repository](https://github.com/OMP-Industrial-Project-Chat-Assistant/OMP-Chat-Assistant), including issue creation, branch naming conventions, pull request workflows, and time tracking. Follow these guidelines to ensure consistency and efficiency in collaborative development.

All developers are strongly recommended to use **GitHub Desktop**.

---

### Table of Contents
1. [Issue Guidelines](#issue-guidelines)
2. [Branch Naming Convention](#branch-naming-convention)
3. [Assigning Branches to Issues](#assigning-branches-to-issues)
4. [Creating Pull Requests](#creating-pull-requests)
5. [Merging and Cleanup](#merging-and-cleanup)
6. [Best Practices](#best-practices)
7. [Pull Request Template](#pull-request-template)
8. [Example Workflow](#example-workflow)

---

### Issue Guidelines <a name="issue-guidelines"></a>

#### Issue Template
All issues include **predicted work hours**, **actual time spent** (tracked via Clockify), and **self-reported completion status** in the github sidebar. Use this template when creating issues:

````markdown
#### **Description**  
- **What**: Explain the problem or feature.  
- **Why**: Business/user impact (e.g., "Users receive duplicate messages, causing confusion").  
- **Reproduction Steps** (for bugs):  
  1. Step 1  
  2. Step 2  

#### **Acceptance Criteria**  
- [ ] Criteria 1 (e.g., "Messages must render uniquely in the UI")  
- [ ] Criteria 2  

#### **Additional Notes** 
- **Linked Resources**: Attach designs, API docs, or related PRs.  
````

#### Rules
1. **Estimating Work**  
   - Break tasks into sub-tasks if predicted work exceeds **12 hours**.  
   - Update estimates if scope changes (add a comment explaining changes).  
2. **Time Tracking**  
   - Log time in Clockify **regularly** under the correct project and tag.  
   - After resolving the issue, update `Actual Work` in the issue. 
3. **Closing Issues**  
   - Only close after:  
     - All acceptance criteria are met.  
     - The PR is merged into the release branch.  
     - `Actual Work` is filled in.  

---

### Branch Naming Convention <a name="branch-naming-convention"></a>

#### Format  
Non-release branches must follow this naming structure:  
`<type>/chat-<issue-number>/<short-description>`  

- **`<type>`**: Either `feature` (for new functionality), `bug` (for bug fixes), or `task` (for other issues, such as documentation)
- **`chat-<issue-number>`**: The GitHub issue number prefixed with `chat-` (e.g., `chat-42`).  
- **`<short-description>`**: A brief, hyphen-separated description of the task (e.g., `add-message-timestamp`).  

Release branches must follow this naming structure:  
`release/<version>`

Documentation release branches have same versioning as the project.

Process repository does not have release branches - the `master` branch is considered the most up-to-date.
#### Examples  
- `feature/chat-45/add-file-upload`  
- `bug/chat-12/fix-message-duplication`  
- `release/1.0`

#### Rules  
- Use lowercase letters and hyphens (no spaces or underscores).  
- Keep descriptions concise (3–5 words).  

---

### Assigning Branches to Issues <a name="assigning-branches-to-issues"></a>

1. **Link Branches to Issues**  
   - Add a comment to the issue with a link to the branch (e.g., `Working on this in [branch-name]`).  
   - Add the branch in the **Development** category of the sidebar on the right of the issue preview.  

---

### Creating Pull Requests <a name="creating-pull-requests"></a>

#### Timing  
- **Before the wrap-up meeting**: Create a PR targeting the **latest release branch** (e.g., `release/1.2.0`).  
- Ensure PRs are created early enough for review and discussion.  

#### Steps  
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

### Merging and Cleanup <a name="merging-and-cleanup"></a>

#### After Approval  
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

### Best Practices <a name="best-practices"></a>

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

### Pull Request Template <a name="pull-request-template"></a>

```markdown  
#### Data  
Predicted work hours: <put prediction based on planning poker>  
Actual work hours: <add amount of hours spent on issue after completion>  

#### Description  
<!-- Explain the purpose of this PR and link to the issue (e.g., Fix #45). -->  

#### Changes  
- Change 1  
- Change 2  

#### Testing Steps  
1. Step 1 to test  
2. Step 2 to test  

#### Screenshots/GIFs (if applicable)  

#### Checklist  
- [ ] Tests added/updated  
- [ ] Documentation updated  
- [ ] Code linted  
- [ ] Reviewed by at least 1 team member  
```  

---

### Example Workflow <a name="example-workflow"></a>

1. **Start Tracking Time**  
   - Before any action, start tracking time in Clockify under the `OMP Chat Assistant` project with the issue tag (e.g., `#45`).  
   - Stop tracking when you pause work.  
2. **Create a Branch**  
   ```bash  
   git checkout -b feature/chat-45/add-message-reactions  
   ```  
3. **Work on Changes**  
   Commit and push:  
   ```bash  
   git add .  
   git commit -m "Add emoji reactions to messages"  
   git push origin feature/chat-45/add-message-reactions  
   ```  
4. **Create a PR**  
   - Target: `release/[latest-version]`  
   - Description: "Fixes #45: User can now use feature 1 and feature 2."  
5. **Review and Merge**  
   - Address feedback, then merge into `release/[latest-version]`.  
6. **Cleanup**  
   - Delete the branch locally and remotely.  
   - Update the issue’s `Actual Work` field with time logged in Clockify.  

# Changelog
- v1.0 - 13.04.2025. Conversion to current format of documents. Yaroslav Kim
- v1.1 - 16.04.2025. Link fixes. Yaroslav Kim