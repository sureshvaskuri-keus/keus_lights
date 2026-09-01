# KEUS Static Lighting Catalogue

This is a static website. It automatically reads CSV files stored inside the project.

## Folder structure

```text
keus_static_catalogue/
├── index.html
├── assets/
│   ├── css/
│   │   └── styles.css
│   └── js/
│       └── app.js
└── data/
    ├── downlights.csv
    ├── tracklights.csv
    ├── profiles.csv
    └── outdoor-lights.csv
```

## How it works

`assets/js/app.js` maps each category tab to one CSV file:

- Downlights → `./data/downlights.csv`
- Tracklights → `./data/tracklights.csv`
- Profiles → `./data/profiles.csv`
- Outdoor Lights → `./data/outdoor-lights.csv`

When a visitor clicks a category, JavaScript fetches the matching CSV, parses it in the browser, groups rows by product name, detects finishes from Stock Code, and renders the catalogue.

There is NO "upload CSV" step for the visitor.

## Required CSV headers

Keep these column names:

```text
Name,Item No,Vf,Imax,CCT,CRI,Cutout,Beam Angle,Wattage,Batch Code,Stock Code,IMAGE
```

You can add or replace rows freely. Keep the file names unchanged unless you also edit `CATEGORIES` inside `assets/js/app.js`.

## Finish codes recognised

```text
W   = White
B   = Mat Black
CG  = Champagne Gold
RG  = Rose Gold
BR  = Brown
COF = Coffee
DGR = Dark Gray
BB  = Ballet Blue
CH  = Chrome
CHB = Chrome Black
```

The finish code should preferably be the final part of Stock Code, e.g.:

```text
ATP15/W
ATP15/B
ATP15/CG
ATP15/CHB
```

## Publishing on GitHub Pages

1. Create a GitHub repository.
2. Upload the entire contents of this folder.
3. Go to Settings → Pages.
4. Source: Deploy from a branch.
5. Branch: `main`.
6. Folder: `/ (root)`.
7. Save.

GitHub Pages will serve `index.html`.

## Updating catalogue data later

Replace only the CSV you need inside `/data`.

Example:
- update downlights only → replace `data/downlights.csv`
- no HTML or JavaScript change required

Commit/push the change to GitHub and the website will use the new CSV automatically.

## Important

Do not test by double-clicking `index.html` and opening it with a `file://` URL. Browsers can block `fetch()` from local files.

Use GitHub Pages, VS Code Live Server, Python `http.server`, or another HTTP server.
