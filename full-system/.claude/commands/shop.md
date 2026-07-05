Generate the grocery list and (after approval) push it to AnyList.

Read ALL of these:
- this week's `weekly/[YYYY-MM-DD]/meal-plan.md`
- `inventory/freezer.md`, `inventory/pantry.md`, `inventory/fridge.md`
- `planning/needs-this-week.md`
- `family/household-rules.md` (staples list + budget) and `family/family-preferences.md` (snack lists, lunch items)
- `stores/this_week.md` if it exists

**Step 1: Compile everything needed**

Go through each dinner in the meal plan. For every dinner and its sides:
- Pull the real ingredient list from AnyList for any recipe that lives there — don't guess ingredients for recipes that exist in AnyList
- List EVERY ingredient (protein, vegetables, starches, sauces, spices, oils, toppings)
- Be exhaustive — better to include something the user crosses off than to miss it
- Include all lunch and breakfast items running low
- Include every item from `planning/needs-this-week.md` regardless of the meal plan

**Step 2: Staples check**

Walk the "Pantry / Freezer Items to Always Have" list in `household-rules.md` and the snack lists in `family-preferences.md` item by item. Anything not confidently in stock goes on the list. A meal plan is not a grocery list; the staples are what get forgotten — do not skip this step.

**Step 3: Cross-reference inventory**

For each ingredient:
- Clearly in stock and sufficient → omit (only if CERTAIN from the inventory files)
- Marked LOW, GONE, or not found → include
- Uncertain → INCLUDE (always err on inclusion)

**Step 4: Assign stores (only if `stores/this_week.md` exists)**

- Item on deal/coupon at one store → assign there
- No deal anywhere → default to the primary store
- A second store trip is only worth it if that store's basket saves real money (~$15+) — otherwise fold those items into the primary store and note the call

If there's no deals file, build one list for the user's usual store.

**Step 5: Build the list**

Organize by store (if multiple), then by store section:

```
## [STORE]
### Produce
- [ ] item — quantity (deal note if applicable)
### Meat & Seafood / Dairy / Frozen / Bread / Pantry / Snacks / Beverages / Household
...
```

Give an estimated total and flag if it's approaching the budget maximum from `household-rules.md`.

**Step 6: Push to AnyList (ask first)**

Ask: "Approved to push to AnyList?" Only proceed after confirmation.

1. Add every item to the matching AnyList shopping list (one list per store), deal notes in the item notes. If a store's list doesn't exist in AnyList yet, keep those items in the markdown list and tell the user — the MCP can't create lists.
2. Add each dinner to the AnyList meal-plan calendar on its night, with the recipe linked and sides + thaw reminders in the details.
3. Clear the items you carried over from `planning/needs-this-week.md` (leave anything you couldn't place, and say so).

**Step 7: Write the file**

Write the grocery list to `weekly/[YYYY-MM-DD]/grocery-list.md`, with "Deals expire: [dates]" at the bottom if a deals file was used.

After completing: confirm "Grocery list ready for week of [dates]", and note which store trips are recommended this week and why (estimated savings).
