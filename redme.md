# Git Guide  
A comprehensive guide on how to use Git effectively.

---

## 1. Configure Git with User Details  
Set up your Git user details globally:  
```bash
git config --global user.name "your_user_name"
git config --global user.email "your_email"
```


### Verify your configuration:  
```bash
git config --global --list
```

---

## 2. Initialize a Git Repository  
Used to start tracking files in a new or existing project folder:  
```bash
git init
```

---

## 3. Check the Status of Your Changes  
```bash
git status
```

---

## 4. Stage Files for Commit  
### Stage a single file:  
```bash
git add file_name
```
### Stage all files:  
```bash
git add .
```

---

## 5. Commit Changes with a Message  
### Commit message best practices:  
- Use **imperative mood** (like giving a command).  
- A commit should complete the sentence:  
  _"If applied, this commit will **[describe change]**."_  
- ✅ **Examples:**  
  - `git commit -m "Add login page"`  
  - `git commit -m "Fix bug in authentication"`  
  - `git commit -m "Refactor user service"`  
  - `git commit -m "Initial commit: Added project setup files"`  

```bash
git commit -m "Add login page"
```

---

## 6. Push Changes to a Remote Repository  
### Add a remote repository:  
```bash
git remote add origin https://github.com/username/repository.git
```
### Push your code to the remote repository:  
```bash
git push -u origin main
```
(*Replace `main` with `master` if your repo uses `master` as the default branch.*)

---

## 7. Pull Changes from Remote Repository  
Fetch and merge updates from the remote repository:  
```bash
git pull origin main
```

---

## 8. View Commit History  
### Show all commit logs:  
```bash
git log
```
### Show a compact one-line history:  
```bash
git log --oneline
```
### Show detailed commit history with diffs:  
```bash
git log -p
```
### Show the latest commit:  
```bash
git log -1
```

---

## 9. Branching in Git  
### Create a new branch:  
```bash
git branch feature-branch
```
### List all branches:  
```bash
git branch
```
### Delete a branch:  
```bash
git branch -d feature-branch
```
(*Use `-D` instead of `-d` to force delete.*)

---

## 10. Switching Between Branches  
```bash
git checkout feature-branch  # Older method
```
or  
```bash
git switch feature-branch  # Recommended method
```
### Switch back to the main branch:  
```bash
git checkout main
```
or  
```bash
git switch main
```

---

## 11. Merging Branches  
### Merge a branch into the current branch:  
```bash
git merge feature-branch
```
### Abort a merge (if something goes wrong):  
```bash
git merge --abort
```

---

## 12. Resolving Merge Conflicts  
If a conflict occurs, Git will display:  
```
CONFLICT (content): Merge conflict in file.txt
```
### Steps to resolve:  
1. Open the conflicting file and manually fix the conflict.  
2. Stage the resolved file:  
   ```bash
   git add file.txt
   ```
3. Commit the resolved changes:  
   ```bash
   git commit -m "Resolved merge conflict in file.txt"
   ```

---

## 13. Stashing Changes (Temporary Storage)  
### Save uncommitted changes:  
```bash
git stash
```
### Apply the latest stashed changes:  
```bash
git stash pop
```
### View stashed changes:  
```bash
git stash list
```
### Drop a stash:  
```bash
git stash drop
```

---

## 14. Resetting Commits  
### Soft reset (keeps changes staged):  
```bash
git reset --soft HEAD~1
```
### Mixed reset (keeps changes but unstages them):  
```bash
git reset --mixed HEAD~1
```
### Hard reset (removes all changes permanently):  
```bash
git reset --hard HEAD~1
```
🚨 **Warning:** A hard reset deletes all uncommitted changes.

---

## 15. Reverting a Commit  
To undo a commit without losing history:  
```bash
git revert commit_id
```

---

## 16. Removing Files from Git Tracking  
### Remove a file but keep it in the working directory:  
```bash
git rm --cached file_name
```
### Remove a file from Git and the working directory:  
```bash
git rm file_name
```

---

## 17. Cloning a Remote Repository  
To clone a repository from GitHub/GitLab:  
```bash
git clone https://github.com/username/repository.git
```

---

## 18. Viewing Remote Repositories  
### Show the linked remote repositories:  
```bash
git remote -v
```
### Change the remote repository URL:  
```bash
git remote set-url origin https://github.com/username/new-repository.git
```

---

## 19. Git Aliases (Shortcuts)  
To create custom Git shortcuts:  
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.cm "commit -m"
```
Now you can use:  
```bash
git st  # Instead of git status
git co main  # Instead of git checkout main
git cm "message"  # Instead of git commit -m "message"
```

---

## 20. Undoing Local Changes  
### Undo changes to a modified file (before staging):  
```bash
git checkout -- file_name
```
### Unstage a staged file (before commit):  
```bash
git reset file_name
```

---

## 21. Checking Differences in Files  
### Compare working directory changes with the last commit:  
```bash
git diff
```
### Compare staged changes with the last commit:  
```bash
git diff --staged
```
### Compare two commits:  
```bash
git diff commit1 commit2
```

---

## 22. Working with Tags  
### Create a new tag:  
```bash
git tag v1.0.0
```
### Push a tag to the remote repository:  
```bash
git push origin v1.0.0
```
### List all tags:  
```bash
git tag
```

---

## 23. Deleting Commits, Branches, and Tags  
### Delete a commit (by resetting or reverting):  
```bash
git reset --hard commit_id  # Removes commit permanently
git revert commit_id  # Undoes the commit but keeps history
```
### Delete a branch:  
```bash
git branch -d branch_name
```
### Delete a remote branch:  
```bash
git push origin --delete branch_name
```
### Delete a tag:  
```bash
git tag -d v1.0.0
```

---

This guide covers all essential Git commands. 🚀 Happy coding!  
