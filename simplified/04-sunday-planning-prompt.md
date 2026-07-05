# The Sunday Planning Prompt

## How to use this every Sunday

1. Update your inventory file (`03-inventory.md`) — the lazy way: use the Reset Prompt at the bottom of this file and let Claude do it with you
2. Fill in this week's schedule (`02-weekly-schedule.md`) — busy nights, weather, anything to use up
3. Open Claude.ai and go to your Meal Planning project (or start a new chat if you don't have a project set up yet)
4. Attach these two files to the chat:
   - `02-weekly-schedule.md` (you just filled this in)
   - `03-inventory.md` (you just updated this)
5. If your family preferences file is NOT saved in a Claude Project, also attach `01-family-preferences.md`
6. Copy and paste the prompt below — everything from the line that says "---" to the end

Hit send. That's it.

---

## What comes back

Claude will show you:
- A day-by-day dinner plan (meal + sides)
- Weekday lunches
- A grocery list organized by store section, with checkboxes

Review it. Swap anything that doesn't feel right. Copy the grocery list to your phone or type it into your grocery app.

---

## The Prompt

*(Copy everything below this line and paste it into Claude)*

---

Please create my weekly meal plan for the coming week.

I've attached:
- My weekly schedule — busy nights, effort levels, anything I need to use up
- My current inventory — what's in the freezer and pantry right now
- [My family preferences — who we are, what we like, our usual meal rotation] ← delete this line if your preferences file is already saved in your Claude Project

---

**STEP 1 — Plan dinners for all 7 nights**

Using my family preferences and this week's schedule:

- Match meal effort to each night — easy meals on busy nights, normal or weekend effort when we have more time
- Prioritize proteins I already have in the freezer before adding meat to the grocery list
- No red meat two nights in a row — alternate beef or lamb with chicken, pork, or fish
- Every dinner needs a complete plate: protein + vegetable + starch
  - If the meal already includes a vegetable (like a stir fry), note it — don't add a redundant side
  - If the meal already includes a starch (like pasta or potatoes), same thing
  - If either is missing, assign a simple side from my family's usual sides
- Honor any fixed nights I have (like pizza night on Fridays) unless my schedule notes otherwise
- If I flagged any nights as hot weather, avoid heavy oven meals those nights
- If I listed anything to use up from the freezer or fridge, work that in

**STEP 2 — Assign lunches for the week**

- Plan weekday lunches for me based on my preferences file
- Leftovers from the previous night's dinner first
- Fill remaining days from my simple rotation
- If my schedule says my child is home for lunch any days this week, plan a simple lunch for them too

**STEP 3 — Build the grocery list**

- List only what I actually need to buy — skip anything I've marked as stocked in my inventory
- BUT err on the side of inclusion: if you're not certain something is stocked, put it on the list. Crossing an item off in the store is easy — a second trip is not.
- Include everything from my "board list" in the schedule file, even if it's not related to a meal
- Walk through the "Staples & Snacks to Keep Stocked" list in my preferences file, item by item — anything not clearly stocked goes on the list. A meal plan is not a grocery list; the staples are what get forgotten.
- Group by store section with checkboxes:
  - Produce
  - Meat & Protein (only if not in freezer)
  - Dairy & Eggs
  - Pantry & Dry Goods
  - Bread, Wraps & Crackers
  - Frozen (non-protein)
  - Snacks & Drinks
  - Household
- Note any ingredients used across multiple meals this week (helps me shop smarter)
- Give me a rough estimated total at the bottom

---

**OUTPUT FORMAT:**

Show me three things:

**1. Dinner Plan**
For each day:
> Monday — [Meal Name] | Sides: [Vegetable] + [Starch] (or "included in dish")
> *One-line note if relevant: why you picked it, if it uses freezer stock, etc.*

**2. Lunches**
A simple list — just the meal and whose it is. Doesn't need to be elaborate.

**3. Grocery List**
Organized by section with checkboxes. One item per line:
> - [ ] item name — quantity
> *(coupon or sale note if I mentioned one in my schedule)*

Total estimate at the bottom.

---

## Bonus: The Reset Prompt (updates your inventory for you)

Updating the inventory file by hand is the step everyone skips — and then the whole system drifts. Instead, before your Sunday planning session, attach `03-inventory.md` and last week's meal plan, then paste this:

---

Help me reset my inventory from last week.

I've attached my inventory file and last week's meal plan.

1. Ask me which of last week's dinners actually got cooked (assume all of them unless I say otherwise)
2. For each cooked meal, remove or mark LOW everything it used — sides, sauces, and oils too, not just the meat
3. Then ask me to paste my grocery receipt, and add those items to the right sections
4. Give me back the complete updated inventory file so I can paste it over my old one, with today's date at the top

---

Two minutes, and your inventory is honest again.
