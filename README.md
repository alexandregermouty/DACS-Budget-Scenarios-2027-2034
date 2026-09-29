# DACS Cost Explorer

Interactive cost scenarios for the UN Decade of Action for Cryospheric Sciences 2025–2034 (budget period 2027–2034).
Static site: no backend and no database. Each viewer's edits are saved in their own browser only.

## Contents

```
index.html                     The application
assets/img/                    DACS and UNESCO logos, background images, favicon
.github/workflows/pages.yml    Deploys to GitHub Pages on every push to main
.nojekyll                      Serves the files as they are, without Jekyll processing
404.html, robots.txt           Redirect to the app; asks search engines not to index it
```

## Deploy on GitHub Pages

1. Create a repository (for example `dacs-cost-explorer`) and push this folder's contents to `main`:
   ```
   git init
   git add .
   git commit -m "DACS Cost Explorer"
   git branch -M main
   git remote add origin https://github.com/YOUR-ACCOUNT/dacs-cost-explorer.git
   git push -u origin main
   ```
2. In the repository, open **Settings > Pages** and set **Source** to **GitHub Actions**.
3. The workflow runs on each push. The site is published at `https://YOUR-ACCOUNT.github.io/dacs-cost-explorer/`.

Without Actions, choose **Deploy from a branch** instead, branch `main`, folder `/ (root)`.

GitHub Pages sites are public, even from a private repository (except with private Pages on GitHub Enterprise Cloud).
If the figures must stay internal, use the Firebase version or another access-controlled host.

## Test locally

`python3 -m http.server 8080` in this folder, then open http://localhost:8080.

## Updating figures

The default values of the model are in `index.html`, in the `WORKBOOK` object at the top of the script.
They reproduce `DACS_Cost_scenarios_2027-2034.xlsx`. After changing them, viewers click "Reset to workbook" to load the new defaults
(each viewer's own edits are kept in their browser until they do).
