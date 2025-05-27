# 🚀 GitHub Pages Setup Guide

## Step 1: Create GitHub Repository

1. **Go to GitHub.com** and sign in to your account
2. **Click "New Repository"** (green button)
3. **Repository Settings:**
   - Repository name: `gtdlc-onboarding-guide`
   - Description: `Gapteq DLC Management Platform User Onboarding Guide`
   - Set to **Public** (required for free GitHub Pages)
   - Check "Add a README file"
4. **Click "Create Repository"**

## Step 2: Upload Your Documentation

1. **Clone the repository locally:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/gtdlc-onboarding-guide.git
   cd gtdlc-onboarding-guide
   ```

2. **Copy your files:**
   - Copy `USER_ONBOARDING.md` to the repository folder
   - Copy the entire `images/` folder to the repository
   - Rename `USER_ONBOARDING.md` to `README.md` (this will be the main page)

3. **Commit and push:**
   ```bash
   git add .
   git commit -m "Add onboarding documentation and images"
   git push origin main
   ```

## Step 3: Enable GitHub Pages

1. **Go to your repository on GitHub**
2. **Click "Settings" tab**
3. **Scroll down to "Pages" section**
4. **Under "Source":**
   - Select "Deploy from a branch"
   - Choose "main" branch
   - Choose "/ (root)" folder
5. **Click "Save"**

## Step 4: Access Your Public Documentation

- Your documentation will be available at:
  `https://YOUR_USERNAME.github.io/gtdlc-onboarding-guide/`
- GitHub will automatically render the README.md file
- All images will work with relative paths

## Step 5: Easy Updates Process

1. **Make changes locally** to your markdown files
2. **Commit and push:**
   ```bash
   git add .
   git commit -m "Update onboarding guide"
   git push origin main
   ```
3. **Changes go live automatically** within 1-2 minutes

## Benefits:
- ✅ **Free hosting**
- ✅ **Automatic updates** when you push changes
- ✅ **Version control** for all changes
- ✅ **Professional URL**
- ✅ **Mobile-friendly** rendering
- ✅ **Search engine indexable** 