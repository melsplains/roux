Remove all ingredients used across this week's dinner plan from inventory.

Read this week's `weekly/[YYYY-MM-DD]/meal-plan.md` and the inventory files.

## Guard — never deduct the same week twice
Get the plan's week dates from line 2 of `meal-plan.md`. Check the dated notes at the top of the inventory files:
- If a "deducted week of [same dates]" note exists → **STOP.** Say: "That week was already deducted on [date] — nothing to do. If a specific meal was missed, use `/recipe-used` or `/inventory-remove`."

## Deduct

1. Ask which dinners actually got cooked (default: all). Skip the ones that weren't.
2. For each cooked dinner, identify ALL ingredients (sides, sauces, oils, seasonings — not just the protein). Pull real ingredient lists from AnyList rather than guessing.
3. Cross-reference against the inventory files and remove/reduce:
   - Gone → remove or mark GONE
   - Partially used (sauce bottle, bag of cheese) → mark LOW or reduce quantity
   - Wasn't in inventory → skip
4. Salt, pepper, basic spices → "assumed in house, not tracked."
5. Add a dated note to each updated inventory file: `Updated YYYY-MM-DD — deducted week of [dates]`

## Report + restock

- Meals processed: [list]
- Significant items removed or depleted: [list]
- Anything that ran out and should be restocked → add it to `planning/needs-this-week.md` and list what you added.
