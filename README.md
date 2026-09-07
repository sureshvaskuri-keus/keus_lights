# KEUS Lighting Catalogue — Profile Loading Fix

This package contains the latest responsive catalogue and corrected Profiles implementation.

## Important fixes

- Uses the latest 60-row Profiles CSV with:
  `Name, Stock Code, Cutout, New Description, Image`
- Profiles data is loaded from `data/profiles.csv`.
- Profile images try the optimized WebP URL first.
- If the WebP/CDN request fails, the browser automatically falls back to the original ImgBB image.
- `light-details.html` has the same image fallback.
- CSV loading also tries the repository root as a fallback if the `data/` path is accidentally deployed differently.
- Profiles do not calculate or display meaningless finish data.

## Structure

```text
/
├── index.html
├── light-details.html
├── .nojekyll
├── README.md
├── data/
│   ├── downlights.csv
│   ├── tracklights.csv
│   ├── profiles.csv
│   └── outdoor-lights.csv
└── scripts/
```
