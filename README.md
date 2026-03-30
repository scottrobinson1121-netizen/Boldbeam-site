# BoldBeam.io — Deployment Guide

## Option 1: Deploy to Vercel (Recommended — Free)

### Step 1: Push to GitHub
1. Go to github.com and create a new repository called "boldbeam-site"
2. Upload all files from this folder to that repository
3. Or use the command line:
   ```
   cd boldbeam-site
   git init
   git add .
   git commit -m "Initial boldbeam.io site"
   git remote add origin https://github.com/YOUR-USERNAME/boldbeam-site.git
   git push -u origin main
   ```

### Step 2: Deploy on Vercel
1. Go to vercel.com and log in
2. Click "Add New Project"
3. Import your "boldbeam-site" repository from GitHub
4. Click "Deploy" — Vercel will detect the settings automatically
5. Your site will be live at a vercel.app URL within 60 seconds

### Step 3: Connect boldbeam.io domain
1. In Vercel, go to your project → Settings → Domains
2. Add "boldbeam.io"
3. Vercel will show you DNS records to add
4. Go to GoDaddy → DNS Management for boldbeam.io
5. Change the nameservers OR add the records Vercel shows you:
   - Type: A Record → Value: 76.76.21.21
   - Type: CNAME → Name: www → Value: cname.vercel-dns.com
6. Wait 10-30 minutes for DNS to propagate
7. boldbeam.io is now live!

### Step 4: Connect ConvertKit email capture
1. Sign up at kit.com (free tier)
2. Create a Form → choose "Inline" style
3. Copy the form's action URL
4. In index.html, replace the capture() JavaScript function with ConvertKit's embed code
5. Redeploy by pushing to GitHub (Vercel auto-deploys)

## Option 2: Deploy via Direct Upload to Vercel
If you don't want to use GitHub:
1. Install Vercel CLI: npm install -g vercel
2. In this folder, run: vercel
3. Follow the prompts
4. Add your domain in the Vercel dashboard

## File Structure
```
boldbeam-site/
├── public/
│   └── index.html    ← The complete website
├── vercel.json       ← Routing config
└── README.md         ← This file
```

## Updating the Site
Edit public/index.html, push to GitHub, and Vercel auto-deploys in ~30 seconds.

## What to Update Before Going Live
1. Replace "https://amazon.com" links with your actual book listing URLs
2. Add your real LinkedIn and Twitter/X profile URLs
3. Connect ConvertKit for email capture
4. Add your Amazon Author Page URL
