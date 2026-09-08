# KEUS Lighting Catalogue — Selected Colour Logic

## Fixed behaviour

1. Stock Code
- Details page shows only the stock code for the selected colour.
- Changing colour updates the stock code.
- If a colour has multiple image variants, selecting the image thumbnail also updates the exact stock code.

2. Rate / MRP
- Landing-page cards show only the MRP for the colour currently displayed.
- Default is White when White exists; otherwise the first available finish.
- Clicking Rose Gold, Champagne Gold, etc. updates only that card's image and MRP.
- Details page shows only the MRP for the selected colour.

3. Colour scrolling
- No +4 / +N indicator.
- All available colour swatches are rendered.
- Colours scroll horizontally on product cards.
- Colours scroll horizontally on the product-details page.
- Touch scrolling works on mobile.

4. Existing fixes retained
- Changing one product colour does not change other products.
- Profiles use the simplified layout.
- Mobile has no pagination.
- WebP image delivery has original ImgBB fallback.


## Mobile details responsive fix

- Prevents horizontal page overflow.
- Product image scales correctly to phone width.
- Finish colours use touch-enabled horizontal scrolling.
- Image thumbnails use horizontal scrolling.
- Header and Back button fit narrow screens.
- Stock codes and long technical values wrap safely.
- Technical specification grid adapts from 2 columns to 1 column on very narrow phones.
- Variant table is contained inside its own horizontal scroller instead of stretching the page.


## Compact mobile UI update

- Category tabs are smaller, lighter and more compact.
- Finish filter chips are smaller on mobile.
- Product finish indicators are compact dots.
- Swipe left/right on a product image on mobile to cycle through available finishes.
- The active finish dot highlights automatically after swiping.
- Image and MRP update only for the product being swiped.
- The Profiles CSV remains included at `data/profiles.csv`.


## Product ordering + dropdown

- Product cards preserve the exact first-appearance order from each CSV file.
- Product cards are not alphabetically sorted.
- The `All Products` dropdown is alphabetically sorted.
- The selector uses a compact KEUS-style treatment with warm white, restrained gold accents, rounded corners and tighter spacing.


## KEUS black product dropdown

The browser-native product dropdown has been replaced visually by a custom KEUS dropdown:
- charcoal/black surface
- white product names
- subtle selected-item outline
- restrained gold active indicator and arrow
- compact rounded spacing
- custom hover/focus states
- same alphabetical product ordering
- existing hidden native select retained only for filter-state compatibility


## Accent colour correction

This version keeps the earlier visual treatment:
- white product-card surfaces
- white controls and finish chips
- warm light landing-page background
- black / charcoal product dropdown

Only the previous gold accent (`#b28746`) has been replaced with KEUS taupe (`#5b524a`).
