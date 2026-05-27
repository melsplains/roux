# Sunday Planning Prompt — Full System (AnyList + Claude Code)

Run this every Sunday in Claude Code, with your file folder open.

Before you run it, make sure you've:
1. Updated `inventory/freezer.md` and `inventory/pantry.md`
2. Copied the weekly template and filled in `weekly/YYYY-MM-DD/schedule.md`
3. Updated `planning/needs-this-week.md` with anything from your running list

---

## Files Claude Reads Automatically (no attachment needed)

Claude Code reads these from your folder directly:
- `family/family-preferences.md`
- `family/household-rules.md`
- `inventory/freezer.md`
- `inventory/pantry.md`
- `inventory/fridge.md`
- `weekly/YYYY-MM-DD/schedule.md` ← this week's folder
- `planning/needs-this-week.md`

---

## The Prompt

```
Please create a weekly meal plan for the coming week.

Read the following files before starting:
- family/family-preferences.md
- family/household-rules.md
- inventory/freezer.md
- inventory/pantry.md
- inventory/fridge.md
- weekly/[YYYY-MM-DD]/schedule.md
- planning/needs-this-week.md

---

STEP 1 — Check calendar and weather (optional, do if you can)

If you have access to my calendar or a web search tool:
a) Check my calendar for events this week. Flag any evening events after 4pm as easy-dinner nights.
b) Search "[Your City + State] 7-day weather forecast" and note any days above 85°F where heavy oven use should be avoided.

If you can't access those, use the notes I filled in on schedule.md — I've noted busy nights and weather there.

---

STEP 2 — Browse my AnyList recipes

Use the AnyList integration to browse my recipe library.

Friday is always DIY pizza night — lock it in and skip it for recipe selection.

For the remaining 6 nights:
- Search by protein type (beef, chicken, pork, fish) to see what's available
- Prioritize highly-rated recipes
- Look for meal types that fit my week's schedule (easy nights = slow cooker, sheet pan, minimal prep)
- Get full details on any recipe that looks promising before selecting it

---

STEP 3 — Select meals using these rules

1. Prioritize proteins from the freezer first (see freezer.md for what's available)
2. Assign easy dinners on any evening marked busy or low-energy
3. No red meat two nights in a row — alternate beef/venison with chicken, pork, or fish
4. Every dinner needs a complete plate: a vegetable AND a starch
   - Check if the recipe already includes a starch (pasta, rice, potatoes) — if yes, note "included"
   - Check if the recipe already includes a vegetable — if yes, note "included"
   - If either is missing, assign a simple side from household-rules.md preferences
   - Note the assigned sides — they'll be needed for the grocery list
5. Avoid oven-heavy meals on days above 85°F
6. Choose meals whose ingredients overlap across the week where possible

---

STEP 4 — Assign lunches

7. Prioritize dinner leftovers for lunch the next day
8. Fill remaining days from simple rotation (from family-preferences.md)
9. Check schedule.md for whether child is home for lunch this week — if yes, assign them a simple lunch too

---

STEP 5 — Build the grocery list

10. Read stores/this_week.md if it exists — check for any sales or deals to factor in
11. Read planning/needs-this-week.md — include EVERY item from this list regardless of the meal plan
12. List only what needs to be purchased — skip anything already stocked in inventory files
13. For each item, flag if there's a matching sale or coupon from this week's deals
14. If a second store has a significantly better price on something, note it
15. Group the list by store section
16. Note ingredients shared across multiple meals this week
17. Give an estimated total and flag if approaching budget maximum from household-rules.md

---

STEP 6 — Save the output files

Save these to weekly/[YYYY-MM-DD]/:

**meal-plan.md** — dinner assignments in this format:
> Monday — Meal Name | Sides: [Vegetable] + [Starch]  (or "included" if the recipe covers it)
> Tuesday — Meal Name | Sides: included
> (etc.)

**grocery-list.md** — organized by section with checkboxes:
> - [ ] chicken thighs — 2 lbs
> - [ ] shredded cheese — 1 bag
> (one item per line with quantity)
> Always include all items from planning/needs-this-week.md

---

STEP 7 — Add to AnyList calendar

After presenting the plan, ask: "Approved to add to AnyList?"

Only add events to the AnyList calendar after confirmation.

For each dinner:
1. Add the recipe event to the AnyList calendar for that date
2. If the meal has assigned sides (not included in the recipe), add a note to that day
   e.g., "Sides: Broccoli + Rice" or "Side: Green beans"

---

OUTPUT:

Show me:
- The schedule/weather notes you found (or used from the schedule file)
- Which AnyList recipes you selected and why (with rating if available)
- The full meal plan with sides
- The complete grocery list
```

---

## Quick Version

When you just want the plan with minimal back-and-forth:

```
Read my schedule, inventory, and family files, then search my AnyList recipes
and build this week's meal plan. Prioritize freezer stock, alternate proteins,
easy meals on busy evenings. Assign leftovers-first lunches. Build a grocery
list of only what I need to buy. Save meal-plan.md and grocery-list.md to
weekly/[YYYY-MM-DD]/.
```

---

## Seasonal Note

Update your `household-rules.md` when school ends:
- **School year:** Child is NOT home for lunch on weekdays
- **Summer / school breaks:** Child IS home for lunch — assign a simple lunch, add kid-friendly lunch items to the grocery list
