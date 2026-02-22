# Portfolio Deployment Guide

## Step-by-Step Deployment to Cloudflare Pages

### Part 1: Create GitHub Repository

1. **Create New Repository**
   ```bash
   cd c:\Users\amanr\OneDrive\Documents\GitHub\rag-hosting\portfolio
   git init
   git add .
   git commit -m "Initial commit: Portfolio website"
   ```

2. **Create Repository on GitHub**
   - Go to [github.com/new](https://github.com/new)
   - Repository name: `portfolio`
   - Description: "Personal portfolio website"
   - Public or Private (your choice)
   - Don't initialize with README (we already have one)
   - Click "Create repository"

3. **Push to GitHub**
   ```bash
   git remote add origin https://github.com/amanrajfr/portfolio.git
   git branch -M main
   git push -u origin main
   ```

---

### Part 2: Deploy to Cloudflare Pages

1. **Access Cloudflare Dashboard**
   - Go to [dash.cloudflare.com](https://dash.cloudflare.com)
   - Sign in to your account

2. **Navigate to Pages**
   - In the left sidebar, click **"Workers & Pages"**
   - Click **"Create application"**
   - Select **"Pages"** tab
   - Click **"Connect to Git"**

3. **Connect GitHub**
   - Click **"Connect GitHub"**
   - Authorize Cloudflare (if first time)
   - Select your **"portfolio"** repository

4. **Configure Build Settings**
   - **Project name**: `portfolio` (or your choice)
   - **Production branch**: `main`
   - **Framework preset**: None
   - **Build command**: Leave empty
   - **Build output directory**: `/` (root directory)
   
5. **Deploy**
   - Click **"Save and Deploy"**
   - Wait for deployment (usually ~1 minute)
   - Your site will be live at: `portfolio.pages.dev`

---

### Part 3: Configure Custom Domain (amanraj.online)

#### Option A: If Domain is on Cloudflare

1. **Add Custom Domain**
   - In your Pages project, go to **"Custom domains"**
   - Click **"Set up a custom domain"**
   - Enter: `amanraj.online`
   - Click **"Continue"**
   - Cloudflare will automatically configure DNS
   - Wait 1-2 minutes for activation

#### Option B: If Domain is on Namecheap (Your Case)

##### Step 1: Get Cloudflare Nameservers

1. In Cloudflare, go to your **domain** (if already added) or **"Add a site"**
2. Add `amanraj.online` to Cloudflare
3. Cloudflare will provide 2 nameservers (example):
   ```
   bob.ns.cloudflare.com
   liv.ns.cloudflare.com
   ```
4. **Copy these nameservers**

##### Step 2: Update Namecheap DNS

1. Go to [Namecheap Dashboard](https://ap.www.namecheap.com/domains/list/)
2. Find `amanraj.online`, click **"Manage"**
3. Scroll to **"Nameservers"**
4. Select **"Custom DNS"**
5. Enter the Cloudflare nameservers:
   - Nameserver 1: `bob.ns.cloudflare.com` (use your actual ones)
   - Nameserver 2: `liv.ns.cloudflare.com`
6. Click **"Save"**
7. Wait 24-48 hours for propagation (usually ~1 hour)

##### Step 3: Configure DNS in Cloudflare

Once nameservers are updated:

1. In Cloudflare, go to **DNS** → **Records**
2. Cloudflare Pages should auto-add these records:
   - **CNAME** | `@` | `portfolio.pages.dev` | Proxied
   - **CNAME** | `www` | `portfolio.pages.dev` | Proxied

If not auto-added, add manually:
```
Type: CNAME
Name: @
Target: portfolio.pages.dev
Proxy status: Proxied (orange cloud)
```

---

### Part 4: Setup Subdomain for RAG Chat (ragchat.amanraj.online)

#### Step 1: Get Streamlit App URL

1. Go to your RAG app on Streamlit Cloud
2. Note the app URL (e.g., `your-app.streamlit.app`)

#### Step 2: Add CNAME Record in Cloudflare

1. Go to Cloudflare **DNS** → **Records**
2. Click **"Add record"**
3. Configure:
   ```
   Type: CNAME
   Name: ragchat
   Target: your-app.streamlit.app
   Proxy status: DNS only (gray cloud) - Important!
   TTL: Auto
   ```
4. Click **"Save"**

#### Step 3: Configure Custom Domain in Streamlit

1. Go to [share.streamlit.io](https://share.streamlit.io)
2. Open your RAG app settings
3. Click **"Settings"** → **"Custom domains"** (if available)
4. Add: `ragchat.amanraj.online`

> **Note**: Streamlit Cloud free tier may not support custom domains. Check Streamlit documentation for current availability.

**Alternative**: Keep using the Streamlit URL and just link it from your portfolio.

---

## Verification Checklist

### Main Portfolio
- [ ] Navigate to `amanraj.online` - loads correctly
- [ ] HTTPS/SSL certificate is active (🔒 in browser)
- [ ] All sections render properly
- [ ] Mobile responsive works
- [ ] Project links work

### Subdomain
- [ ] `medicheck.amanraj.online` - works (existing)
- [ ] `ragchat.amanraj.online` - works (new)

---

## DNS Records Summary

After setup, your DNS should look like:

| Type | Name | Target | Proxy |
|------|------|--------|-------|
| CNAME | @ | portfolio.pages.dev | Proxied |
| CNAME | www | portfolio.pages.dev | Proxied |
| CNAME | medicheck | [existing-target] | As configured |
| CNAME | ragchat | your-app.streamlit.app | DNS only |

---

## Troubleshooting

### Issue: Domain not loading after 24 hours

**Solution:**
- Check nameserver propagation: [whatsmydns.net](https://www.whatsmydns.net)
- Verify nameservers are correctly set in Namecheap
- Clear browser cache

### Issue: SSL certificate error

**Solution:**
- Wait a few minutes after domain setup
- Cloudflare auto-provisions SSL (usually instant)
- Try accessing via `https://` explicitly

### Issue: Subdomain not working

**Solution:**
- Verify CNAME record is correct
- Check if target app is accessible directly
- For Streamlit: Verify custom domain is supported on your plan

---

## Maintenance

### Update Portfolio

```bash
# Make changes to files
git add .
git commit -m "Update portfolio content"
git push origin main

# Cloudflare Pages auto-deploys (1-2 minutes)
```

### Monitor Performance

- Cloudflare Analytics: View traffic and performance
- Real User Monitoring: Available in Cloudflare dashboard

---

## Next Steps

1. ✅ Create GitHub repository
2. ✅ Deploy to Cloudflare Pages
3. ✅ Configure custom domain
4. ✅ Setup subdomains
5. 🎯 Share your portfolio!

---

**Questions or Issues?**
Reach out via the contact methods on your portfolio!

Good luck! 🚀
