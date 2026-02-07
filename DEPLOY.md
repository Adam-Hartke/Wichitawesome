# 🚀 GITHUB DEPLOYMENT GUIDE

## Quick Deploy to GitHub Pages (5 Minutes)

### Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Repository name: `wichitawesome`
3. Make it **Public** (required for free GitHub Pages)
4. Don't initialize with README (we have one)
5. Click "Create repository"

### Step 2: Push Your Code

```bash
# Navigate to your project folder
cd wichitawesome

# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit - Wichitawesome platform"

# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR_USERNAME/wichitawesome.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top right)
3. Click **Pages** (left sidebar)
4. Under "Build and deployment":
   - Source: **GitHub Actions**
5. That's it! Your site will deploy automatically

### Step 4: Access Your Site

Your site will be live at:
```
https://YOUR_USERNAME.github.io/wichitawesome/
```

**First deployment takes 2-3 minutes.** Check the "Actions" tab to see progress.

---

## 🎯 CUSTOM DOMAIN SETUP

Want `wichitawesome.com` instead of GitHub's URL?

### 1. Buy Domain
- Go to Namecheap, GoDaddy, or Google Domains
- Buy `wichitawesome.com` (~$12/year)

### 2. Configure DNS
Add these records at your domain registrar:

```
Type: A
Name: @
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153

Type: CNAME
Name: www
Value: YOUR_USERNAME.github.io
```

### 3. Configure GitHub
1. Go to repo Settings → Pages
2. Under "Custom domain", enter: `wichitawesome.com`
3. Check "Enforce HTTPS" (after DNS propagates, ~1 hour)
4. Done!

---

## 🔄 UPDATING YOUR SITE

Every time you push to `main` branch, the site automatically updates:

```bash
# Make changes to your files
# Then:

git add .
git commit -m "Update event images"
git push

# Site updates automatically in 1-2 minutes
```

---

## 📁 PROJECT STRUCTURE

```
wichitawesome/
├── .github/
│   └── workflows/
│       └── deploy.yml          # Auto-deployment config
├── public/
│   └── manifest.json           # PWA configuration
├── index.html                   # Main homepage
├── README.md                    # Deployment instructions
└── .gitignore                   # Git ignore rules
```

---

## 🐛 TROUBLESHOOTING

### "404 - Site not found"
- Wait 2-3 minutes after first push
- Check Actions tab - deployment must complete
- Verify Pages is enabled in Settings

### "Deployment failed"
- Check `.github/workflows/deploy.yml` exists
- Verify file permissions
- Look at Actions tab for error details

### Custom domain not working
- DNS changes take up to 24 hours (usually 1-2 hours)
- Use `dig wichitawesome.com` to check DNS propagation
- Verify CNAME file was created in repo root

### Images not loading
- All image paths must be absolute (start with `/` or `https://`)
- Check browser console for 404 errors
- Verify images are in the repo

---

## 📊 GITHUB PAGES LIMITS

- **Free tier includes:**
  - 1 GB storage
  - 100 GB bandwidth/month
  - Unlimited builds
  - HTTPS included

- **This is plenty for:**
  - 10,000+ users/month
  - Hundreds of events
  - Fast load times globally

---

## 🚀 NEXT STEPS AFTER DEPLOYMENT

### Immediate
1. ✅ Verify site loads at your GitHub Pages URL
2. Share link with 5-10 friends for feedback
3. Test on mobile (add to home screen)

### Week 1
1. Set up Google Analytics (optional)
2. Create social media accounts
3. Start collecting emails with waitlist

### Week 2-4
1. Move to full Next.js app (see main README)
2. Set up Supabase database
3. Implement event scraping
4. Launch MVP with real users

---

## 💡 TIPS

**Static vs Full App:**
- Current setup: Static HTML (perfect for landing page)
- Next step: Next.js app with database (for full platform)
- You can run both: static site at wichitawesome.com, full app at app.wichitawesome.com

**Free Hosting Alternatives:**
- Vercel (recommended for Next.js apps)
- Netlify (great for static + serverless)
- Cloudflare Pages (fastest global CDN)

All support custom domains and auto-deploy from GitHub!

---

## 📞 COMMON COMMANDS

```bash
# Check status
git status

# Pull latest changes
git pull

# Create new branch
git checkout -b feature-name

# Switch branches
git checkout main

# View commit history
git log --oneline

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Force push (careful!)
git push --force
```

---

## ✅ YOU'RE LIVE!

Your Wichitawesome platform is now deployed. Every change you make will automatically go live when you push to GitHub.

**Next:** See main README.md for building the full platform with database, scraping, and user accounts.
