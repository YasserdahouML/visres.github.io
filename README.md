# VisRes Bench Project Page

This folder contains the project page for the VisRes Bench paper.

## 🌐 Deployment to GitHub Pages

### Option 1: Deploy from this subdirectory

1. Create a new GitHub repository or use your existing one
2. Push this entire project to the repository
3. Go to repository Settings → Pages
4. Under "Source", select the branch (e.g., `main`)
5. Under "Source", change the folder from `/ (root)` to `/webpage`
6. Click Save
7. Your site will be live at: `https://yourusername.github.io/repository-name/`

### Option 2: Deploy as a standalone repository

1. Create a new repository named `yourusername.github.io` (or any name)
2. Copy the contents of the `webpage` folder to the root of your repository:
   ```bash
   cd webpage
   git init
   git add .
   git commit -m "Initial commit: VisRes project page"
   git remote add origin https://github.com/yourusername/repository-name.git
   git push -u origin main
   ```
3. Go to repository Settings → Pages
4. Select the `main` branch and `/ (root)` folder
5. Your site will be live at: `https://yourusername.github.io/repository-name/`

## 📁 File Structure

```
webpage/
├── index.html          # Main HTML file
├── style.css           # All styling
├── images/             # All figures from the paper
│   ├── main_fig.pdf
│   ├── explainer_fig.pdf
│   ├── L1_*.pdf
│   ├── L2_*.pdf
│   └── L3_*.pdf
└── README.md          # This file
```

## ⚠️ Important: Converting PDFs to Images

**Note:** Web browsers cannot display PDF files as inline images (`<img>` tags). You need to convert the PDF files to PNG or JPG format.

### Batch convert all PDFs to PNGs:

Using ImageMagick:
```bash
cd images/
for file in *.pdf; do
    convert -density 300 "$file" -quality 90 "${file%.pdf}.png"
done
```

Using pdftoppm (from poppler-utils):
```bash
cd images/
for file in *.pdf; do
    pdftoppm -png -r 300 "$file" > "${file%.pdf}.png"
done
```

### After conversion:

Update the image references in `index.html` from `.pdf` to `.png`:
```bash
# In the webpage directory
sed -i '' 's/\.pdf/\.png/g' index.html
```

Or use a text editor to replace all `.pdf` extensions with `.png` in the image src attributes.

## 🎨 Customization

### Update Links
Edit `index.html` to add your actual links:
- Paper (arXiv) link
- Code & Dataset repository link
- Contact email

Search for these placeholder sections:
```html
<a href="#" class="btn btn-primary">Paper (arXiv)</a>
<a href="#" class="btn btn-secondary">Code & Dataset</a>
```

### Color Scheme
Edit `style.css` to change the color scheme. Look for the `:root` section at the top:
```css
:root {
    --primary-color: #2563eb;
    --secondary-color: #1e40af;
    ...
}
```

### Content
All content can be edited directly in `index.html`. The structure is organized by sections with clear comments.

## 🧪 Local Testing

To test locally, simply open `index.html` in a web browser:
```bash
open index.html  # macOS
xdg-open index.html  # Linux
start index.html  # Windows
```

Or use a local server (recommended):
```bash
# Python 3
python -m http.server 8000

# Then visit: http://localhost:8000
```

## 📱 Responsive Design

The page is fully responsive and will work on:
- Desktop computers
- Tablets
- Mobile phones

## 🔧 Technical Details

- **Pure HTML5 + CSS3** (no JavaScript dependencies)
- **No external dependencies** (no CDN links)
- **Fast loading** with optimized styles
- **SEO-friendly** with proper meta tags and semantic HTML
- **Accessible** with proper ARIA labels and semantic structure

## 📄 License

This project page template is free to use and modify for your research project.

## 🤝 Support

For issues or questions, contact: yasser.dahou@tii.ae

