Add items to inventory.

Read `inventory/freezer.md`, `inventory/pantry.md`, `inventory/fridge.md`.

The user will provide either:
- A simple list of items (e.g., "added 2 lbs ground beef, bag of apples, 3 cans chicken broth")
- A grocery receipt (pasted text, photo, or file — parse all food items)

## Guard — don't double-add a receipt
For receipts: check the dated notes at the top of the inventory files. If a note already matches this store + receipt date → warn: "Looks like I already added a [store] receipt from [date] — add anyway?" and wait for confirmation.

## Instructions
1. For each item, pick the correct file: pantry, fridge, or freezer
2. Add with quantity if known
3. If an item already exists, update the quantity rather than duplicating
4. Receipts: skip non-food items (household, personal care) unless clearly relevant (like paper towels)
5. Skip anything `family/household-rules.md` says never to buy or track
6. For receipts, add a dated note to each updated file: `Updated YYYY-MM-DD — added receipt ([store], [receipt date])`

After updating, give a brief summary:
- Added to Pantry / Fridge / Freezer: [lists]
- Items updated (quantity changed): [list]
- Skipped (well stocked or non-food): [list]
