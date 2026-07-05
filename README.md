# Roux by Melsplains

**A weekly meal planning kit that runs in Claude.ai.**

Set it up once. Use it every Sunday. Get a full week of dinners and a grocery list that fits your family, your schedule, and what's already in your freezer.

> **New here? Start with the Claude.ai version.**
> No AnyList. No Claude Code. No installation. No technical knowledge required.
> Just a browser and a free Claude.ai account.

---

## What you get every Sunday

- 7 nights of dinners matched to your actual week (busy Tuesday = easy crockpot meal)
- Lunch plan — leftovers first, then simple options
- Grocery list organized by store section
- Thaw reminders so you don't forget to pull the chicken at 9pm

---

## Two versions included

### Claude.ai Version — Start here

Works in a browser. No extra apps, no installation, no command line. You fill in a few files about your family, attach them to Claude, paste the prompt. That's the whole thing.

**What you need:** A free Claude.ai account. That's it.

**What you do NOT need:** AnyList · Claude Code · any installation · any technical knowledge · a paid subscription (Claude Pro helps but isn't required to try)

**Your files:** Everything in the `simplified/` folder.

**Time:** About 20 minutes the first time (mostly writing down what your family likes, which you've never put on paper before). 15 minutes every Sunday after that.

---

### Advanced — Claude Code + AnyList

Claude browses your actual AnyList recipe library, builds the week, and pushes the plan directly into your AnyList calendar with real recipes attached. Requires some setup (Claude Code + AnyList MCP), but once it's running your whole Sunday is three slash commands: `/deals` → `/plan` → `/shop`. The commands ship in the kit (`full-system/.claude/commands/`), along with the `CLAUDE.md` that turns Claude into Roux.

**What you need:** AnyList subscription + Claude Code installed on your computer.

**Your files:** Everything in the `full-system/` folder.

**Time:** 30–60 minutes to set up the first time. 15 minutes every Sunday after that.

---

## How to get started (Claude.ai version)

### Step 1 — Download the kit

Click the green **Code** button above → **Download ZIP** → unzip anywhere.

Or clone: `git clone https://github.com/melsplains/roux.git`

### Step 2 — Open your setup guide

Go to `setup-guides/simplified-setup-guide.md`. It walks you through every step.

For the Advanced version: `setup-guides/full-system-setup-guide.md`.

### Step 3 — Fill in your files

Open the templates and fill in the brackets. Your family, your rules, your meals.

| File | What it is | When you update it |
|------|-----------|-------------------|
| `01-family-preferences.md` | Who eats what, hard nos, protein rules, your meal rotation | Once |
| `02-weekly-schedule.md` | This week: busy nights, weather, freezer items to use | Every Sunday (~3 min) |
| `03-inventory.md` | What's in the freezer and pantry | As you cook; every Sunday |
| `04-sunday-planning-prompt.md` | The prompt you paste into Claude | Every Sunday |

### Step 4 — Run it

Attach your files to Claude.ai and paste the planning prompt. Get back a full week plan and grocery list. Adjust anything. Done.

---

## About the setup time

The first setup takes longer than 20 minutes on paper — not because the tool is complicated, but because you're writing down things that have lived in your head: your family's food rules, the meals everyone actually likes, which nights are impossible. Most people find that part surprisingly useful on its own.

After the first week: 15 minutes. Every Sunday. That's the whole point.

---

## More from Melsplains

Melsplains is a content brand for working moms who want practical help with AI, marketing, and family systems — explained without condescension.

- Download page + more context: [melaniedunn.work/melsplains-meal-planning-kit](https://www.melaniedunn.work/melsplains-meal-planning-kit)
- More free tools: [melaniedunn.work/melsplains/tools](https://www.melaniedunn.work/melsplains/tools)
- Instagram: [@melsplains](https://www.instagram.com/melsplains)

Questions or feedback? Open an issue — I update this kit when I find better ways to do it.
