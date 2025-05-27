# 🦊 GitLab Pages Setup Guide

## Step 1: Create GitLab Repository

1. **Go to GitLab.com** and sign in
2. **Click "New Project"**
3. **Choose "Create blank project"**
4. **Project Settings:**
   - Project name: `gtdlc-onboarding-guide`
   - Project description: `Gapteq DLC Management Platform User Onboarding Guide`
   - Visibility: **Public**
5. **Click "Create Project"**

## Step 2: Set Up GitLab Pages

1. **Create `.gitlab-ci.yml` file** in your repository root:
   ```yaml
   pages:
     stage: deploy
     script:
       - mkdir public
       - cp README.md public/index.md
       - cp -r images public/
     artifacts:
       paths:
         - public
     only:
       - main
   ```

2. **Upload your files:**
   - Copy `USER_ONBOARDING.md` as `README.md`
   - Copy `images/` folder
   - Add the `.gitlab-ci.yml` file

3. **Commit and push** - GitLab Pages will automatically deploy

## Step 3: Access Your Documentation

- Available at: `https://YOUR_USERNAME.gitlab.io/gtdlc-onboarding-guide/`
- Updates automatically on every push to main branch

## Benefits:
- ✅ **Free hosting**
- ✅ **Automatic CI/CD**
- ✅ **Private repositories** supported on free tier
- ✅ **Custom domains** available 