# Plan: daily sales report

## Phase 1 · The page (done)
- Page layout: totals at the top, one table by store, one by collection.
- Check: the page opens in the browser and shows the three parts.

## Phase 2 · Read the export (built on example data, check blocked)
- `report.html` reads a sales CSV ("Choose the sales file") and fills the page from it.
  Until a file is chosen it shows `data/example-sales-export.csv` (made up, marked "Example data", with a yellow banner).
- Column names are set in one place at the top of the report code (`COLUMNS`, `DATE_ORDER`), to change when the real export arrives.
- Check: yesterday's total matches the total in the accounting system for one day we know.
- Blocked: no real export yet. We are waiting for the accounting team to send:
  the Sage product and version, a CSV of one known day, that day's net total from Sage,
  and which column means store and which means collection.
  How to export from each Sage product: `research/sage-connection.md`.

## Phase 3 · Compare with last week (built on example data, 11 Nov 2026)
- Next to the total, each store and each collection: sales on the same day last week and the difference in %.
- Check: done on example data. Riverside: € 4,411.11 on 10/11 and € 3,807.44 on 03/11 gives +16%, the same as the page.
  To repeat on the real export.
- Choices made (all confirmed 11 Nov 2026):
  - **Last week comes from the same file (confirmed 11 Nov 2026):** each daily export covers the last 8 days
    (yesterday and the same day last week). If a file has only one day, the page says there is no comparison.
  - **Amounts (confirmed 11 Nov 2026):** net, without VAT ("Net Amount").
  - **Percent:** whole number with sign (+16%, −5%); green up, red down, the sign always shown.
  - **Nothing last week:** shows "new" with no %. **Nothing yesterday but something last week:** € 0 and −100%.
  - **Order:** rows sorted by yesterday's sales, biggest first.
  - **"Yesterday" (confirmed 11 Nov 2026):** the latest date in the file, with that date shown above the total.

## Phase 4 · Share it
- Send the page to the sales team every morning.
