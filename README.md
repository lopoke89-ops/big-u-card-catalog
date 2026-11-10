# Big U Basketball Card Catalog

An offline-friendly, single-page basketball card catalog for tracking example listings and price comparisons across 12 NBA players.

## Included

- **60 cards** copied from the November 10, 2026 catalog
- Dark responsive interface and searchable card grid/table
- Filters for player, year, rookies, autographs, numbered cards, grades, relics, parallels, asking prices, sold medians, and asking premiums
- CSV export of filtered results
- Links to original seller listings or searches where available

## View the site

Open `index.html` in a browser or publish the repository using GitHub Pages:

1. Go to **Settings → Pages** in the repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select `main` and `/(root)`, then **Save**.
4. After GitHub deploys the site, the URL will be `https://<github-username>.github.io/<repository-name>/`.

## Important data notes

This is a snapshot, **not a live-price feed**. Historical example asks are not necessarily current listings. Market medians are included only where the source catalog supplied them; **N/V** means not verified, not zero. Prices exclude taxes, shipping, and fees. Some checklist/category flags are derived from card titles and should be verified on the underlying cards.

`cards.json` contains the extracted entries for future updates. `index.html` also embeds the same data, so the page can open without a local web server. If you edit JSON only, regenerate the embedded data in HTML to synchronize the site.