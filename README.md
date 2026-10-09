# Berghaus Tower Prices

Interactive 3D price map of the Berghaus A6 east tower (Koningin Wilhelminaplein, 1062 LE Amsterdam), floors 5–12, 80 apartments.

- **3D model** (three.js) colour-coded by price, €/m², type, transfer date, or deviation from a price model
- **Price model**: OLS of €/m² on apartment type + floor + months since Jul 2025, computed live in the browser (R² ≈ 0.97 on 49 sales)
- **Charts + sortable table** of all units; estimates for units without a recorded sale

## Data
All data lives inline in `index.html` (`const RAW = [...]`), one row per unit:
`[houseNo, type, floor, areaGBO_m2, position, price|null, transferDate|null]`

- Floor areas: NEN 2580 GBO measurements (type B, block A6)
- Sale prices/dates: Kadaster koopsominformatie, postcode 1062 LE (Jul 2025 – Aug 2026)
- Rentals (other Berghaus blocks): publicly advertised asking rents from Funda and Huurmatcher, checked 2026-10-09, in the `RENT` array near the end of `index.html`. Only units visible online are included.

To add sales, edit `RAW`; the model and every chart recompute automatically. Update `TODAY` when refreshing estimates.

## Run
Static single file, no build. Open `index.html` or serve the folder with any static host.

## Support
Free to use. Donation link: see the "Support this page" section (`DONATION_LINK` placeholder in `index.html`).

Not a valuation or financial advice.
