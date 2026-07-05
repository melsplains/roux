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

Once it's open, you have a chat-style interface but it can also see your files, run things locally, and connect to apps like AnyList. This is how you'll run the planning commands each Sunday.

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

## Part 3 — Set Up Your MealPlanning Folder

**Download and organize your files:**

1. Move the `full-system/` folder from this kit to wherever you keep documents
2. Rename the folder `MealPlanning` (or whatever you want)
3. Note the full path — you'll use it to tell Claude Code where your files are
   - Example on Mac: `/Users/[your-username]/Documents/MealPlanning/`
   - Example on Windows: `C:\Users\[your-username]\Documents\MealPlanning\`

**What's already in the folder (don't delete these):**

- `CLAUDE.md` — the instructions Claude reads automatically every time you open this folder. This is what turns generic Claude into Roux.
- `.claude/commands/` — the slash commands: `/deals`, `/plan`, `/shop`, and the inventory helpers. The folder name starts with a dot, so your computer may hide it — it's there. (Mac: press `Command + Shift + .` in Finder to show hidden files.)

**Fill in your templates:**

Fill in these files before your first planning session:
- `family/family-preferences.md` — who eats what, favorite meals, hard nos
- `family/household-rules.md` — protein rules, budget, fixed nights
- `family/camping-mode.md` — optional; how planning changes on camping weeks (delete it if you don't camp)
- `inventory/freezer.md` — what's actually in your freezer
- `inventory/pantry.md` — what's in your pantry
- `inventory/fridge.md` — what's in your fridge

---

## Part 4 — Connect AnyList (the MCP)

MCP stands for "Model Context Protocol." The short version: it's how Claude Code connects to external apps like AnyList. You set it up once and then Claude can browse your recipes automatically every Sunday.

This is the most technical part. Take it one step at a time.

**Step 1 — Get the AnyList MCP**

The AnyList MCP is a connector package. To get it, you'll run one terminal command:

```
npm install -g anylist-mcp
```

(Same process as installing Claude Code — open Terminal or PowerShell, paste this, hit Enter, wait.)

**Step 2 — Tell Claude Code about it**

Create a file named exactly `.mcp.json` (note the dot at the start) inside your MealPlanning folder, with this content:

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

Because the file lives in the folder, the connection comes along automatically whenever Claude Code is opened there — no global settings to hunt down. The first time you open the folder, Claude Code will ask whether to trust this MCP server; approve it.

**Step 3 — Test it**

Open Claude Code in your MealPlanning folder and type:

> "Use AnyList to show me a few of my saved recipes."

If Claude comes back with actual recipes from your library, it's connected. If it says it can't find AnyList or returns an error, check that the MCP is installed and the `.mcp.json` file has no typos (missing commas and brackets are the most common issues).

---

## Part 5 — Your First Sunday Run

Open Claude Code in your MealPlanning folder and run three commands. Type each one (with the slash) and follow the conversation:

1. **`/deals`** — drop screenshots of this week's deals from your store apps (or paste them). Claude writes them to a deals file the planner reads.
2. **`/plan`** — Claude reconciles last week (what got cooked, your receipts), asks about your calendar, checks the weather, browses your AnyList recipes, and builds the week.
3. **`/shop`** — Claude builds the grocery list from the plan + your staples + your needs list, and (after you approve) pushes everything to your AnyList lists and calendar.

That's the whole Sunday. `/plan` handles last week's inventory cleanup automatically, so you don't need to prep anything — just have your receipts nearby.

**Between Sundays:** when something runs low, tell Claude `/needs-add we're out of ranch` — it goes on the running list and shows up on the next grocery list.

**Prefer one big prompt instead of commands?** The original all-in-one version still lives at `prompts/sunday-planning-prompt.md` — copy, fill in the date, paste. Same result, more scrolling.

---

## Common Questions

**I don't have AnyList — can I still use the full system?**

The full system is designed around AnyList. Without it, Claude can't browse your actual recipe library — it would just work from descriptions, which is essentially what the simplified version does. If you don't use AnyList, start with the simplified version.

**What's the difference between the desktop app and the terminal?**

Same Claude Code, different interface. The desktop app has a visual window. The terminal is text-based. Both work identically for this system. Use whichever feels more comfortable.

**I'm using a different AI tool (OpenAI Codex, Cursor, etc.) — does this still work?**

Mostly, yes — the files are just markdown. Three renames:
1. Copy `CLAUDE.md` to `AGENTS.md` — that's the filename most other tools (including Codex) read automatically.
2. The slash commands: in Codex, copy the files from `.claude/commands/` into `~/.codex/prompts/` and they become `/plan`, `/shop`, etc. there too. In tools without custom commands, open the command file and paste its contents as your prompt.
3. The AnyList connection: `.mcp.json` is Claude Code's format. Codex configures MCP servers in `~/.codex/config.toml` instead — check your tool's MCP docs and reuse the same command + email/password values.

**My .mcp.json file has an error and the connection won't work.**

JSON files are picky about formatting — a missing comma or bracket breaks the whole thing. Copy your `.mcp.json` content and paste it into jsonlint.com. It'll tell you exactly where the error is.

**Claude can see my files but can't connect to AnyList.**

Check three things: (1) the MCP is installed (run `anylist-mcp --version` in Terminal — you should see a version number), (2) the `.mcp.json` file is inside your MealPlanning folder and has the correct email and password with no typos, and (3) you approved the MCP when Claude Code asked about it (run `/mcp` inside Claude Code to check its status).

**Typing /plan does nothing / Claude doesn't know the command.**

The commands live in the `.claude/commands/` folder inside your MealPlanning folder. Two usual causes: Claude Code was opened in a different folder (open it in MealPlanning itself), or the hidden `.claude` folder didn't come along when you moved things (re-copy it from the kit — Mac hides dot-folders by default; press `Command + Shift + .` in Finder to see them).

**It worked but the plan doesn't look right.**

Tell Claude what to change. "Switch Wednesday to a pork dish" or "Remove Thursday's salmon — I don't have any left" — just say it in plain English. The plan is a starting point, not a final answer.

---

## That's the whole setup

If you got through Part 4 without panicking, give yourself credit. The MCP setup is genuinely the hardest part and you only do it once. After that, it's three slash commands. Every Sunday.

---

*Made by Melanie — melaniedunn.work/melsplains*
