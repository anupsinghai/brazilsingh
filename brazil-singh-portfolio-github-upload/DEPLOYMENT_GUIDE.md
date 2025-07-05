# GitHub Pages Deployment Guide

This guide will help you deploy your Brazil Singh portfolio website to GitHub Pages.

## Prerequisites

1. **GitHub Account**: Make sure you have a GitHub account
2. **Git Installed**: Ensure Git is installed on your computer
3. **Node.js**: Make sure Node.js (version 18 or higher) is installed

## Method 1: Automatic Deployment with GitHub Actions (Recommended)

### Step 1: Upload Your Code to GitHub

1. **Create a new repository** on GitHub:
   - Go to https://github.com/new
   - Name it `brazil-singh-portfolio` (or any name you prefer)
   - Make it **Public** (required for free GitHub Pages)
   - Don't initialize with README, .gitignore, or license

2. **Upload your project files**:
   ```bash
   # Navigate to your project folder
   cd brazil-singh-portfolio
   
   # Initialize git repository
   git init
   
   # Add all files
   git add .
   
   # Commit files
   git commit -m "Initial commit: Brazil Singh Portfolio"
   
   # Add your GitHub repository as origin
   git remote add origin https://github.com/YOUR_USERNAME/brazil-singh-portfolio.git
   
   # Push to GitHub
   git branch -M main
   git push -u origin main
   ```

### Step 2: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **Settings** tab
3. Scroll down to **Pages** section in the left sidebar
4. Under **Source**, select **GitHub Actions**
5. The deployment will start automatically when you push code

### Step 3: Access Your Website

After the GitHub Action completes (usually 2-5 minutes), your website will be available at:
```
https://YOUR_USERNAME.github.io/brazil-singh-portfolio/
```

## Method 2: Manual Deployment

If you prefer manual deployment or the automatic method doesn't work:

### Step 1: Install Dependencies and Build

```bash
# Navigate to your project folder
cd brazil-singh-portfolio

# Install dependencies (if not already installed)
npm install

# Install gh-pages package
npm install --save-dev gh-pages

# Build the project
npm run build
```

### Step 2: Deploy to GitHub Pages

```bash
# Deploy to gh-pages branch
npm run deploy
```

### Step 3: Configure GitHub Pages

1. Go to your repository settings
2. Navigate to **Pages** section
3. Under **Source**, select **Deploy from a branch**
4. Select **gh-pages** branch
5. Select **/ (root)** folder
6. Click **Save**

## Troubleshooting

### Common Issues and Solutions

1. **404 Error on GitHub Pages**
   - Make sure your repository is **Public**
   - Check that GitHub Pages is enabled in repository settings
   - Wait a few minutes for deployment to complete

2. **CSS/JS Files Not Loading**
   - This is handled by the `base` configuration in `vite.config.js`
   - Make sure the repository name matches the base path

3. **Build Fails**
   - Check that all dependencies are installed: `npm install`
   - Ensure Node.js version is 18 or higher: `node --version`

4. **GitHub Actions Fails**
   - Check the Actions tab in your repository for error details
   - Make sure the repository has Pages enabled
   - Verify the workflow file is in `.github/workflows/deploy.yml`

### Manual Build and Upload (Alternative)

If automated deployment doesn't work, you can manually upload the built files:

1. **Build the project locally**:
   ```bash
   npm run build
   ```

2. **Create a new repository** on GitHub named `YOUR_USERNAME.github.io`

3. **Upload only the contents of the `dist` folder** to this repository

4. **Your site will be available at**: `https://YOUR_USERNAME.github.io`

## File Structure

Your repository should have this structure:
```
brazil-singh-portfolio/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions workflow
├── src/                        # Source code
├── public/                     # Public assets
├── dist/                       # Built files (generated)
├── package.json               # Dependencies and scripts
├── vite.config.js             # Vite configuration
└── DEPLOYMENT_GUIDE.md        # This guide
```

## Important Notes

1. **Repository Name**: If you change the repository name, update the `base` path in `vite.config.js`
2. **Custom Domain**: You can add a custom domain in GitHub Pages settings
3. **HTTPS**: GitHub Pages automatically provides HTTPS
4. **Updates**: Push new code to the main branch to trigger automatic redeployment

## Support

If you encounter any issues:
1. Check the GitHub Actions logs in the "Actions" tab
2. Verify all files are uploaded correctly
3. Ensure the repository is public
4. Wait a few minutes for changes to propagate

Your modern, vibrant portfolio website will be live and accessible to the world once deployed!

