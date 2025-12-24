# Complete GitHub Pages Deployment Guide

## 🚀 Step-by-Step Guide to Host Your VisRes Project Page

### Prerequisites
- A GitHub account (free) - [Sign up here](https://github.com/join) if you don't have one
- Git installed on your computer - [Download here](https://git-scm.com/downloads)

---

## Method 1: Deploy from Web Interface (Easiest - No Command Line!)

### Step 1: Create a New Repository

1. Go to [GitHub](https://github.com) and log in
2. Click the **"+"** button in the top-right corner
3. Select **"New repository"**

### Step 2: Repository Settings

Choose **ONE** of these naming options:

**Option A: User/Organization Site** (Recommended)
- Repository name: `yourusername.github.io` (replace `yourusername` with your actual GitHub username)
- Your site will be at: `https://yourusername.github.io/`

**Option B: Project Site**
- Repository name: `visres-bench` (or any name you prefer)
- Your site will be at: `https://yourusername.github.io/visres-bench/`

**Settings for both:**
- ✅ Public repository
- ✅ Add a README file (optional)
- Click **"Create repository"**

### Step 3: Upload Your Files

1. In your new repository, click **"Add file"** → **"Upload files"**

2. Drag and drop ALL files from the `webpage` folder:
   - `index.html`
   - `style.css`
   - `images/` folder (with all PNG files inside)
   - `.gitignore` (optional but recommended)

3. Scroll down, add a commit message like: `Initial commit: VisRes project page`

4. Click **"Commit changes"**

### Step 4: Enable GitHub Pages

1. In your repository, click **"Settings"** (top menu)

2. In the left sidebar, click **"Pages"**

3. Under **"Source"**:
   - Branch: Select **`main`** (or `master` if that's your default)
   - Folder: Select **`/ (root)`**
   - Click **"Save"**

4. Wait 1-2 minutes for deployment

5. Refresh the page - you'll see a green box with your site URL:
   - `✅ Your site is live at https://yourusername.github.io/`

6. **Click the link** to view your live site! 🎉

---

## Method 2: Deploy Using Command Line (For Git Users)

### Step 1: Prepare Your Files

```bash
# Navigate to the webpage directory
cd /Users/yasserdahou/Downloads/cvpr_visual_puzzles_arvix_arXiv/webpage
```

### Step 2: Initialize Git Repository

```bash
# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: VisRes project page"
```

### Step 3: Create GitHub Repository

1. Go to GitHub.com and create a new repository (see Method 1, Step 2 for naming)
2. **DO NOT** initialize with README, .gitignore, or license
3. Copy the repository URL (looks like: `https://github.com/yourusername/repository-name.git`)

### Step 4: Push to GitHub

```bash
# Add remote repository
git remote add origin https://github.com/yourusername/repository-name.git

# Rename branch to main (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

### Step 5: Enable GitHub Pages

Follow **Method 1, Step 4** above to enable GitHub Pages in repository settings.

---

## 🔧 Before Going Live - Important Updates!

### Update Your Links

Open `index.html` and update these:

**Line 34:** Add your arXiv paper link
```html
<!-- Change this: -->
<a href="#" class="btn btn-primary">Paper (arXiv)</a>

<!-- To this: -->
<a href="https://arxiv.org/abs/YOUR_PAPER_ID" class="btn btn-primary">Paper (arXiv)</a>
```

**Line 574:** Verify contact email
```html
<p>Contact: <a href="mailto:yasser.dahou@tii.ae">yasser.dahou@tii.ae</a></p>
```

After making changes:
```bash
git add index.html
git commit -m "Update paper link and contact info"
git push
```

Wait 1-2 minutes for changes to go live.

---

## 📋 Deployment Checklist

Before sharing your site, make sure:

- [ ] Site loads correctly at your GitHub Pages URL
- [ ] All images display properly
- [ ] Paper (arXiv) link is updated
- [ ] Contact email is correct
- [ ] Test on mobile (resize browser window)
- [ ] Navigation arrows work in carousel
- [ ] All sections display correctly
- [ ] BibTeX citation is correct at bottom

---

## 🔄 How to Update Your Site

Whenever you make changes:

### Option 1: Web Interface
1. Go to your repository on GitHub
2. Click on the file you want to edit
3. Click the pencil icon (✏️) to edit
4. Make changes
5. Scroll down and click "Commit changes"
6. Wait 1-2 minutes - changes are live!

### Option 2: Command Line
```bash
# Make your changes to files
# Then:

git add .
git commit -m "Description of changes"
git push
```

Wait 1-2 minutes for changes to deploy.

---

## 🎨 Custom Domain (Optional)

Want to use your own domain like `visres.yourdomain.com`?

### Step 1: In GitHub Repository Settings → Pages

1. Under "Custom domain", enter: `visres.yourdomain.com`
2. Click "Save"
3. Check "Enforce HTTPS" (after DNS propagates)

### Step 2: Configure Your Domain DNS

Add these DNS records in your domain registrar:

**For subdomain (visres.yourdomain.com):**
```
Type: CNAME
Name: visres
Value: yourusername.github.io
```

**For apex domain (yourdomain.com):**
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
```

Wait 24-48 hours for DNS propagation, then your site will be live on your custom domain!

---

## 🆘 Troubleshooting

### Problem: Site shows 404 error

**Solution:**
- Wait 2-3 minutes after enabling Pages
- Make sure `index.html` is in the root directory
- Check that Pages is enabled in Settings
- Verify the branch is correct (main/master)

### Problem: Images not loading

**Solution:**
- Make sure `images/` folder is uploaded
- Check that all images are `.png` (not `.pdf`)
- Verify file paths in `index.html` are correct: `images/filename.png`
- Force refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)

### Problem: Changes not showing

**Solution:**
- Wait 1-2 minutes after pushing changes
- Hard refresh your browser: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)
- Clear browser cache
- Try incognito/private mode

### Problem: Carousel not working

**Solution:**
- Make sure JavaScript is enabled in your browser
- Check browser console for errors (F12 → Console tab)
- Clear cache and refresh

### Problem: Styling looks broken

**Solution:**
- Verify `style.css` is in the same directory as `index.html`
- Check that both files were uploaded
- Hard refresh browser

---

## 📊 GitHub Pages Limitations

✅ **What's Allowed:**
- Static HTML, CSS, JavaScript files
- Images (PNG, JPG, GIF, SVG)
- Total size: 1 GB recommended
- Bandwidth: 100 GB/month soft limit
- Builds: 10 per hour

❌ **What's NOT Allowed:**
- Server-side code (PHP, Python, etc.)
- Databases
- File uploads
- Complex backend logic

Your VisRes page uses only static files, so you're good! ✅

---

## 🚀 Your Site URLs

After deployment, your site will be live at:

**Option A (User site):**
- URL: `https://yourusername.github.io/`
- Example: `https://yasserdahou.github.io/`

**Option B (Project site):**
- URL: `https://yourusername.github.io/repository-name/`
- Example: `https://yasserdahou.github.io/visres-bench/`

---

## 📱 Share Your Site

Once live, share your site URL:
- On Twitter/X with your paper announcement
- In your arXiv paper abstract
- In your email signature
- With collaborators and reviewers

---

## 🎉 You're Done!

Your VisRes Bench project page is now live on the internet!

**Next steps:**
1. Share the URL with your team
2. Add the URL to your arXiv paper
3. Tweet about it with #VLM #VisualReasoning #MachineLearning
4. Update your paper link once on arXiv

---

## 📞 Need Help?

**Resources:**
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Community Forum](https://github.community/)

**Contact:**
- Email: yasser.dahou@tii.ae

**Common GitHub Pages Examples:**
- OpenAI: https://openai.github.io/
- Segment Anything: https://segment-anything.com/
- Your site: https://yourusername.github.io/

---

## 🔐 Repository Settings Recommendations

### Make Repository Public
- Settings → General → Danger Zone
- Keep it public so GitHub Pages works

### Enable Issues (Optional)
- Settings → General → Features
- Enable "Issues" for people to report problems

### Add Description
- Go to repository main page
- Click ⚙️ next to "About"
- Add: "VisRes Bench: A benchmark for evaluating visual reasoning in VLMs"
- Add website URL
- Add topics: `vision-language-models`, `benchmark`, `visual-reasoning`

---

**Good luck with your paper! Your project page looks fantastic! 🎊**

