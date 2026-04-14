# Git Rebase vs Merge

When working with Git, both `rebase` and `merge` are used to integrate changes from one branch into another. However, they work differently and have distinct use cases.

## Git Rebase

Rebasing is the process of moving or combining a sequence of commits to a new base commit. It rewrites the commit history and creates a linear sequence of commits.

### Key Points:
- **Linear History**: Rebase creates a clean, linear history by applying your changes on top of the target branch.
- **Rewriting History**: Since it rewrites commit history, it should not be used on shared branches.
- **Conflict Resolution**: Conflicts may need to be resolved multiple times during the rebase process.

### Example:
```bash
git checkout feature-branch
git rebase main
```
This applies the commits from `feature-branch` on top of the `main` branch.

### Squash Commits
Squashing combines multiple commits into a single commit, making the history cleaner.

#### Example:
```bash
git rebase -i HEAD~3
```
This opens an interactive rebase for the last 3 commits. Change `pick` to `squash` for the commits you want to combine.

### Reword Commits
Rewording allows you to edit the commit message of a specific commit during an interactive rebase.

#### Example:
```bash
git rebase -i HEAD~3
```
In the interactive rebase, change `pick` to `reword` for the commit whose message you want to edit.

## Git Merge

Merging is the process of combining two branches into one. It preserves the history of both branches and creates a new merge commit.

### Key Points:
- **Preserves History**: Merge keeps the history of all commits intact, including the branch structure.
- **No History Rewriting**: Unlike rebase, merge does not rewrite commit history, making it safer for shared branches.
- **Single Conflict Resolution**: Conflicts, if any, are resolved once during the merge process.

### Example:
```bash
git checkout main
git merge feature-branch
```
This merges the `feature-branch` into the `main` branch, creating a new merge commit.

## When to Use
- **Rebase**: Use when you want a clean, linear history and are working on a private branch.
- **Merge**: Use when you want to preserve the complete history and are working on a shared branch.

  ## Practice screenshot <img width="1280" height="1024" alt="git1" src="https://github.com/user-attachments/assets/ffd49f17-62a9-4ba4-8498-d77fb749868c" />
  <img width="1280" height="1024" alt="git2" src="https://github.com/user-attachments/assets/8378641e-44ba-466b-8e63-7198d3bc0304" />
  <img width="1280" height="1024" alt="reword" src="https://github.com/user-attachments/assets/f47f6cd5-d716-45c7-9037-5aaec449996f" />
  <img width="1280" height="1024" alt="squash" src="https://github.com/user-attachments/assets/f271acb8-6040-454a-9ef2-9ce4441f7277" />
  <img width="1280" height="1024" alt="Screenshot from 2026-04-14 13-40-07" src="https://github.com/user-attachments/assets/b9b17d53-c5d2-4ecb-9d40-60ae697a9eb0" />
  <img width="1280" height="1024" alt="gitf" src="https://github.com/user-attachments/assets/447195b1-cd98-47b0-bd56-713985ae741c" />
  <img width="1280" height="1024" alt="pr3" src="https://github.com/user-attachments/assets/ff59f4c7-8da8-4ca2-ba6f-8043b924bc9f" />
  <img width="1280" height="1024" alt="pr2" src="https://github.com/user-attachments/assets/e48b3a6d-e3f8-4168-839d-f7597be5988a" />







  
