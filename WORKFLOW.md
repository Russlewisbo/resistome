# 📊 GitHub Pages Workflow Diagram

## Your Files → GitHub → Website

```
┌─────────────────────────────────────────────────────────────┐
│                    YOUR LOCAL COMPUTER                       │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  📁 Your Project Folder                                      │
│  ├── index.qmd                    ← Homepage                 │
│  ├── resistome_analysis_report.qmd ← Full Report            │
│  ├── about.qmd                    ← About Page               │
│  ├── _quarto.yml                  ← Configuration            │
│  ├── styles.css                   ← Styling                  │
│  └── Progetto 1 (KPC-31)...xlsx  ← Data                     │
│                                                               │
│  💻 Step 1: Edit files in Positron/RStudio                   │
│                                                               │
│  ⚡ Step 2: Run: quarto render                               │
│       │                                                       │
│       ├─→ Creates docs/ folder with HTML files               │
│       │                                                       │
│       └─→ docs/                                              │
│           ├── index.html                                     │
│           ├── resistome_analysis_report.html                 │
│           ├── about.html                                     │
│           └── (all plots, tables, etc.)                      │
│                                                               │
└─────────────────────────────────────────────────────────────┘
                         │
                         │ git push
                         ↓
┌─────────────────────────────────────────────────────────────┐
│                         GITHUB                               │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  🐙 Your Repository: username/kpc31-resistome-analysis      │
│                                                               │
│  main branch:                                                │
│  ├── All your .qmd files                                    │
│  ├── _quarto.yml                                            │
│  └── docs/ ← GitHub Pages serves from here!                 │
│      ├── index.html                                         │
│      ├── resistome_analysis_report.html                     │
│      └── ...                                                │
│                                                               │
└─────────────────────────────────────────────────────────────┘
                         │
                         │ GitHub Pages
                         │ (automatic)
                         ↓
┌─────────────────────────────────────────────────────────────┐
│                    LIVE WEBSITE 🌐                          │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  🌍 https://username.github.io/kpc31-resistome-analysis/    │
│                                                               │
│  ┌─────────────────────────────────────────┐               │
│  │  🏠 Homepage                             │               │
│  │  ├─ Quick Summary                        │               │
│  │  ├─ Key Findings                         │               │
│  │  └─ Links to Full Report                 │               │
│  └─────────────────────────────────────────┘               │
│                                                               │
│  ┌─────────────────────────────────────────┐               │
│  │  📊 Full Report                          │               │
│  │  ├─ All analyses                         │               │
│  │  ├─ Interactive plots                    │               │
│  │  ├─ Tables                               │               │
│  │  └─ Collapsible code                     │               │
│  └─────────────────────────────────────────┘               │
│                                                               │
│  ┌─────────────────────────────────────────┐               │
│  │  ℹ️  About Page                          │               │
│  │  ├─ Methods                              │               │
│  │  ├─ Data sources                         │               │
│  │  └─ Technical details                    │               │
│  └─────────────────────────────────────────┘               │
│                                                               │
│  Anyone can access this URL! 🎉                             │
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

## 🔄 Update Workflow

```
Edit .qmd → quarto render → git push → Website updates!
   📝            ⚡             🚀           ✨
 (2 min)      (1 min)       (1 min)    (1-2 min)
```

## 📋 Checklist

### One-Time Setup
- [ ] Create GitHub repository
- [ ] Edit `_quarto.yml` (update username/repo)
- [ ] Run `quarto render`
- [ ] Push to GitHub
- [ ] Enable GitHub Pages in Settings
- [ ] Wait 2 minutes
- [ ] Visit your website!

### Every Update
- [ ] Edit files
- [ ] Run `quarto render`
- [ ] `git add . && git commit && git push`
- [ ] Wait 1-2 minutes
- [ ] Refresh website

## 🎯 Key Points

1. **Edit locally** - Work on `.qmd` files in Positron
2. **Render locally** - `quarto render` creates HTML
3. **Push to GitHub** - Git uploads everything
4. **GitHub Pages** - Automatically serves from `docs/` folder
5. **Website updates** - Takes 1-2 minutes to go live

## 🔒 Data Privacy Options

### Option 1: Keep Data Public
```
└── Data included in GitHub (anyone can download)
```

### Option 2: Keep Data Private
```
1. Uncomment *.xlsx in .gitignore
2. git rm --cached "*.xlsx"
3. Users need local copy to run code
4. Website still shows all results (already rendered)
```

## 🌟 What Makes This Special

- ✅ **Free** - GitHub Pages is free for public repos
- ✅ **Fast** - Updates in minutes
- ✅ **Professional** - Clean, modern design
- ✅ **Interactive** - All plots and tables work
- ✅ **Mobile-friendly** - Works on phones/tablets
- ✅ **Shareable** - Just share the URL
- ✅ **Version controlled** - Full history with git

## 💡 Tips

- Use `quarto preview` to see changes before pushing
- Hard refresh (Ctrl+Shift+R) if changes don't show
- Check GitHub Actions tab to see deployment status
- Custom domain possible (see GitHub Pages docs)

---

**Next**: Open `QUICKSTART.md` for step-by-step commands!
