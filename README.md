### Git Playbook

Git is a powerful version control system used to track changes in code and collaborate with others. This playbook covers essential Git commands and workflows, including branching, merging, resolving conflicts, and handling pull requests.

---

### **1. Setting up a Repository**
Before working on any project, you need to initialize a Git repository or clone an existing one.

- **Initialize a new Git repository**:
  ```bash
  git init
  ```
  This creates a new `.git` directory and sets up the repository for version control.

- **Clone an existing repository**:
  ```bash
  git clone <repository_url>
  ```
  This copies an existing repository to your local machine.

---

### **2. Basic Commands**

#### **Stage and Commit Changes**
- **Check the status** of the current repository:
  ```bash
  git status
  ```
  Shows which files have changed, staged, or are untracked.

- **Stage a file** (add it to the commit):
  ```bash
  git add <file_name>
  ```
  To stage all files:
  ```bash
  git add .
  ```

- **Commit the changes**:
  ```bash
  git commit -m "commit message"
  ```
  A commit records changes to the repository with a message describing what was done.

#### **View History**
- **See commit history**:
  ```bash
  git log
  ```
  Displays a history of commits with details like author, date, and commit hash.

#### **Undo Changes**
- **Unstage a file**:
  ```bash
  git reset <file_name>
  ```
  This unstages a file, removing it from the staging area.

- **Discard local changes** (restore the file to its previous state):
  ```bash
  git checkout -- <file_name>
  ```

---

### **3. Branching**

Git branches allow you to work on different features or fixes without affecting the main codebase.

- **Create a new branch**:
  ```bash
  git branch <branch_name>
  ```

- **Switch to a branch**:
  ```bash
  git checkout <branch_name>
  ```
  Or use:
  ```bash
  git switch <branch_name>
  ```

- **Create and switch to a branch**:
  ```bash
  git checkout -b <branch_name>
  ```

- **List all branches**:
  ```bash
  git branch
  ```

---

### **4. Merging Branches**

Once you’ve completed work on a branch, you can merge it into another branch (e.g., `main` or `develop`).

- **Merge a branch** into the current branch:
  ```bash
  git checkout <target_branch>
  git merge <source_branch>
  ```

  Example: If you want to merge the feature branch into the main branch:
  ```bash
  git checkout main
  git merge feature-branch
  ```

---

### **5. Fixing Merge Conflicts**

Merge conflicts occur when two branches modify the same part of a file. To fix them:

1. **After merging** and encountering conflicts, Git will pause the merge and show conflict markers (`<<<<<<`).
2. **Open the conflicted file**, locate the conflict, and edit the file to resolve the conflict.
3. **After fixing the conflict**, stage the changes:
   ```bash
   git add <file_name>
   ```
4. **Complete the merge**:
   ```bash
   git commit
   ```

To abort a merge if you can’t resolve the conflict:
```bash
git merge --abort
```

---

### **6. Pulling and Pushing Changes**

To sync your local repository with the remote repository:

- **Pull changes from the remote repository**:
  ```bash
  git pull origin <branch_name>
  ```
  Fetches the changes from the remote branch and merges them into your local branch.

- **Push changes to the remote repository**:
  ```bash
  git push origin <branch_name>
  ```
  Uploads your commits to the remote repository.

---

### **7. Pull Requests (PR)**

A **Pull Request (PR)** is a way to propose changes to the codebase in GitHub, GitLab, or similar Git-based platforms. It’s used for code reviews and collaboration before merging changes into the main branch.

#### **Workflow for Pull Requests:**

1. **Create a new branch** for your feature or bug fix.
   ```bash
   git checkout -b feature/my-feature
   ```

2. **Make changes** and commit them to the branch.
   ```bash
   git add .
   git commit -m "Added my feature"
   ```

3. **Push the branch** to the remote repository.
   ```bash
   git push origin feature/my-feature
   ```

4. **Open a Pull Request** in the GitHub or GitLab interface:
   - Go to your repository in the browser.
   - Select the branch you just pushed.
   - Click the "Open Pull Request" button.
   - Provide a meaningful description and link it to any relevant issues.

5. **Code Review**:
   - Your team will review the code.
   - Address feedback if necessary by making additional commits to the branch.

6. **Merge the PR**:
   - Once approved, the PR can be merged into the main branch.

---

### **8. Advanced Git Commands**

#### **Rebase**
Rebasing is an alternative to merging that creates a cleaner project history.

- **Rebase the current branch** onto another:
  ```bash
  git rebase <target_branch>
  ```

#### **Stashing**
Stash temporarily saves your uncommitted changes without committing them.

- **Save changes to stash**:
  ```bash
  git stash
  ```

- **Apply stashed changes**:
  ```bash
  git stash apply
  ```

#### **Cherry-pick**
Cherry-picking allows you to apply a specific commit from one branch into another.

- **Apply a specific commit**:
  ```bash
  git cherry-pick <commit_hash>
  ```

---

### **9. Best Practices**

- **Commit often** with clear, concise messages.
- **Pull frequently** to keep your branch up-to-date with changes from the remote repository.
- **Use descriptive branch names**, such as `feature/add-user-login` or `bugfix/fix-null-pointer`.
- **Keep branches small and focused** on a specific feature or issue to avoid complex merges.
- **Write meaningful commit messages** that explain the "why" behind the changes, not just the "what."
- **Review your changes** before committing to ensure quality and relevance.
- **Use tags** to mark release points in your project history for easier navigation.
- **Avoid committing sensitive information** such as passwords or API keys.
- **Regularly clean up stale branches** to maintain a tidy repository and avoid confusion.
- **Use Git hooks** to automate checks and tasks before commits or pushes.
- **Keep sensitive information out of version control** by using environment variables or secure vaults.
- **Document your Git workflow** in your project's README or contribution guidelines.
- **Use Git aliases** for frequently used commands to improve productivity.
- **Regularly backup your repository** to prevent data loss.
- **Write meaningful commit messages** that explain the "why" behind changes, not just the "what".
- **Use .gitignore files** to exclude unnecessary files from version control.
- **Regularly review and clean up old branches** to keep the repository tidy.
- **Utilize code reviews** to improve code quality and share knowledge within the team.
- **Tag important milestones** in your project's history for easy reference.

---

This playbook covers the essential Git workflows for managing your project efficiently.
