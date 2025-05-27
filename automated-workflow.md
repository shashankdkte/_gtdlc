# 🤖 Automated Update Workflow Setup

## Overview
Set up a system where you can update documentation with minimal effort and maximum automation.

## Recommended Workflow: GitHub + VS Code + GitHub Desktop

### Step 1: Initial Setup

1. **Install required tools:**
   - [GitHub Desktop](https://desktop.github.com/) - Visual Git interface
   - [VS Code](https://code.visualstudio.com/) - Markdown editor with preview
   - [Markdown All in One extension](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) for VS Code

2. **Set up repository** (using GitHub Pages method from Option 1)

### Step 2: Configure VS Code for Easy Editing

1. **Open your repository folder** in VS Code
2. **Install helpful extensions:**
   ```
   - Markdown All in One
   - Markdown Preview Enhanced
   - Auto-Open Markdown Preview
   - Paste Image (for easy image insertion)
   ```

3. **Configure VS Code settings** (File > Preferences > Settings):
   ```json
   {
     "markdown.preview.openMarkdownLinks": "inPreview",
     "markdown.preview.scrollPreviewWithEditor": true,
     "markdown.preview.scrollEditorWithPreview": true
   }
   ```

### Step 3: Streamlined Update Process

#### For Quick Text Updates:
1. **Open VS Code** to your repository folder
2. **Edit markdown files** with live preview (Ctrl+Shift+V)
3. **Save changes** (Ctrl+S)
4. **Open GitHub Desktop**
5. **Review changes** in the visual diff
6. **Write commit message** and click "Commit to main"
7. **Click "Push origin"** - changes go live in 1-2 minutes

#### For Image Updates:
1. **Drag new images** into the `images/` folder in VS Code
2. **Use Paste Image extension** to insert images directly into markdown
3. **Follow the same commit/push process**

### Step 4: Advanced Automation (Optional)

#### Auto-deploy Script
Create `update-docs.bat` (Windows) or `update-docs.sh` (Mac/Linux):

```bash
#!/bin/bash
# Quick documentation update script

echo "📝 Updating documentation..."

# Add all changes
git add .

# Prompt for commit message
echo "Enter commit message (or press Enter for default):"
read commit_message

if [ -z "$commit_message" ]; then
    commit_message="Update documentation $(date '+%Y-%m-%d %H:%M')"
fi

# Commit and push
git commit -m "$commit_message"
git push origin main

echo "✅ Documentation updated and deployed!"
echo "🌐 Live at: https://YOUR_USERNAME.github.io/gtdlc-onboarding-guide/"
```

#### VS Code Tasks (Optional)
Create `.vscode/tasks.json`:

```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Deploy Documentation",
            "type": "shell",
            "command": "git",
            "args": ["add", ".", "&&", "git", "commit", "-m", "Update docs", "&&", "git", "push"],
            "group": "build",
            "presentation": {
                "echo": true,
                "reveal": "always",
                "focus": false,
                "panel": "shared"
            }
        }
    ]
}
```

### Step 5: Mobile Updates (Advanced)

#### GitHub Mobile App:
- Edit files directly on GitHub.com mobile
- Changes deploy automatically
- Good for quick text fixes

#### GitHub Codespaces:
- Full VS Code in browser
- Edit from any device
- Automatic sync and deployment

## Daily Update Workflow Summary:

1. **📝 Edit** in VS Code with live preview
2. **👀 Review** changes in GitHub Desktop
3. **💾 Commit** with descriptive message
4. **🚀 Push** to deploy (1-2 minutes to live)
5. **✅ Verify** at your public URL

## Benefits:
- ✅ **Visual editing** with live preview
- ✅ **One-click deployment**
- ✅ **Version history** for all changes
- ✅ **Rollback capability**
- ✅ **Mobile editing** options
- ✅ **Automated backups** 