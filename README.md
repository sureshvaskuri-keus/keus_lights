# KEUS Lighting Catalogue — GitHub-ready static site

This project uses the supplied KEUS catalogue HTML design and automatically loads CSV files from the `data` folder.

## Structure

```text
keus_lighting_catalogue_github/
├── index.html
├── README.md
├── .nojekyll
├── data/
│   ├── downlights.csv
│   ├── tracklights.csv
│   ├── profiles.csv
│   └── outdoor-lights.csv
└── assets/
    └── images/
        ├── downlight.svg
        ├── tracklight.svg
        ├── profile.svg
        └── outdoor.svg
```

## Category → CSV mapping

- Down Lights → `data/downlights.csv`
- Track Lights → `data/tracklights.csv`
- Profiles → `data/profiles.csv`
- Outdoor Lights → `data/outdoor-lights.csv`

Visitors do not upload CSV files. Clicking a tab automatically fetches the matching CSV.

## CSV columns

Keep these headers exactly (the code also accepts several common aliases):

```text
Name,Item No,Vf,Imax,CCT,CRI,Cutout,Beam Angle,Wattage,Batch Code,Stock Code,IMAGE
```

## Finish codes

The last stock-code segment can be:

- W = White
- B = Mat Black
- CG = Champagne Gold
- RG = Rose Gold
- BR = Brown
- COF = Coffee
- DGR = Dark Gray
- BB = Ballet Blue
- CH = Chrome
- CHB = Chrome Black

Example: `ATP15/CHB`.

When a product such as Altair Prime 15 is selected, the catalogue displays one card for every available finish in that product's CSV rows.

## Replacing dummy data

Replace the contents of the CSV files but keep the same file names. You do not need to edit `index.html`.

The bundled SVG images are only local placeholders for this demo. In your final CSV, put your actual hosted image URL in the `IMAGE` column.

## GitHub Pages

1. Create a GitHub repository.
2. Upload everything inside this folder to the repository root.
3. Open Settings → Pages.
4. Choose **Deploy from a branch**.
5. Select `main` and `/ (root)`.
6. Save.

GitHub Pages will serve `index.html` and the browser will fetch the CSV files from the `data` folder.

## Local preview

Do not rely on double-clicking `index.html`, because browsers can block CSV `fetch()` under `file://`.

From this folder you can run:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/`.
