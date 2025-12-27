# KPC-31 Resistome Analysis Website

Comprehensive genomic and phenotypic analysis of 42 carbapenemase-producing bacterial isolates.

## 🌐 Live Website

Once deployed, your website will be available at:
`https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

## 📋 Contents

This repository contains:
- `index.qmd` - Homepage
- `resistome_analysis_report.qmd` - Full analytical report
- `about.qmd` - Methods and technical details
- `_quarto.yml` - Website configuration
- `styles.css` - Custom styling
- `Progetto 1 (KPC-31) versione 2.xlsx` - Data file (optional to include)

## 🚀 Setting Up GitHub Pages

### Prerequisites

1. **Install Quarto** (if not already installed)
   - Download from: https://quarto.org/docs/get-started/
   - Verify installation: `quarto --version`

2. **Install R and required packages**
   ```r
   install.packages(c("tidyverse", "readxl", "knitr", "kableExtra"))
   ```

3. **GitHub account**
   - Create one at https://github.com if you don't have one

### Step 1: Create a GitHub Repository

1. Go to https://github.com/new
2. Repository name: Choose a name (e.g., `kpc31-resistome-analysis`)
3. Description: "Analysis of KPC-31 carbapenemase-producing Enterobacterales"
4. Set to **Public** (required for free GitHub Pages)
5. ✅ Check "Add a README file"
6. Click "Create repository"

### Step 2: Prepare Your Local Files

1. **In your Positron/RStudio terminal**, navigate to your project directory:
   ```bash
   cd /path/to/your/project
   ```

2. **Initialize git** (if not already done):
   ```bash
   git init
   ```

3. **Edit `_quarto.yml`** to update the GitHub link:
   - Replace `YOUR-USERNAME` with your GitHub username
   - Replace `YOUR-REPO-NAME` with your repository name

4. **Render the website** to generate HTML files:
   ```bash
   quarto render
   ```
   
   This creates a `docs/` folder with your website files.

### Step 3: Push to GitHub

1. **Add all files to git**:
   ```bash
   git add .
   ```

2. **Commit the changes**:
   ```bash
   git commit -m "Initial commit: KPC-31 resistome analysis website"
   ```

3. **Connect to your GitHub repository**:
   ```bash
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
   ```
   
   Replace `YOUR-USERNAME` and `YOUR-REPO-NAME` with your actual values.

4. **Push to GitHub**:
   ```bash
   git branch -M main
   git push -u origin main
   ```

### Step 4: Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/YOUR-USERNAME/YOUR-REPO-NAME`

2. Click **Settings** (top menu)

3. Click **Pages** (left sidebar)

4. Under "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/docs**
   - Click **Save**

5. Wait 1-2 minutes for deployment

6. Refresh the page - you'll see:
   > "Your site is live at https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/"

7. Click the link to view your website! 🎉

## 🔄 Updating Your Website

When you make changes:

1. **Edit your `.qmd` files** in Positron/RStudio

2. **Re-render the website**:
   ```bash
   quarto render
   ```

3. **Commit and push changes**:
   ```bash
   git add .
   git commit -m "Update analysis"
   git push
   ```

4. **GitHub Pages will automatically update** (takes 1-2 minutes)

## 📊 Data Privacy

**Important**: By default, the Excel data file will be included in your repository.

**To keep data private**:
1. Uncomment the line `# *.xlsx` in `.gitignore`
2. The website will still work if users have the data file locally
3. Or, remove all data-dependent code sections

## 🛠️ Local Development

To preview your website locally before pushing:

```bash
quarto preview
```

This opens a local web server (usually at http://localhost:4200) where you can see live updates as you edit files.

## 📁 File Structure

```
your-project/
├── index.qmd                           # Homepage
├── resistome_analysis_report.qmd       # Full report
├── about.qmd                           # About page
├── _quarto.yml                         # Configuration
├── styles.css                          # Custom styling
├── .gitignore                          # Git ignore rules
├── README.md                           # This file
├── Progetto 1 (KPC-31) versione 2.xlsx # Data (optional)
└── docs/                               # Generated website (after render)
    ├── index.html
    ├── resistome_analysis_report.html
    ├── about.html
    └── ...
```

## 🎨 Customization

### Change Theme
Edit `_quarto.yml`:
```yaml
format:
  html:
    theme: cosmo  # Try: flatly, journal, lumen, sandstone, etc.
```

### Update Colors
Edit `styles.css` to change colors, fonts, spacing, etc.

### Add More Pages
1. Create new `.qmd` file
2. Add to `_quarto.yml` navbar
3. Re-render and push

## ❗ Troubleshooting

### Website not showing up?
- Wait 2-3 minutes after first deployment
- Check Settings → Pages shows "Your site is published"
- Verify Branch is set to "main" and Folder to "/docs"

### Plots not showing?
- Make sure `execute: echo: false` is set in YAML
- Check that `embed-resources: true` is NOT set in `_quarto.yml` (it's for single files only)

### Changes not appearing?
- Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)
- Check that you ran `quarto render` before pushing
- Verify new commit appears on GitHub

### Data file errors?
- Make sure the Excel file is in the same directory as the `.qmd` files
- Or update the `file_path` in the code chunks

## 📚 Resources

- **Quarto Documentation**: https://quarto.org/docs/websites/
- **GitHub Pages Guide**: https://docs.github.com/en/pages
- **Markdown Guide**: https://www.markdownguide.org/

## 📧 Contact

[Your contact information]

## 📄 License

[Add your license here - e.g., MIT, CC-BY-4.0, etc.]

---

**Last updated**: December 27, 2025
