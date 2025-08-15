# 🚀 GitHub Setup Guide - Smart Expense Splitter

## 📋 Prerequisites

Before pushing to GitHub, ensure you have:
- **Git installed** on your system
- **GitHub account** created
- **Git configured** with your credentials

## 🔧 Configure Git (First Time Setup)

If you haven't configured Git before:

```bash
# Set your name and email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Verify configuration
git config --list
```

## 🏗️ Create GitHub Repository

### Option 1: Create via GitHub Website (Recommended)

1. **Go to GitHub**: Visit [github.com](https://github.com)
2. **Sign in** to your account
3. **Click "New"** or the "+" icon → "New repository"
4. **Repository Details**:
   - **Repository name**: `smart-expense-splitter`
   - **Description**: `A modern expense splitting application with professional UI`
   - **Visibility**: Choose Public or Private
   - **DO NOT** initialize with README, .gitignore, or license (we already have these)
5. **Click "Create repository"**

### Option 2: Create via GitHub CLI

```bash
# Install GitHub CLI first: https://cli.github.com/
gh repo create smart-expense-splitter --public --description "A modern expense splitting application with professional UI"
```

## 🔗 Connect Local Repository to GitHub

After creating the GitHub repository, you'll see instructions. Use these commands:

### Step 1: Add Remote Origin
```bash
# Replace 'yourusername' with your actual GitHub username
git remote add origin https://github.com/yourusername/smart-expense-splitter.git
```

### Step 2: Verify Remote
```bash
git remote -v
# Should show:
# origin  https://github.com/yourusername/smart-expense-splitter.git (fetch)
# origin  https://github.com/yourusername/smart-expense-splitter.git (push)
```

### Step 3: Push to GitHub
```bash
# Push main branch to GitHub
git branch -M main
git push -u origin main
```

## 🔐 Authentication Options

### Option 1: Personal Access Token (Recommended)

1. **Go to GitHub Settings**: Profile → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. **Generate new token**: Click "Generate new token (classic)"
3. **Configure token**:
   - **Note**: "Smart Expense Splitter"
   - **Expiration**: Choose appropriate duration
   - **Scopes**: Select `repo` (Full control of private repositories)
4. **Copy the token** (you won't see it again!)
5. **Use token as password** when Git prompts for credentials

### Option 2: SSH Key (Advanced)

```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your.email@example.com"

# Add to SSH agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Copy public key to clipboard
cat ~/.ssh/id_ed25519.pub
```

Then add the public key to GitHub: Settings → SSH and GPG keys → New SSH key

## 📤 Push Commands Reference

### Initial Push
```bash
git push -u origin main
```

### Subsequent Pushes
```bash
git add .
git commit -m "Your commit message"
git push
```

### Push with Tags
```bash
git tag v1.0.0
git push --tags
```

## 🏷️ Repository Settings

After pushing, configure your repository:

### 1. Repository Description
- Go to your repository on GitHub
- Click the gear icon next to "About"
- Add description: "A modern expense splitting application with professional UI"
- Add topics: `expense-tracker`, `react`, `spring-boot`, `tailwindcss`, `java`, `postgresql`

### 2. Enable GitHub Pages (Optional)
- Go to Settings → Pages
- Source: Deploy from a branch
- Branch: main / docs (if you want to host documentation)

### 3. Branch Protection (Recommended for teams)
- Go to Settings → Branches
- Add rule for `main` branch
- Enable "Require pull request reviews before merging"

## 📝 Repository Structure

Your repository will have this structure:
```
smart-expense-splitter/
├── 📁 frontend/          # React frontend
├── 📁 src/               # Spring Boot backend
├── 📁 .mvn/              # Maven wrapper
├── 📄 README.md          # Main documentation
├── 📄 FEATURES.md        # Feature documentation
├── 📄 INSTALLATION.md    # Installation guide
├── 📄 GITHUB_SETUP.md    # This file
├── 📄 pom.xml            # Maven configuration
├── 📄 .gitignore         # Git ignore rules
└── 📄 start-app.bat      # Quick start script
```

## 🔄 Workflow Commands

### Daily Development Workflow
```bash
# Check status
git status

# Add changes
git add .

# Commit changes
git commit -m "feat: add new feature"

# Push to GitHub
git push
```

### Commit Message Conventions
Use conventional commits for better organization:
- `feat:` - New features
- `fix:` - Bug fixes
- `docs:` - Documentation changes
- `style:` - Code style changes
- `refactor:` - Code refactoring
- `test:` - Adding tests
- `chore:` - Maintenance tasks

### Example Commit Messages
```bash
git commit -m "feat: add Gmail-style email invitations"
git commit -m "fix: resolve sidebar navigation issue"
git commit -m "docs: update installation guide"
git commit -m "style: improve responsive design"
```

## 🎯 Next Steps

After pushing to GitHub:

1. **Update README**: Add your GitHub repository URL
2. **Create Issues**: Track bugs and feature requests
3. **Set up CI/CD**: Consider GitHub Actions for automated testing
4. **Add Contributors**: Invite team members if working in a team
5. **Create Releases**: Tag stable versions

## 🆘 Troubleshooting

### Common Issues

#### Authentication Failed
```bash
# Use personal access token as password
# Or set up SSH keys
```

#### Remote Already Exists
```bash
git remote remove origin
git remote add origin https://github.com/yourusername/smart-expense-splitter.git
```

#### Push Rejected
```bash
# Pull latest changes first
git pull origin main --rebase
git push
```

---

**🎉 Congratulations! Your Smart Expense Splitter is now on GitHub!**

**Repository URL**: `https://github.com/yourusername/smart-expense-splitter`
