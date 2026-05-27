# Setup Guide — Simplified Version (Claude.ai)

This gets you running in about 20 minutes. After that, it's 15 minutes every Sunday.

No installation. No command line. Just your browser.

---

## What you need before you start

- A computer, tablet, or phone with a browser
- A Claude.ai account

That's it. If you don't have a Claude.ai account yet, go to claude.ai and sign up. Free accounts work. Read the section below before deciding whether to upgrade.

---

## Free vs. Pro — the honest answer

**Free tier:** Works. You can paste all your files into Claude and get a plan. The limitation is that Claude doesn't "remember" anything between conversations, so every Sunday you re-attach all your files. Annoying but doable.

**Pro tier ($20/month):** Unlocks Projects — a space where you can save files permanently. Your family preferences file lives there forever. Every Sunday you only attach the two files that change week to week (schedule and inventory). Significantly less friction.

My recommendation: Try the free tier once to see if the system works for you. If you're doing this every Sunday, the $20/month is worth it. But start free so you know you'll actually use it before you pay for it.

---

## Step 1 — Fill in your template files

Before you set anything up in Claude, fill in your files.

Open these files from the `simplified/` folder in a text editor (TextEdit on Mac, Notepad on Windows, or any app that opens plain text files):

1. **`01-family-preferences.md`** — This is the important one. Take 10–15 minutes on this. The more specific you are, the better the plan. Replace every placeholder in [brackets] with your real information.

2. **`02-weekly-schedule.md`** — This one you'll fill in fresh every Sunday. For now, just look at the format so you know what you'll be filling in.

3. **`03-inventory.md`** — Fill in what you actually have in your freezer and pantry right now. Don't overthink it — approximate quantities are fine.

**Tips for editing .md files:**

On a Mac: right-click the file → Open With → TextEdit. It will look like plain text with some # symbols and dashes — that's normal. Just type over the placeholders.

On Windows: right-click → Open With → Notepad.

You can also drag the files into a Google Doc, edit them there, and copy the text back. Or open them in any notes app. The # symbols and formatting are just organizational — they don't need to look pretty.

---

## Step 2 — Set up a Claude Project (Pro users only — skip if free)

If you have Claude Pro, setting up a Project means your preferences file stays saved permanently. Worth 5 minutes.

1. Go to claude.ai
2. In the left sidebar, look for **Projects** and click it (or click the + icon)
3. Click **New Project**
4. Name it something like "Meal Planning" or "Sunday Planner"
5. Inside the project, look for an option to **Add files** or **Upload to project**
6. Upload your completed `01-family-preferences.md`

That's it. Every time you start a new chat inside this project, Claude will already have your preferences loaded. You won't need to re-attach it.

**Note:** The Projects interface on claude.ai may look slightly different depending on when you're reading this — Anthropic updates it periodically. If you can't find the upload option, look for "Project Instructions" or "Knowledge" in the project settings.

---

## Step 3 — Your first Sunday run

Here's what to do this Sunday:

**Before opening Claude (5 minutes):**

1. Open `03-inventory.md` and update it. What did you cook this week? Remove it. What's low? Note it.
2. Open `02-weekly-schedule.md` and fill it in fresh for this week. Busy nights, weather, anything to use up.

**In Claude (5 minutes):**

1. Go to claude.ai
2. If you have Pro: open your Meal Planning project, then start a new chat inside it
3. If you're on free: start a new chat
4. Attach your files:
   - Click the paperclip icon (or file attachment button) in the chat bar
   - Attach `02-weekly-schedule.md`
   - Attach `03-inventory.md`
   - If you're on free (no project), also attach `01-family-preferences.md`
5. Open `04-sunday-planning-prompt.md` and copy everything from the "---" line to the end
6. Paste it into the Claude chat
7. Hit send

Wait about 30–60 seconds. Claude will generate your meal plan and grocery list.

---

## Step 4 — Review and use the output

**Reviewing the plan:**

Skim the dinner plan. Does it make sense for your week? If something feels wrong (you know it's your kid's birthday and you want to do something special, or you just don't feel like pasta this week), just say so:

> "Swap Wednesday's dinner for something with pork instead."

Or:

> "Replace Thursday's meal with something that takes under 15 minutes."

Claude will adjust.

**Using the grocery list:**

Copy the grocery list from the chat and:

- Paste it into Apple Notes or Google Keep to use while shopping
- Type the items into your grocery app (AnyList, Instacart, etc.)
- Screenshot it if you shop from your phone

---

## Step 5 — Tell Claude to update your inventory (optional)

After you shop, you can ask Claude to update your inventory file so next Sunday's list stays accurate. Just say:

> "Here's my current inventory file: [paste the file]. I bought everything on this grocery list: [paste the list]. Please give me an updated inventory I can save."

Copy what Claude gives you back and paste it over your old `03-inventory.md` file.

---

## Common Questions

**Can I use this on my phone?**

Yes. The claude.ai app works fine. The files are small enough to manage from your phone, though filling in the templates is easier on a computer.

**What if Claude misses something or makes a weird choice?**

Just tell it. "We're out of pasta sauce, take that off the list" or "Switch Tuesday to an easy night, we have soccer" — Claude will revise. The prompt is a starting point, not a contract.

**What if I don't have all the sections in my inventory?**

That's fine. Fill in what you know. Claude will ask you about anything it needs.

**What about the grocery list format?**

Claude will organize it by store section automatically. If you want a different format, just say so after it generates the list: "Give me the list as a flat plain list with no headers."

**I'm getting a weird response / Claude isn't following my preferences.**

Check that your preferences file is actually attached (or saved in the project). Sometimes a new chat doesn't inherit the project files if you started it wrong. Open the project, click New Chat from inside it, then try again.

---

## That's it

The first Sunday takes a little setup. After that it's attach two files, paste the prompt, done. Most people take the same 15 minutes they were spending staring at the fridge and spend them doing something else.

If something in the kit doesn't work for your family, change it. The templates are placeholders — your version will be better than the default.

---

*Made by Melanie — melaniedunn.work/melsplains*
