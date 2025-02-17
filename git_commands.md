# Git & GitHub Ultimate Cheat Sheet

## 1. Basic Setup
```sh
git config --global user.name "Your Name"  # Set username
git config --global user.email "your.email@example.com"  # Set email
git config --list  # View Git configurations
```

## 2. Repositories

### Initializing & Cloning
```sh
git init  # Initialize a new repository
git clone <repo-url>  # Clone an existing repository
```

### Remote Repositories
```sh
git remote add origin <url>  # Link to a remote repository
git remote -v  # View remote URLs
git remote set-url origin <new-url>  # Update remote URL
git push -u origin <branch-name>  # Push changes to a remote repository
git pull origin <branch-name>  # Pull changes from a remote branch
git fetch  # Download updates from remote without merging
```

## 3. Working with Changes

### Tracking Changes
```sh
git status  # View working directory status
git diff  # Compare working directory changes
git diff <branch1> <branch2>  # Compare two branches
```

### Staging & Committing
```sh
git add <file>  # Stage a file
git add .  # Stage all changes
git commit -m "Message"  # Commit changes
git commit -am "Message"  # Stage & commit tracked files
git commit --amend  # Edit last commit
```

### Undoing Changes
```sh
git reset <file>  # Unstage a file
git reset --soft HEAD~1  # Undo last commit but keep changes staged
git reset --mixed HEAD~1  # Undo last commit, keep changes unstaged
git reset --hard HEAD~1  # Completely remove last commit
git revert <commit-id>  # Create a new commit that undoes a specific commit
```

### Stashing Changes
```sh
git stash  # Temporarily save changes
git stash list  # View stashed changes
git stash pop  # Apply & remove stashed changes
git stash apply  # Apply stashed changes without removing
git stash clear  # Remove all stashed entries
```

## 4. Branching & Merging

### Managing Branches
```sh
git branch  # List local branches
git branch -r  # List remote branches
git branch -a  # List all branches (local & remote)
git branch <branch-name>  # Create a new branch
git checkout <branch-name>  # Switch to a branch
git checkout -b <branch-name>  # Create and switch to a branch
git branch -d <branch-name>  # Delete a branch (-D to force delete)
```

### Merging & Rebasing
```sh
git merge <branch-name>  # Merge a branch into the current branch
git merge --no-edit <branch-name>  # Merge without opening a commit message editor
git rebase <branch-name>  # Reapply commits on another base branch
git rebase -i HEAD~<n>  # Interactive rebase to edit commit history
```

### Handling Merge Conflicts
```sh
git mergetool --tool=vimdiff  # Use an editor to resolve merge conflicts
git diff  # Compare changes in files
git show <commit-id>  # Show details of a specific commit
```

## 5. Collaboration & Pull Requests

### Working with Remote Repositories
```sh
git push origin :<branch-name>  # Delete a remote branch
git pull origin <branch-name>  # Pull latest changes
git fetch  # Fetch updates from remote
```

### Creating a Pull Request (PR)
1. Push changes to a new branch:
   ```sh
   git push origin <branch-name>
   ```
2. Go to your GitHub repository.
3. Click **"New Pull Request"**, select your branch, and create the PR.

## 6. Viewing & Managing History

### Checking Logs & History
```sh
git log  # View commit history
git log --oneline  # Concise commit history
git reflog  # View all reference changes (including resets & checkouts)
```

### Inspecting Changes
```sh
git show <commit-id>  # Show details of a specific commit
git blame <file>  # Show who last modified each line of a file
git grep "search-term"  # Search for a term in the repository
```

## 7. Advanced Git Features

### Cherry-Picking Commits
```sh
git cherry-pick <commit-id>  # Apply a specific commit from another branch
git cherry-pick <start-commit-id>^..<end-commit-id>  # Cherry-pick a range of commits
```

### Working with Tags
```sh
git tag <tag-name>  # Add a tag to a commit
git tag -d <tag-name>  # Delete a tag
git tag -n  # View tags with descriptions
```

### Submodules & Worktrees
```sh
git submodule add <repo-url> <path>  # Add a submodule
git submodule init  # Initialize submodules
git submodule update  # Update submodules
git worktree add <path> <branch>  # Create a worktree
```

## 8. Cleaning Up & Maintenance
```sh
git clean -f  # Remove untracked files
git clean -fd  # Remove untracked files & directories
git gc --prune=now  # Optimize the repository
git fsck  # Check repository integrity
```

## 9. GitHub CLI Commands (Optional)
```sh
gh repo create  # Create a GitHub repository from the command line
gh repo clone <repo-url>  # Clone a GitHub repository
gh pr create  # Create a pull request
gh pr list  # List open PRs
gh issue create  # Create a GitHub issue
```

### GitHub API (Using cURL)
```sh
curl -H "Authorization: token YOUR_TOKEN" https://api.github.com/repos/USERNAME/REPO_NAME/issues
# List issues in a repository
```

# Best Practices & Common Workflows

✔ **Commit Often** – Frequent, clear commits maintain project history.  
✔ **Branch for Features** – Keep changes organized.  
✔ **Use Meaningful Messages** – Explain changes clearly.  
✔ **Pull Regularly** – Stay updated & avoid conflicts.  
✔ **Resolve Conflicts Quickly** – Avoid integration delays.  
✔ **Review PRs Thoroughly** – Maintain code quality.  
✔ **Tag Releases** – Mark milestones for easy reference.  
✔ **Clean Up Branches** – Delete unnecessary branches.  
✔ **Use Git Hooks** – Automate tasks for consistency.  
✔ **Squash Commits Before Merging** – Keep history clean.  
✔ **Avoid Large Commits** – Keep changes small & focused.  
✔ **Use Descriptive Branch Names** – e.g., `feature/login-page`.  
✔ **Keep Main Branch Deployable** – Always ensure stability.


