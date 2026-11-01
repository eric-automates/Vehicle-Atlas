# Vehicle Atlas — GitHub Pages edition

A standalone vehicle-research website. Visitors do **not** need Python, a terminal, an account, an API key, or a server. The app is independent and is not affiliated with any data provider.

## Publish the update

1. Replace the existing **`index.html`** in the branch and folder published by GitHub Pages (usually the repository root, sometimes `/docs`). It is self-contained: visitors do not need the other files in the ZIP to run it.
2. Commit, wait for Pages to deploy, and reload. If the old version still appears, force-refresh the browser or wait for deployment.
3. Click **Load latest data**. The progress panel reports each source separately; an unavailable source is retained from an earlier snapshot. An internet connection is needed for online updates and live lookups.

The included data also opens offline in a modern browser. The in-app document preview can block all network requests; use the deployed site or a normal browser for live data. Some browsers restrict live requests from a `file:` URL.

## Finding a car, truck or other vehicle

- Use the quick search near the top. **Find a vehicle** clears the previous filters and lens, then searches everything; for example, `Chevy Traverse` finds the existing Chevrolet Traverse configurations. It also recognizes aliases such as `VW` for Volkswagen. The detailed search stays synchronized with the quick search. Ordinary filter changes can still hide vehicles; use **Reset filters** to clear them.
- The included snapshot starts with **55,469 source records**: **50,407 EPA fuel-economy configurations** for model years **1984–2027**, plus **4,248 community model-only listings** and **814 additional model-only names** from the complaint summary after approximate-name deduplication. These are source records, not a count of unique cars; different naming conventions can still create duplicates. A model-only listing has no invented EPA MPG, exact trim, MSRP, or score.
- If a vehicle is missing, use **Find more models** under “Can’t find a vehicle?” Enter a make and model year. The app requests names from the NHTSA vPIC API and adds non-duplicate model-only names to the table for this session. vPIC can be incomplete or overinclusive and its names and model-year availability should be verified; it is not a definitive sales register. The original community catalogue is especially sparse for 2025 and 2026.
- If the vehicle is still missing, expand **Research a vehicle not listed** and enter its year, make and model. This opens an explicitly unverified, session-only research card, including links, photo search and on-demand NHTSA reports. It does not establish that the vehicle or model year was sold in the U.S., and it does not fill in unknown specs.
- The optional **Decode a VIN** tool sends the entered VIN directly to NHTSA vPIC and shows its reported vehicle details and decode status. You can add the decoded vehicle to the compare studio; its reported non-empty fields can be compared side by side. The VIN itself is excluded from the comparison field list and CSV export. Decoding does not check for open recalls. Visit [NHTSA’s recall lookup](https://www.nhtsa.gov/recalls) and enter the VIN there for an individual vehicle.

**Coverage limit:** No source here guarantees every American vehicle. The EPA fuel-economy database excludes many heavy-duty pickups, large vans and commercial vehicles; vPIC and the community model list also have gaps, possible errors and naming differences. A U.S. vehicle listing does not imply that its exact trim or every model year was sold. [EPA explains why some heavy-duty vehicles lack ratings.](https://www.fueleconomy.gov/feg/info.shtml#sizeclasses)

## Photos, color and comparisons

- Opening a vehicle or Compare studio searches **[Wikimedia Commons](https://commons.wikimedia.org/)** for candidate vehicle photos. Each displayed photo includes its file page, author and license; select **Next reference photo** to see another. Matching by year, make and model can be imperfect: a photo may show a different generation, year, trim or color, and some vehicles will have no matching photo. Photo requests need an internet connection. The large home-page image is a generic concept illustration, not a pictured model.
- Color swatches recolor a **generic vehicle illustration**, and can optionally affect the reference-photo search. They do **not** recolor the photo or claim to be factory colors for that vehicle. An unavailable image is not proof that a vehicle did not exist; retry or use the Commons search link.
- **Compare studio** supports up to four catalog or decoded-VIN vehicles. Choose Overview, MPG & energy, Specs, Problems, Reviews & links, Safety, All EPA fields or All VIN fields. Export the currently selected comparison view as CSV. To start from the table, select vehicles using their checkboxes, or open a vehicle and select **Add to compare**.
- In a vehicle card, **Find dimensions** queries **[Transport Canada Canadian Vehicle Specifications](https://open.canada.ca/data/en/dataset/913f8940-036a-45f2-a5f2-19bde76c1252)** via NHTSA vPIC. Select a candidate variant to add its measurements to the comparison. It is a Canadian-market reference, not proof of the exact U.S. trim; the source `MYR` may predate the requested model year. The source is used under the [Open Government Licence – Canada](https://open.canada.ca/en/open-government-licence-canada).
- **Reviews & links** provides generated outbound links to Consumer Reports reliability, Edmunds owner reviews, CarComplaints and an IIHS ratings search. Those sites have their own methods, may not have a matching model, and some Consumer Reports content may require a subscription. A link to [CarComplaints’ worst-vehicle ranking](https://www.carcomplaints.com/worst_vehicles/) opens that publisher’s own ranking and methodology. The app does **not** scrape their ratings, invent review scores or make a legal lemon determination.

## Explore reported problems

**Explore reported problems** filters, sorts and exports the exact vehicle-system labels in the dated complaint snapshot. The initial edition covers **4,087 model-years, 90,254 component rows and 678 labels** for 2010–2025. Search all models or narrow by year/make/model; choose labels such as **Electrical system**, **Power train** or **Power train, automatic transmission**. Power-train reports are broader than transmission-specific reports. The same complaint can mention multiple components; do not add overlapping counts or treat them as failure rates or lemon rankings. The snapshot excludes model-years with fewer than 10 total complaints, and its names may differ from EPA names. A missing row does not mean zero problems.

Vehicle details show the component breakdown for an unambiguous snapshot match. To look beyond that limited snapshot, click **Load NHTSA reports** in a vehicle card. The live model-name query shows a separately labeled component breakdown and example reports, with the full returned JSON available to download. The live API can use different component labeling and dates from the snapshot; the delimiter-based grouping can be ambiguous. Both are unverified owner allegations, not established defects, and neither is a VIN-specific open-recall check.

## Five everyday costs and recalls

Open a vehicle in the table and choose **Ownership costs & quote links**. The planner has:

1. Fuel or electricity, based on editable annual miles, consumption and prices.
2. Oil changes, using a shop or dealership quote and your assumed service interval.
3. Repairs, including a brake quote, optional other annual repairs, and a battery-estimate link.
4. Four replacement tires, with separate front and rear prices, installation, fees and tire tax.
5. Insurance and registration/other annual fees.

The planner also displays available model-matched recall and complaint counts. **Dealer-specific service prices and the cost of four exact OEM tires are not supplied automatically.** Use the outbound KBB, RepairPal, YourMechanic, TireSize.com and tire-retailer links, confirm the year, trim, engine, VIN, ZIP, exact tire brand/model/size and load/speed markings, and enter an actual quote. Those websites are not scraped; generated model links can require correction or may not be available. YourMechanic is a mobile mechanic; its estimates of shop/dealer prices are not actual dealership quotes. A compatible replacement tire is not necessarily the original-equipment tire.

The tire calculation assumes two front and two rear tires, applies the entered sales tax to the tire subtotal only, then adds four installation charges and additional fees. Add any installation tax to the fees. A blank rear price means the front price is used for all four. Enter tire life to annualize the installed cost. A six-wheel/dual-rear-wheel vehicle requires a separate quote beyond this four-tire calculator.

Fuel prices start with a dated national FuelEconomy.gov price snapshot and can be updated with **Load latest data**; edit them for local prices. The feed itself does not identify the price’s effective date, so the app displays the date it was checked. For EVs, the planner uses kWh per 100 miles and the electricity price—not MPGe as gasoline MPG. For plug-in hybrids it uses an editable electric-mile share, assuming those miles use only electricity and the others use gasoline; some plug-ins also burn gasoline in charge-depleting mode. Charging losses, temperatures and driving patterns can change real costs.

Annual totals are explicitly **partial**: blank items are omitted. They do not automatically include depreciation, loan payments, parking or other unentered costs. User-entered planner amounts stay in the current browser session and are not sent to the app’s sources.

## Recall and complaint counts

- The table’s **Recalls** column starts with partial, approximate matches from NHTSA recall archives where available. Use the row’s **Load / Update** button or **Load page recalls** for live NHTSA make/model/year counts. Page lookups are grouped by model name and run three at a time; large pages require confirmation and can be stopped. Live results are session-only.
- In vehicle details, edit the NHTSA model name and choose **Load NHTSA reports** for live recall and complaint counts and example reports. Download the complete returned JSON if desired. A failed request is not zero; a zero or empty name search does not prove there are no reports under a different name.
- Neither a model-year campaign count nor a complaint count is an individual VIN’s open-recall count, a failure rate or a reliability score. Complaints are unverified allegations; reporting differs with age and fleet size. Use [NHTSA’s VIN lookup](https://www.nhtsa.gov/recalls) for an individual vehicle.

## The five added public data sources

1. **[US Car Models Data](https://github.com/abhionlyone/us-car-models-data), Abhilash Reddy**, CC BY 4.0: a frozen community list of 11,543 year/make/model entries from 1992–2026, reshaped and exact-name-deduplicated against EPA to provide 4,248 initial extra model-only rows. The upstream free dataset is no longer updated and is especially incomplete in 2025–26. It may contain errors, unbuilt projections or duplicate names; verify exact availability. This app adapts the dataset; see `CC-BY-4.0.txt`.
2. **[Iqbal Taher / Oil & Miles, NHTSA complaints, Q3 2026 revision 2](https://doi.org/10.5281/zenodo.23685716)**, CC BY 4.0: a summary of the NHTSA complaints file dated August 25, 2026, covering 4,087 model-years from 2010–2025. The app adapts it by retaining the model-year total and all published exact component counts, and uses approximate name matching; ambiguous normalized-name collisions are omitted rather than combined. Model-years with fewer than 10 complaints are excluded, so a blank does **not** mean zero. **Load latest data** checks the publisher’s public GitHub files for a newer edition; the displayed date and attribution follow the retrieved metadata. Before applying a downloaded CSV, the app checks its SHA-256, byte count and available row counts against the publisher’s manifest; a mismatch retains the previous data.
3. **[NHTSA vPIC](https://vpic.nhtsa.dot.gov/api/)**: manufacturer-reported model names and VIN decoding are fetched directly, on demand. The catalogue and results are model-level and may have errors, omissions or inconsistent naming.
4. **[AAA 2026 Your Driving Costs](https://newsroom.aaa.com/wp-content/uploads/2026/09/8-YDC-Brochure_2026-1.pdf)**: the published weighted average for maintenance, repairs and tires is **11.73 cents per mile**; total ownership cost is **$12,863 per year** at 15,000 miles for AAA’s selection of new vehicles. It is a 2026 study benchmark, not a model-specific quote; its maintenance figure already includes one replacement tire set, so do not add it to an itemized tire/maintenance budget.
5. **[U.S. Bureau of Labor Statistics, CPI-U motor vehicle maintenance and repair, CUUR0000SETD](https://data.bls.gov/timeseries/CUUR0000SETD)**: a national monthly price index, not a dollar estimate. The app includes a September 2026 baseline and can retrieve the newest available monthly data from BLS. The percentage shown is the change against the same month one year earlier, when both values are available.

**Bonus repair-cost reference:** [AutoBlast, Auto Repair Cost Calculator — NJ Driver Guide](https://www.autoblast.online/tools/auto-repair-cost-calculator), updated April 22, 2026, data and methodology CC BY 4.0. The planner reproduces selected generic base ranges without AutoBlast’s vehicle-class multipliers: conventional oil $35–$75 and synthetic oil $70–$150 (AutoBlast cites KBB, 2024), and brake pads $320–$379 per axle (AutoBlast cites RepairPal, January 2026; excludes rotors and fluid). These are not vehicle-specific, local or dealer quotes and may exclude taxes and fees. They are examples only and are not automatically added to your budget.

The already-present FuelEconomy.gov fuel-price API is also used for the editable national fuel and electricity defaults. Prices, indexes and benchmarks are not exact vehicle-specific costs.

## Existing sources and updates

- **[EPA / DOE FuelEconomy.gov](https://www.fueleconomy.gov/feg/download.shtml):** The complete fuel-economy catalogue and all original columns. EPA can add, remove or revise records. MPG and MPGe are different measures; the primary plug-in value is gasoline-mode MPG, with electric values separately identified. EPA annual fuel cost uses its 15,000-mile/fuel-type-1 assumption; plug-in gasoline-mode cost excludes charging. Tailpipe CO₂ is not lifecycle CO₂.
- **[DOE My MPG](https://www.fueleconomy.gov/feg/ws/index.shtml#ympgVehicle):** On-demand self-reported harmonic averages, sometimes based on very small samples. They are not verified test results. Loading all filtered vehicles can require many requests and can be stopped.
- **[NHTSA ratings and recall archives](https://www.nhtsa.gov/nhtsa-datasets-and-apis):** Safety and equipment are approximate model/variant matches; recall counts are partial. Matching is not guaranteed for an exact trim. Open a vehicle to request live model reports.
- **[Wikimedia Commons](https://commons.wikimedia.org/):** Candidate photos are retrieved on demand with per-file attribution and license; matching and availability are not guaranteed.
- **[Transport Canada Canadian Vehicle Specifications](https://open.canada.ca/data/en/dataset/913f8940-036a-45f2-a5f2-19bde76c1252):** Optional Canadian-market candidate dimensions via vPIC, under the Open Government Licence – Canada; user selection is required and U.S. variants may differ.
- **[CarAPI sample](https://carapi.app/features/vehicle-csv-download/):** The public 2015–2020 sample provides candidate-trim historical MSRP, clearance, power, weight and seats. Matches may be incomplete or wrong; historical MSRP is not a current used-market price. Public availability alone does not establish redistribution or commercial-use rights; review the source terms before public use.

### Browser access, privacy and fallback

Several public bulk-file hosts do not allow direct cross-origin browser access. For those files, the app uses the independent no-signup **[cors.dev](https://cors.dev/)** gateway. The gateway receives the visitor’s IP address and the public source URLs; imported CSV, planner inputs and VINs are not sent through it. Its availability and limits can change. If the official EPA download fails, the app tries the **[KAPSARC mirror](https://datasource.kapsarc.org/explore/dataset/us-vehicle-fuel-economy-data-1984-2017/)**, which can lag the official data. The progress panel identifies fallbacks; if no source can be checked, the existing snapshot remains unchanged.

Direct NHTSA, vPIC, DOE, BLS and Oil & Miles/GitHub requests go to their respective providers. Opening a vehicle card or comparison automatically sends its year, make, model and selected color to Wikimedia Commons to find photos; Wikimedia also receives the visitor’s IP address. Transport Canada candidate queries go to NHTSA vPIC only when requested. Clicking external review or quote links opens those sites, which receive the navigation and any information the user enters there. A VIN is sent to NHTSA only when the user requests a decode; the actual VIN is excluded from displayed comparison fields and comparison CSV. Online request availability, CORS rules and rate limits may change.

After a successful core refresh, the EPA/recall/spec snapshot and the current complaint, BLS and fuel-price context are stored in the browser where storage is available. Otherwise an update is session-only. Clear the site’s browser storage to return to the included snapshots. The community catalogue and AAA report figures are bundled snapshots; vPIC additions, manual research cards, VIN-decoded comparison rows, photo selections, live per-model reports, imported CSV values and planner inputs are session-only. **Stop update** keeps the previous applied data.

## Scoring, filters and exports

- Ten curated lenses and a custom score use documented, fixed 0–100 normalization scales. Every required input must be present; missing information is never treated as zero or silently reweighted. Lenses are editorial examples, not measured buyer-preference rankings.
- With no search text, a lens may exclude vehicles outside its category. A text search can include those vehicles unscored so they are still findable; other explicit filters and the scored-only checkbox continue to apply. The quick **Find a vehicle** button clears those obstacles.
- Thresholds exclude unknown values. Charts compare filtered rows; EPA MPG and MPGe are different measures. Select up to four vehicles for comparison. Candidate-trim specifications marked `~` and model-level data should not be treated as exact trim facts.
- **Load EPA fields** enables all original EPA columns for EPA records. Model-only records have blank EPA IDs and EPA raw fields. CSV exports include all filtered rows—not just the page—plus source attribution, distinct snapshot/live recall fields and dated complaint-summary information.
- Import a CSV using exact positive `epa_id` values and fields in `import-template.csv`: `price_usd`, `ground_clearance_in`, `horsepower`, `curb_weight_lb`, `interior_rating`, `exterior_rating`, `reliability_rating`, `seats`, and `source`. Imported values are session-only; use data you own or have permission to use.

## Files

- `index.html` — complete standalone application and bundled snapshots; the only file needed to run the GitHub Pages site.
- `import-template.csv` — blank template for permitted user-provided metrics.
- `FFLATE-LICENSE.txt` — MIT license for the embedded fflate library; the license is also in the HTML.
- `CC-BY-4.0.txt` — Creative Commons Attribution 4.0 International license for the attributed CC BY 4.0 sources above.
- `README.md` — this guide.

The app is a research aid, not a substitute for verifying exact specifications, prices, recall status or a vehicle inspection.
