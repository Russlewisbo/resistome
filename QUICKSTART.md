# 🚀 Quick Start Guide - GitHub Pages Setup

## 5-Minute Setup

### 1️⃣ Create GitHub Repository (2 min)
```
1. Go to: https://github.com/new
2. Name: kpc31-resistome-analysis
3. Public ✅
4. Add README ✅
5. Click "Create repository"
```

### 2️⃣ Prepare Files (1 min)
```bash
# In your terminal (where your files are):
cd /path/to/your/project

# Edit _quarto.yml line 13:
# Change: YOUR-USERNAME to your GitHub username
# Change: YOUR-REPO-NAME to kpc31-resistome-analysis

# Render website
quarto render
```

### 3️⃣ Push to GitHub (1 min)
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR-USERNAME/kpc31-resistome-analysis.git
git branch -M main
git push -u origin main
```

### 4️⃣ Enable GitHub Pages (1 min)
```
1. Go to: https://github.com/YOUR-USERNAME/kpc31-resistome-analysis
2. Click: Settings → Pages
3. Source: Deploy from a branch
4. Branch: main
5. Folder: /docs
6. Save
```

### ✅ Done!
Your site will be live in 1-2 minutes at:
```
https://YOUR-USERNAME.github.io/kpc31-resistome-analysis/
```

---

## 🔄 To Update Website Later

```bash
# 1. Make your changes to .qmd files
# 2. Re-render
quarto render

# 3. Push changes
git add .
git commit -m "Update analysis"
git push
```

Website updates automatically in 1-2 minutes!

---

## ❓ Common Issues

**Q: Website shows 404?**
- A: Wait 2-3 minutes after first setup
- Check Settings → Pages shows "published"

**Q: Changes not showing?**
- A: Did you run `quarto render` before pushing?
- Try hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)

**Q: How do I keep data private?**
- A: In `.gitignore`, uncomment: `# *.xlsx`
- Then: `git rm --cached "*.xlsx"` and push

---

## 📱 Share Your Website

Once live, share this link:
```
https://YOUR-USERNAME.github.io/kpc31-resistome-analysis/
```

The website works on:
- 💻 Desktop browsers
- 📱 Mobile devices
- 📊 Contains all interactive plots and tables
- 🔍 Searchable and navigable

---

**Need detailed help?** See `README.md`

**Problems?** Check: https://quarto.org/docs/troubleshooting/
