# Git_for_devops_a_to_z
Commonly used Git commands by DevOps engineers in day-to-day operations

# Git Commands Guide for DevOps Engineers
---

# 1. Git Configuration

### Configure username & email

```bash
git config --global user.name "username"
git config --global user.email "email@company.com"
```

Example: Configure username and email from github

```bash
git config --global user.name "Rahul Sharma"
git config --global user.email "rahul@company.com"
```

### Check configuration

```bash
git config --list
```

---

#  2. Initialize & Clone Repository

### Initialize a new repository

```bash
git init
```

### Clone existing repository

Example: Cloning project from GitHub

```bash
git clone https://github.com/company/project.git
```

Example with branch:

```bash
git clone -b dev https://github.com/company/project.git
```

---

#  3. Check Repository Status

```bash
git status
```

Shows:

* Modified files
* Untracked files
* Staged files

---

#  4. Staging & Committing Changes

### Add single file

```bash
git add app.py
```

### Add all files

```bash
git add .
```

### Commit changes for all files

```bash
git commit -m "Fixed production bug in payment module"
```
### Commit changes for single file

```bash
git commit <filename> -m "Fixed production bug in payment module"
```

### Real DevOps Example

```bash
git add Dockerfile
git commit -m "Updated base image to node:18 for security patch"
```

---

#  5. Branch Management

### Create new branch

```bash
git branch feature-login
```

### Switch branch

```bash
git checkout feature-login
```

Or (recommended modern command):

```bash
git switch feature-login
```

### Create & switch branch

```bash
git checkout -b feature-ci-pipeline
```

### List branches

```bash
git branch
```

### Delete branch

```bash
git branch -d feature-login
```

---

#  6. Working with Remote Repositories

### Add remote

```bash
git remote add origin https://github.com/company/project.git
```

### View remotes

```bash
git remote -v
```
### Remove remotes

```bash
git remote remove origin
```

### Fetch changes from main

```bash
git pull origin main --rebase
```
### Push code to remote

```bash
git push origin main
```

### Push new branch

```bash
git push -u origin feature-ci-pipeline
```

### Pull latest changes

```bash
git pull origin main
```

---

#  7. Fetch vs Pull

### Fetch changes (without merging)

```bash
git fetch origin
```

### Merge manually

```bash
git merge origin/main
```

---

#  8. Merge Branches

### Merge feature into main

```bash
git checkout main
git merge feature-ci-pipeline
```

### Real DevOps Example

Merging CI configuration to production:

```bash
git checkout main
git merge release-v1.2
git push origin main
```

---

#  9. Rebase (Clean History)

```bash
git checkout feature-branch
git rebase main
```

### Interactive Rebase

```bash
git rebase -i HEAD~3
```

Used to:

* Squash commits
* Edit commit messages
* Clean history before PR

---

#  10. Resolve Merge Conflicts

When conflict occurs:

```bash
git status
```

Edit conflicted file manually.

Then:

```bash
git add .
git commit -m "Resolved merge conflict"
```

---

#  11. Git Logs & History

### View commit history

```bash
git log
```

### One-line log

```bash
git log --oneline
```

### Graph view (DevOps favorite)

```bash
git log --oneline --graph --all
```

---

#  12. Undo Changes

### Unstage file

```bash
git reset HEAD app.py
```

### Discard local changes

```bash
git checkout -- app.py
```

### Reset commit (keep changes)

```bash
git reset --soft HEAD~1
```

### Hard reset (dangerous)

```bash
git reset --hard HEAD~1
```
---

#  13. Git Diff

### Check file differences

```bash
git diff
```

### Diff between branches

```bash
git diff main feature-branch
```

---

#  14. Cherry Pick

Apply specific commit to another branch:

```bash
git cherry-pick <commit-id>
```

DevOps Example:
Applying hotfix commit to production branch.

---

#  15. Git Revert (Safe Undo)

```bash
git revert <commit-id>
```

Creates new commit that undoes changes.

---

#  16. Git Best Practices for DevOps Engineers

- Always pull before push
- Use feature branches
- Write meaningful commit messages
- Tag production releases
- Avoid force push on shared branches
- Use rebase for clean PR history
- Protect main branch in GitHub/GitLab

---

# Conclusion

Git is a critical tool for DevOps Engineers to manage:

* Infrastructure as Code (Terraform, Ansible)
* CI/CD pipelines
* Docker & Kubernetes manifests
* Application deployments
* Release versioning

Mastering these commands ensures smooth automation, collaboration, and production stability.

---
