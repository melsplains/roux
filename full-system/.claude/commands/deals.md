Update this week's deals file (`stores/this_week.md`).

## Step 1 — Get the deals

Ask the user (or use what they already provided):

> "Drop screenshots of this week's ads/deals from your store apps, paste the deals as text, or give me store names and I'll try fetching their weekly ad. Which stores are we working with this week?"

Sources, in order of reliability:
1. **Screenshots or pasted text** from the user's store apps (weekly ad, digital coupons, loyalty offers). This is the primary source — loyalty/clipped coupons are account-specific and can't be fetched.
2. **Web fetch** (best effort): many grocery chains block automated requests to their own sites, but coupon matchup blogs and flipp.com often work. If a fetch fails, skip it silently and rely on what the user provided.

**Partial updates:** if the user says "just [store]", rewrite only that store's section of `stores/this_week.md` and leave the others untouched with their original week dates visible.

## Step 2 — Parse, merge, and organize

For each store, build:

- **Digital Coupon / Loyalty Deals** (with expiration dates)
- **Weekly Sale Prices** (grouped: Meat, Produce, Dairy, Frozen, Bread, Snacks, Beverages, Pantry)
- **Price Comparison Notes** (same item at multiple stores — flag which is better)

Rules:
- Skip non-grocery noise (clothing, patio furniture, electronics) unless it's a household staple
- Flag items expiring within 2 days with ⚠️
- Note multi-buy requirements clearly (Buy 5 Save $5, BOGO, etc.)
- Ad week dates at the top of the file AND at the top of each store's section

## Step 3 — Write and confirm

Write to `stores/this_week.md` (create the folder if it doesn't exist; full rewrite, or per-store section rewrite for partial updates).

Confirm: "Deals updated for week of [dates]. ~[X] items across [stores]. Highlights worth planning around: [2–4 bullets on the best protein/produce deals]"
