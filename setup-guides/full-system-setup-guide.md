# Setup Guide — Full System (AnyList + Claude Code)

This is the more involved version. The setup takes 30–60 minutes the first time. After that, it's 15 minutes every Sunday.

What you get for that setup time: Claude browses your actual AnyList recipe library, picks meals based on your freezer and your week, and pushes the plan directly into AnyList's calendar with the actual recipes attached. For me, that part felt like magic the first time it worked.

If you've never installed an app from a terminal command before, don't skip this guide — I've written it for you.

---

## What You Need

1. **AnyList** — the recipe app this system is built around
2. **Claude Code** — Anthropic's AI tool that runs locally on your computer
3. **The AnyList MCP** — the connector between Claude and AnyList (more on this below)
4. About 45 minutes the first time, most of which is downloading and waiting

---

## Part 1 — Get AnyList Set Up

If you already use AnyList and have a paid subscription, skip to Part 2.

**Download AnyList:**
- iPhone/iPad: search "AnyList" in the App Store
- Android: search "AnyList" in the Google Play Store
- It's free to download

**Do you need the paid subscription?**

The free version lets you store recipes and use basic lists. The paid subscription unlocks features that make this system actually work — specifically, the ability to access your full recipe library via the integration we're setting up. I use it and it's worth it.

**Set up your recipe library:**

If you have existing recipes in AnyList, great. If you're starting fresh, spend 20–30 minutes adding your family's usual meals. The system works better the more recipes you have in there. You can import recipes from websites by sharing the URL into AnyList — it pulls in ingredients automatically.

---

## Part 2 — Install Claude Code

Claude Code is the tool that runs on your computer and connects to your files and apps. You're going to install it, and then you're going to feel like you did something technical and impressive. You did.

**Pick the installation method that fits how you work:**

---

### Option A — Claude Code Desktop App (easiest, recommended if you're new to this)

This is a standalone app you download and install like any other program. No command line involved.

1. Go to **claude.ai/download** (or search "Claude Code desktop app")
2. Download the version for your computer (Mac or Windows)
3. Open the downloaded file and follow the installer
4. Sign in with your Claude account

Once it's open, you have a chat-style interface but it can also see your files, run things locally, and connect to apps like AnyList. This is how you'll run the planning prompt each Sunday.

---

### Option B — VS Code Extension (if you already use VS Code)

VS Code is a code editor a lot of developers use, but it's also just a really good text editor for keeping files organized. If you already have it installed:

1. Open VS Code
2. Click the Extensions icon in the left sidebar (it looks like four small squares)
3. Search for **"Claude"** or **"Anthropic Claude"**
4. Install the Claude Code extension
5. Sign in when prompted

The extension adds a Claude panel to VS Code where you can chat, and it has access to whatever folder you have open. Open your MealPlanning folder in VS Code, and Claude can see all your files.

---

### Option C — Terminal / Command Line (for the curious or technically comfortable)

If you're comfortable opening Terminal on Mac (or Command Prompt / PowerShell on Windows), this is the direct installation method.

**On Mac:**

1. Open **Terminal** (search for it in Spotlight — the magnifying glass in the top right of your screen, or look in Applications → Utilities)
2. You'll see a black or white window with a blinking cursor. That's normal.
3. Type (or copy and paste) this command, then press Enter:

```
npm install -g @anthropic-ai/claude-code
```

4. Wait for it to finish. You'll see a lot of text scrolling — that's it installing. Normal.
5. When it's done, type:

```
claude
```

And press Enter. Claude will start up and ask you to sign in.

**If you get a "command not found" error for npm:**

You need to install Node.js first. Go to nodejs.org, download the installer for your system, run it, then come back and try the command above again.

**On Windows:**

Same process, but open PowerShell instead of Terminal. Search for "PowerShell" in the Start menu.

---

## Part 3 — Set Up the AnyList MCP

MCP stands for "Model Context Protocol." The short version: it's how Claude Code connects to external apps like AnyList. You set it up once and then Claude can browse your recipes automatically every Sunday.

This is the most technical part. Take it one step at a time.

**Step 1 — Find your Claude Code settings file**

Claude Code has a settings file where you register the apps it can connect to.

- On Mac: the file is at `~/.claude/settings.json`
  - To find it: open Finder, press `Command + Shift + G`, type `~/.claude/`, press Go
- On Windows: the file is at `%APPDATA%\Claude\settings.json`
  - To find it: open File Explorer and type `%APPDATA%\Claude\` in the address bar

If the file doesn't exist yet, Claude Code will create it the first time you run it.

**Step 2 — Get the AnyList MCP**

The AnyList MCP is a connector package. To get it, you'll run one terminal command:

```
npm install -g anylist-mcp
```

(Same process as installing Claude Code — open Terminal or PowerShell, paste this, hit Enter, wait.)

**Step 3 — Register it in Claude Code settings**

Open the settings.json file in a text editor. You're going to add a section that tells Claude Code about the AnyList connection.

Add this inside the file (if the file already has content, add it inside the existing structure — the MCP setup guide that comes with Claude Code explains the exact placement):

```json
{
  "mcpServers": {
    "anylist": {
      "command": "anylist-mcp",
      "env": {
        "ANYLIST_EMAIL": "your-anylist-email@example.com",
        "ANYLIST_PASSWORD": "your-anylist-password"
      }
    }
  }
}
```

Replace the email and password with your actual AnyList login credentials.

**Step 4 — Test it**

Open Claude Code and type:

> "Use AnyList to show me a few of my saved recipes."

If Claude comes back with actual recipes from your library, it's connected. If it says it can't find AnyList or returns an error, check that the MCP is installed and the settings file has no typos (missing commas and brackets are the most common issues).

---

## Part 4 — Set Up Your MealPlanning Folder

**Download and organize your files:**

1. Move the `full-system/` folder from this kit to wherever you keep documents
2. Rename the folder `MealPlanning` (or whatever you want)
3. Note the full path — you'll use it to tell Claude Code where your files are
   - Example on Mac: `/Users/[your-username]/Documents/MealPlanning/`
   - Example on Windows: `C:\Users\[your-username]\Documents\MealPlanning\`

**Fill in your templates:**

Fill in these files before your first planning session:
- `family/family-preferences.md` — who eats what, favorite meals, hard nos
- `family/household-rules.md` — protein rules, budget, fixed nights
- `family/camping-mode.md` — optional; how planning changes on camping weeks (delete it if you don't camp)
- `inventory/freezer.md` — what's actually in your freezer
- `inventory/pantry.md` — what's in your pantry
- `inventory/fridge.md` — what's in your fridge

---

## Part 5 — Your First Sunday Run

**Before opening Claude Code (5 minutes):**

1. Update your inventory files — what did you use this week?
2. Create a new weekly folder: duplicate the `weekly/template/` folder and name it with this week's date (`YYYY-MM-DD`, e.g., `2026-04-27`)
3. Open `weekly/2026-04-27/schedule.md` and fill it in — busy nights, weather, anything to use up, child home for lunch?
4. Update `planning/needs-this-week.md` with anything you noticed throughout the week

**In Claude Code:**

1. Open Claude Code with your MealPlanning folder
2. Open `full-system/prompts/sunday-planning-prompt.md`
3. Copy the prompt and paste it into Claude Code
4. Update the date reference (`[YYYY-MM-DD]`) to this week's date before sending
5. Hit send

Claude will check your files, search your AnyList recipes, build the week, and come back with a plan. It will ask before pushing anything to your AnyList calendar — you get to review the plan first.

---

## Common Questions

**I don't have AnyList — can I still use the full system?**

The full system is designed around AnyList. Without it, Claude can't browse your actual recipe library — it would just work from descriptions, which is essentially what the simplified version does. If you don't use AnyList, start with the simplified version.

**What's the difference between the desktop app and the terminal?**

Same Claude Code, different interface. The desktop app has a visual window. The terminal is text-based. Both work identically for this system. Use whichever feels more comfortable.

**My settings.json file has an error and Claude won't start.**

JSON files are picky about formatting — a missing comma or bracket breaks the whole thing. Copy your settings.json content and paste it into jsonlint.com. It'll tell you exactly where the error is.

**Claude can see my files but can't connect to AnyList.**

Check two things: (1) the MCP is installed (run `anylist-mcp --version` in Terminal — you should see a version number), and (2) the settings.json has the correct email and password with no typos.

**It worked but the plan doesn't look right.**

Tell Claude what to change. "Switch Wednesday to a pork dish" or "Remove Thursday's salmon — I don't have any left" — just say it in plain English. The prompt is a starting point, not a final answer.

---

## That's the whole setup

If you got through Part 3 without panicking, give yourself credit. The MCP setup is genuinely the hardest part and you only do it once. After that, it's update a few files and paste the prompt. Every Sunday.

---

*Made by Melanie — melaniedunn.work/melsplains*
