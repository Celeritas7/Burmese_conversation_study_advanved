# 🔧 EXACT Steps to Fix Your App

## Your Current Problem
- Error: `Failed to load resource: main.jsx 404`
- Your CSV files are in `src/data/` but should be in `public/data/`

---

## Step-by-Step Fix

### Step 1: Move your CSV files
**Move** (not copy) your CSV files from `src/data/` to a NEW folder `public/data/`:

```
FROM: src/data/
  - Burmese_Conversation.csv
  - Consonants.csv
  - Special_cases.csv
  - Special_characters.csv
  - Vowels.csv

TO: public/data/   (create this folder)
  - Burmese_Conversation.csv
  - Consonants.csv
  - Special_cases.csv
  - Special_characters.csv
  - Vowels.csv
```

### Step 2: Replace these 4 files
From the ZIP file, replace these files in your project:

| File | Action |
|------|--------|
| `index.html` | REPLACE your existing one |
| `src/main.jsx` | REPLACE your existing one |
| `src/App.jsx` | REPLACE your existing one |
| `package.json` | REPLACE your existing one |
| `vite.config.js` | REPLACE your existing one |

### Step 3: Your folder should look like this after:
```
Burmese_conversation_study/
├── public/
│   └── data/                    ← NEW FOLDER
│       ├── Burmese_Conversation.csv
│       ├── Consonants.csv
│       ├── Special_cases.csv
│       ├── Special_characters.csv
│       └── Vowels.csv
├── src/
│   ├── components/              ← Keep this (not used anymore)
│   ├── data/                    ← DELETE this folder after moving
│   ├── App.jsx                  ← REPLACED
│   └── main.jsx                 ← REPLACED
├── index.html                   ← REPLACED
├── package.json                 ← REPLACED
└── vite.config.js               ← REPLACED
```

### Step 4: Install dependencies
Open terminal in your project folder:
```bash
npm install
```

### Step 5: Test locally
```bash
npm run dev
```
Open http://localhost:5173/Burmese_conversation_study_new/

**Make sure it works locally before deploying!**

### Step 6: Push to GitHub
```bash
git add .
git commit -m "Fix app structure for GitHub Pages"
git push
```

### Step 7: Deploy
```bash
npm run deploy
```

### Step 8: Configure GitHub Pages
1. Go to: https://github.com/Celeritas7/Burmese_conversation_study_new/settings/pages
2. Source: **Deploy from a branch**
3. Branch: **gh-pages** / **(root)**
4. Save

### Step 9: Access your app!
After 1-2 minutes:
**https://celeritas7.github.io/Burmese_conversation_study_new/**

---

## Summary of Changes

| Before | After |
|--------|-------|
| CSV in `src/data/` | CSV in `public/data/` |
| main.jsx imports wrong file | main.jsx imports App.jsx |
| App.jsx uses wrong CSV paths | App.jsx uses correct paths |
| No gh-pages script | Has deploy script |

---

## If You Get Errors

### "Module not found"
- Make sure `src/main.jsx` exists
- Make sure `src/App.jsx` exists

### "CSV not loading"
- Make sure `public/data/` folder exists
- Check CSV files are in `public/data/`

### "Blank page on GitHub Pages"
- Clear browser cache (Ctrl+Shift+R)
- Wait 2 minutes after deploy
- Check gh-pages branch exists
