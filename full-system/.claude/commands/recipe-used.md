Remove all ingredients used in one specific recipe from inventory.

Read the inventory files (`inventory/freezer.md`, `inventory/pantry.md`, `inventory/fridge.md`).

The user will name a recipe, e.g.: `/recipe-used Chicken Parmesan`

Instructions:
1. Pull the recipe's real ingredient list from AnyList if it lives there; otherwise list every ingredient it typically requires (be thorough — oils, spices, pantry items, not just the main protein)
2. For each ingredient, check the inventory files
3. Remove or reduce quantities accordingly:
   - Full recipe portion used = remove or mark LOW
   - Shared ingredient (a bottle of oil, a bag of cheese) = mark as partially used or LOW
   - Items not in inventory = note them as "not found in inventory"
4. Salt, pepper, basic spices — note as "assumed in house, not tracked"

After updating, confirm:
- Ingredients removed/reduced: [list]
- Ingredients not found in inventory (may need to check): [list]
- Assumed pantry staples not tracked: [list]
