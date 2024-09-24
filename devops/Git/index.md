# Git

## Introduction
Git is a distributed version control system designed to handle everything from small to very large projects with speed and efficiency. It allows multiple developers to work on a project simultaneously without interfering with each other's work.

## Basic Syntax
```bash
# Initialize a new Git repository
git init

# Clone an existing repository
git clone https://github.com/user/repo.git

# Add files to the staging area
git add .

# Commit changes
git commit -m "Initial commit"

# Push changes to a remote repository
git push origin main
```

## Common Use Cases
- Version control for source code
- Collaboration among multiple developers
- Tracking changes and history
- Branching and merging

## Advanced Features
- **Branching**: Create and manage branches for feature development and bug fixes.
- **Rebasing**: Reapply commits on top of another base tip.
- **Stashing**: Save changes temporarily without committing.
- **Submodules**: Include other Git repositories within a repository.

## Code Snippets
### Branching
```bash
# Create a new branch
git branch feature-branch

# Switch to the new branch
git checkout feature-branch

# Create and switch to a new branch
git checkout -b feature-branch
```

### Rebasing
```bash
# Rebase the current branch onto another branch
git rebase main

# Continue a rebase after resolving conflicts
git rebase --continue

# Abort a rebase
git rebase --abort
```

### Stashing
```bash
# Stash changes
git stash

# List stashes
git stash list

# Apply the most recent stash
git stash apply

# Apply and drop the most recent stash
git stash pop
```

### Submodules
```bash
# Add a submodule
git submodule add https://github.com/user/repo.git path/to/submodule

# Initialize and update submodules
git submodule update --init --recursive

# Remove a submodule
git submodule deinit -f path/to/submodule
rm -rf .git/modules/path/to/submodule
git rm -f path/to/submodule
```

## Tips & Best Practices
- **Commit Often**: Make small, frequent commits with clear messages.
- **Branching Strategy**: Use a branching strategy like Git Flow or GitHub Flow.
- **Code Reviews**: Use pull requests for code reviews and collaboration.
- **Backup**: Regularly push changes to a remote repository to avoid data loss.
- **Documentation**: Document your Git workflow and conventions for your team.

## External Resources
- [Git Official Documentation](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)
- [GitHub Learning Lab](https://lab.github.com/)