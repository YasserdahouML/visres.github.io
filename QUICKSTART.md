# Quick Start Guide

## 🚀 View Locally (Right Now!)

### Option 1: Direct File Open
Simply double-click `index.html` or run:
```bash
open index.html  # macOS
```

### Option 2: Local Server (Recommended)
```bash
# Navigate to the webpage folder
cd webpage

# Start a local server
python3 -m http.server 8000

# Open browser to: http://localhost:8000
```

## 📦 What's Included

```
webpage/
├── index.html          # Complete project page
├── style.css           # All styling (no external dependencies)
├── images/             # All figures (PNG format)
│   ├── main_fig.png
│   ├── explainer_fig.png
│   └── ... (all benchmark figures)
├── README.md           # Full deployment guide
└── QUICKSTART.md       # This file
```

## ✏️ Before Publishing

### 1. Update Your Links
Edit `index.html` lines 34-36:
```html
<a href="#" class="btn btn-primary">Paper (arXiv)</a>
<a href="#" class="btn btn-secondary">Code & Dataset</a>
```

Replace `#` with your actual URLs:
```html
<a href="https://arxiv.org/abs/YOUR_PAPER_ID" class="btn btn-primary">Paper (arXiv)</a>
<a href="https://github.com/YOUR_USERNAME/YOUR_REPO" class="btn btn-secondary">Code & Dataset</a>
```

### 2. Update Contact Email
Edit line 574 (in footer):
```html
<p>Contact: <a href="mailto:yasser.dahou@tii.ae">yasser.dahou@tii.ae</a></p>
```

## 🌐 Deploy to GitHub Pages

### Quick Deploy (Recommended)
1. Create a new repository on GitHub
2. Upload the entire `webpage` folder contents to the repository root
3. Go to Settings → Pages
4. Select branch (e.g., `main`) and folder `/ (root)`
5. Save and wait ~1 minute
6. Your site will be live at: `https://yourusername.github.io/repository-name/`

### Command Line Deploy
```bash
cd webpage
git init
git add .
git commit -m "Initial commit: VisRes project page"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git branch -M main
git push -u origin main
```

Then enable GitHub Pages in repository settings.

## 🎨 Customization Tips

### Change Colors
Edit `style.css` lines 9-17:
```css
:root {
    --primary-color: #2563eb;     /* Main blue */
    --secondary-color: #1e40af;   /* Darker blue */
    --accent-color: #3b82f6;      /* Light blue */
    ...
}
```

### Change Header Gradient
Edit `style.css` line 114:
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

Try these alternatives:
- Ocean: `linear-gradient(135deg, #00c6ff 0%, #0072ff 100%)`
- Sunset: `linear-gradient(135deg, #f093fb 0%, #f5576c 100%)`
- Forest: `linear-gradient(135deg, #11998e 0%, #38ef7d 100%)`

## ✅ Checklist Before Publishing

- [ ] Tested locally in browser
- [ ] Updated arXiv paper link
- [ ] Updated code/dataset repository link
- [ ] Updated contact email
- [ ] Verified all images load correctly
- [ ] Checked mobile responsiveness (resize browser)
- [ ] Proofread all text content

## 📱 Test Responsiveness

Resize your browser window to test:
- Desktop: > 1024px wide
- Tablet: 768px - 1024px wide
- Mobile: < 768px wide

Or use browser dev tools (F12) → Device Toolbar

## 🆘 Troubleshooting

### Images not loading?
- Check that PNG files exist in `images/` folder
- Check browser console (F12) for errors
- Verify file paths in HTML are correct

### Styling looks broken?
- Ensure `style.css` is in the same folder as `index.html`
- Check browser console for CSS loading errors

### Page looks different on GitHub Pages?
- Wait 1-2 minutes after deploying for cache to clear
- Hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)

## 🎉 That's It!

Your project page is ready to publish. For detailed documentation, see `README.md`.

For questions, contact: yasser.dahou@tii.ae

