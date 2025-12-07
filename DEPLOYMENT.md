# Deployment Guide

This guide will help you deploy the WordUp UX Enhancement Proposal to GitHub Pages.

## Prerequisites

- GitHub account
- Git installed on your computer
- Terminal/Command line access

## Step 1: Create GitHub Repository

1. Go to [GitHub](https://github.com) and sign in
2. Click the **+** icon in the top right corner
3. Select **New repository**
4. Repository name: `wordup` (or your preferred name)
5. Description: `WordUp UX/UI Enhancement Proposal - A comprehensive redesign showcasing improved user experience`
6. Set visibility: **Public** (required for free GitHub Pages)
7. **DO NOT** initialize with README, .gitignore, or license (we already have these)
8. Click **Create repository**

## Step 2: Connect Local Repository to GitHub

Run these commands in your terminal (replace `YOUR_USERNAME` with your GitHub username):

```bash
cd /Users/masih/Downloads/Cursors/wordup

# Add GitHub remote (replace YOUR_USERNAME with your actual GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/wordup.git

# Rename branch to main if needed
git branch -M main

# Push to GitHub
git push -u origin main
```

## Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **Settings** (top menu)
3. Scroll down to **Pages** (left sidebar)
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**

## Step 4: Access Your Live Site

After a few minutes, your site will be available at:
```
https://YOUR_USERNAME.github.io/wordup/
```

GitHub Pages may take 1-10 minutes to deploy. You can check the deployment status in the **Actions** tab.

## Alternative: Using GitHub CLI

If you have GitHub CLI installed:

```bash
# Install GitHub CLI (if not installed)
# macOS: brew install gh
# Then authenticate: gh auth login

# Create repository and push
gh repo create wordup --public --source=. --remote=origin --push
```

## Troubleshooting

### Images Not Loading
- Ensure all image paths in `index.html` use relative paths starting with `./assets/images/`
- Check that images are committed to git

### 404 Error
- Verify the repository is set to **Public**
- Check that `index.html` is in the root directory
- Wait a few minutes for GitHub Pages to update

### Deployment Not Working
- Check the **Actions** tab for error messages
- Ensure the workflow file `.github/workflows/pages.yml` is present
- Verify you're pushing to the `main` branch

## Custom Domain (Optional)

To use a custom domain:

1. Add a `CNAME` file in the root with your domain:
   ```
   yourdomain.com
   ```
2. Configure DNS records with your domain provider
3. Update GitHub Pages settings with your custom domain

## Updating the Site

After making changes:

```bash
git add .
git commit -m "Description of changes"
git push origin main
```

GitHub Pages will automatically rebuild and deploy your changes.

---

**Need Help?** Check the [GitHub Pages Documentation](https://docs.github.com/en/pages)

