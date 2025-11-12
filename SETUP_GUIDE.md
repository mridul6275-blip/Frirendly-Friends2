# GitHub Setup Guide for Friendly Friends App

This guide will help you upload your Friendly Friends App to GitHub.

## Step 1: Create a GitHub Repository

1. Go to [GitHub](https://github.com) and sign in
2. Click the "+" icon in the top right corner
3. Select "New repository"
4. Name your repository (e.g., "friendly-friends-app")
5. Choose public or private
6. **DO NOT** initialize with README, .gitignore, or license (we'll add these)
7. Click "Create repository"

## Step 2: Initialize Git in Your Project

Open terminal in your project root directory and run:

```bash
# Initialize git repository
git init

# Add all files
git add .

# Make your first commit
git commit -m "Initial commit: Friendly Friends App"

# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 3: Copy GitHub Configuration Files

Copy these files from the `github/` folder to your project root:

```bash
# Copy .gitignore to root
cp github/.gitignore .

# Copy README.md to root
cp github/README.md .
```

## Step 4: Update README.md

Edit the `README.md` file with:
- Your actual license information
- Your GitHub username/repository name
- Any additional project-specific information

## Step 5: Commit and Push Configuration Files

```bash
git add .gitignore README.md
git commit -m "Add GitHub configuration files"
git push
```

## Step 6: Set Up Environment Variables (Important!)

**DO NOT commit your `.env` file!** It's already in `.gitignore`.

Instead, set up environment variables in GitHub:

1. Go to your repository on GitHub
2. Click "Settings"
3. Click "Secrets and variables" → "Actions"
4. Add secrets:
   - `OPENAI_API_KEY`
   - `FLASK_SECRET_KEY`
   - Any other sensitive data

## Step 7: Optional - Add GitHub Actions

If you want CI/CD, create `.github/workflows/` directory and add workflow files.

## Important Notes

### Files NOT to Upload:
- `node_modules/` (already in .gitignore)
- `*.db` files (database files - already in .gitignore)
- `.env` files (environment variables - already in .gitignore)
- `uploads/` folder (user content - already in .gitignore)
- `dist/` folder (build output - already in .gitignore)

### Files TO Upload:
- All source code (`.py`, `.jsx`, `.js`, `.css`, `.html`)
- Configuration files (`package.json`, `requirements.txt`, `vite.config.js`)
- Documentation files
- `.gitignore` and `README.md`

## Troubleshooting

### If you get "repository not found" error:
- Check that your repository URL is correct
- Verify you have access to the repository
- Make sure you're authenticated: `git config --global user.name "Your Name"` and `git config --global user.email "your.email@example.com"`

### If files are too large:
- Check `.gitignore` is working: `git status`
- Remove large files: `git rm --cached large_file.ext`
- Use Git LFS for large files if needed

### If you need to update:
```bash
git add .
git commit -m "Update: describe your changes"
git push
```

## Next Steps

After uploading:
1. Add collaborators in repository settings
2. Set up branch protection rules
3. Enable GitHub Pages if needed
4. Add issues and project boards
5. Set up GitHub Actions for CI/CD

Happy coding! 🚀

