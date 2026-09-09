# KEUS Lighting Catalogue

Updated UI accent uses #5b524a / #403a35 / #c6beb6. Product finish colours are not changed.

The All Products control is a custom KEUS-styled dropdown. Product cards retain CSV order; the dropdown remains alphabetical. Each light series card shows its total variant count at the top-right.


## Mobile compact + swipe update

- 4 category tabs are smaller, with smaller icons, tighter spacing and a cleaner pill shape.
- The finish filter section is reduced in height.
- Finish chips and colour circles are smaller.
- Product colour indicators are compact dots.
- On mobile, swiping left/right on a product image changes that product’s finish.
- The corresponding colour dot highlights automatically.
- Only that product’s image and MRP change.
- Detail-page finish chips are slightly smaller.
- `profiles.csv` remains included correctly inside `data/`.


## All colour dots visible on mobile

- Every available product finish dot is shown under the product card.
- No finish dots are hidden behind horizontal scrolling or a `+N` indicator.
- Swiping left/right on the product image changes the finish.
- The matching dot highlights immediately.
- Only that product's image and MRP change.


## Stock code + mobile details fix

- Details page shows one stock code only for the currently selected finish/colour.
- Changing the finish re-renders the selected stock code dynamically.
- If the selected finish has multiple image variants, choosing a thumbnail updates the exact stock code and MRP for that image variant.
- Mobile details layout now prevents page-wide horizontal overflow.
- Product image, finish chips, thumbnails, specification grid and variant table are contained responsively.
- Variant table scrolls inside its own container on mobile.


## Profiles — New Description colour variations

This update is isolated to the `profiles` category. Downlights, Tracklights and Outdoor Lights retain their existing behaviour.

Profile colour/body + diffuser variation is extracted only from `New Description` and mapped to these UI codes:

- WH — White
- GW — Grey & White Diffuser
- CW — Champagne & White Diffuser
- BW — Black & White Diffuser
- IGW — Iron Grey & White Diffuser
- WW — White & White Diffuser
- BB — Black & Black Diffuser
- WB — White & Black Diffuser
- WT — White & Transparent Diffuser
- BT — Black & Transparent Diffuser
- BK — Black

Selecting a variation changes the Profile image using the `Image` value from that same CSV row. The Profile Stock Code, Cutout and description also follow the selected row.

No changes were made to the data schema; `data/profiles.csv` still uses:
`Name, Stock Code, Cutout, New Description, Image`


## Font-size + WebP update

- All existing UI `font-size` values in `index.html` and `light-details.html` are increased by 30%.
- The change is typography-only; product logic, category behaviour, filters and profile variation logic are preserved.
- All four CSV data files now store WebP delivery URLs through `https://wsrv.nl/`.
- The original ImgBB image remains embedded inside each wsrv URL as the source, so the catalogue can continue using the same product artwork while loading WebP.
- `scripts/optimize_csv_images.py` remains included so future raw ImgBB links can be converted to the same WebP format.
