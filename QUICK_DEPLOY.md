# Quick Deployment Steps - Portfolio

## ✅ Completed
- Git repository initialized
- All files committed successfully

## 📝 Next Steps (Manual - Please Follow)

### Step 1: Create GitHub Repository

1. **Open your browser** and go to: https://github.com/new

2. **Fill in the form**:
   - Repository name: `portfolio`
   - Description: `Personal portfolio website`  
   - Visibility: **Public** (recommended) or Private
   - **DO NOT** check any boxes (no README, no .gitignore, no license)

3. **Click "Create repository"**

4. You'll see a page with setup instructions. **Keep this page open.**

---

### Step 2: Push Code to GitHub

Copy and run these commands **one at a time**:

```bash
# Set branch to main
git branch -M main

# Add GitHub remote (REPLACE with your actual URL from step 1)
git remote add origin https://github.com/amanrajfr/portfolio.git

# Push to GitHub
git push -u origin main
```

**If you get authentication error**, use your GitHub token:
```bash
git remote set-url origin https://ghp_YOUR_TOKEN@github.com/amanrajfr/portfolio.git
git push -u origin main
```

---

### Step 3: Deploy to Cloudflare Pages

1. **Go to**: https://dash.cloudflare.com

2. **Navigate**: Workers & Pages → Create application → Pages

3. **Connect to Git**: 
   - Click "Connect to Git"
   - Authorize GitHub if needed
   - Select your `portfolio` repository

4. **Build Settings**:
   - Project name: `portfolio` (or your choice)
   - Production branch: `main`
   - Framework preset: **None**
   - Build command: **Leave empty**
   - Build output directory: `/`

5. **Click "Save and Deploy"**

6. **Wait** ~1-2 minutes for deployment

7. Your portfolio will be live at: `portfolio.pages.dev` or similar

---

### Step 4: Configure Custom Domain

1. In your Cloudflare Pages project, go to **"Custom domains"**

2. Click **"Set up a custom domain"**

3. Enter: `amanraj.online`

4. Cloudflare will add DNS records automatically

5. **If domain is on Namecheap**:
   - You may need to update nameservers to Cloudflare
   - Or manually add CNAME record in Namecheap DNS

---

## 🎯 Current Status

✅ Git initialized
✅ Files committed
⏳ Ready to push to GitHub

**Next Action**: Create GitHub repository and run push commands above!

---

Let me know when you've completed each step, or if you need help!
