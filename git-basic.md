# Git Basics for Software Projects

## Introduction
Git is a distributed version control system that helps teams collaborate on software projects. This guide covers the essential Git commands and workflows you'll need for your daily development tasks.

## Getting Started

### Initial Setup
1. Install Git from [git-scm.com](https://git-scm.com/)
2. Configure your identity:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Basic Concepts
- **Repository**: A directory where Git tracks changes to your project
- **Commit**: A snapshot of your project at a specific point in time
- **Branch**: A separate line of development
- **Remote**: A copy of your repository hosted on a server (e.g., GitHub, GitLab)

## Common Git Commands

### Starting a New Project
```bash
# Initialize a new Git repository
git init

# Create a .gitignore file
touch .gitignore  # On Unix/Linux/MacOS
# OR
echo "" > .gitignore  # On Windows
```

Common entries in .gitignore:
```
# Dependencies
node_modules/
vendor/

# Build outputs
dist/
build/
*.exe
*.dll
*.so
*.dylib

# IDE and editor files
.idea/
.vscode/
*.swp
*.swo
.DS_Store

# Environment files
.env
.env.local
.env.*.local

# Log files
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Testing
coverage/
.nyc_output/

# Temporary files
*.tmp
*.temp
```

### Cloning an Existing Project
```bash
# Clone an existing repository
git clone <repository-url>
```

### Making Changes
```bash
# Check repository status
git status

# Add files to staging area
git add <file-name>
git add .  # Add all changes

# Commit changes
git commit -m "Your commit message"

# View commit history
git log
```

### Working with Branches
```bash
# List all branches
git branch

# Create a new branch
git branch <branch-name>

# Switch to a branch
git checkout <branch-name>

# Create and switch to a new branch
git checkout -b <branch-name>

# Merge branches
git merge <branch-name>
```

### Remote Repository Operations
```bash
# Add a remote repository
git remote add origin <repository-url>

# Push changes to remote
git push origin <branch-name>

# Pull changes from remote
git pull origin <branch-name>

# Fetch updates without merging
git fetch
```

## Best Practices

### Commit Messages
- Write clear, descriptive commit messages
- Use present tense ("Add feature" not "Added feature")
- Keep messages concise but informative

### Branching Strategy
1. **main/master**: Production-ready code
2. **develop**: Development branch
3. **feature/**: New features
4. **bugfix/**: Bug fixes
5. **hotfix/**: Urgent production fixes

### Workflow Example
1. Create a feature branch:
```bash
git checkout -b feature/new-feature
```

2. Make changes and commit:
```bash
git add .
git commit -m "Add new feature"
```
3. Push to remote:
```bash
git push origin feature/new-feature
```

4. Create a pull request on GitHub/GitLab

## Common Scenarios

### Undoing Changes
```bash
# Discard changes in working directory
git checkout -- <file-name>

# Undo last commit (keeping changes)
git reset --soft HEAD~1

# Undo last commit (discarding changes)
git reset --hard HEAD~1
```
### Stashing Changes
```bash
# Save changes temporarily
git stash

# List stashed changes
git stash list

# Apply most recent stash
git stash pop

# Apply specific stash
git stash apply stash@{n}
```

## Tips and Tricks

1. **Always pull before pushing** to avoid conflicts
2. **Use .gitignore** to exclude unnecessary files
3. **Commit often** with meaningful messages
4. **Review changes** before committing using `git diff`
5. **Keep branches updated** with the main branch

## Troubleshooting

### Common Issues
1. **Merge conflicts**: Resolve conflicts in your code editor
2. **Detached HEAD**: Use `git checkout main` to return to main branch
3. **Lost commits**: Use `git reflog` to find and recover lost commits

## Additional Resources
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)


