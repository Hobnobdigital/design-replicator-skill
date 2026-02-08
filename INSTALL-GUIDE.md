# 📖 Installation Guide — Design Replicator Skill v2.0

Two ways to use this skill: **Claude Code CLI** or **Claude.ai Web**. Pick the one you use.

---

## Option 1: Claude Code CLI (Terminal)

### What You Need
- Claude Code CLI installed (`npm install -g @anthropic-ai/claude-code`)
- A terminal/command line

### Step-by-Step

**Step 1: Create the skills directory (if it doesn't exist)**
```bash
mkdir -p ~/.claude/skills
```

**Step 2: Clone this repo into the skills folder**
```bash
git clone https://github.com/Hobnobdigital/design-replicator-skill.git ~/.claude/skills/design-replicator
```

**Step 3: Verify it's installed**
```bash
ls ~/.claude/skills/design-replicator/SKILL.md
```
You should see the file path printed. If so, it's installed.

**Step 4: Use it!**

Open Claude Code in any project:
```bash
claude
```

Then type your request. Claude Code automatically detects the skill when you mention design replication. Examples:

```
> Replicate this design as an editable PowerPoint
> (drag and drop or paste image path)

> Convert this screenshot to pixel-perfect HTML/CSS
> /path/to/screenshot.png

> Recreate this flyer as a PDF with exact same layout
> Here's the image: /path/to/flyer.jpg
```

### How Claude Code Finds the Skill

Claude Code scans `~/.claude/skills/` on startup. It reads the `description` field in SKILL.md's frontmatter to decide when to use it. You don't need to tell it to "use the design replicator skill" — it automatically activates when your request matches.

**Trigger phrases that activate the skill:**
- "replicate this design"
- "copy this layout"
- "recreate this document"
- "convert to editable"
- "match this exactly"
- "screenshot to code"
- "design to document"
- "pixel-perfect copy"
- Any request to reproduce a visual design

### Updating the Skill Later

```bash
cd ~/.claude/skills/design-replicator
git pull
```

---

## Option 2: Claude.ai Web (Browser)

### What You Need
- A Claude.ai account (free or paid) at https://claude.ai
- The file `DESIGN-REPLICATOR-STANDALONE.md` from this repo

### Step-by-Step

**Step 1: Download the standalone file**

Go to: https://github.com/Hobnobdigital/design-replicator-skill/blob/master/DESIGN-REPLICATOR-STANDALONE.md

Click the **Download** button (or "Raw" → Save As).

Or from terminal:
```bash
curl -O https://raw.githubusercontent.com/Hobnobdigital/design-replicator-skill/master/DESIGN-REPLICATOR-STANDALONE.md
```

**Step 2: Open Claude.ai**

Go to https://claude.ai and start a **new chat**.

**Step 3: Upload the skill file**

Click the **paperclip icon** (📎) at the bottom of the chat box, or drag and drop the file into the chat.

Upload: `DESIGN-REPLICATOR-STANDALONE.md`

**Step 4: Upload your source design**

In the SAME chat, also upload the image/screenshot of the design you want replicated.

You can upload both files at once or one at a time.

**Step 5: Write your prompt**

Example prompts:

```
I've uploaded the Design Replicator skill and a flyer design. 
Replicate this flyer as pixel-perfect HTML/CSS with exact same 
text placement, fonts, colors, and layout.
```

```
Using the Design Replicator skill, convert this website screenshot 
into an editable PowerPoint presentation. All text should be in 
editable text boxes positioned exactly where they appear in the original.
```

```
Replicate this brochure design as a PDF. Match the fonts, colors, 
spacing, and layout exactly. Use the Design Replicator instructions 
I uploaded.
```

### Important Notes for Claude.ai Web

1. **Upload BOTH files in the SAME chat** — the skill file AND your design image
2. **Use `DESIGN-REPLICATOR-STANDALONE.md`** — NOT `SKILL.md` (the standalone version is self-contained with all references included)
3. **Mention the skill in your prompt** — say "using the Design Replicator skill" or "follow the replication instructions I uploaded"
4. **Specify your desired output format** — "as HTML/CSS", "as PDF", or "as editable PowerPoint"
5. **You need to re-upload the skill file for each new chat** — it doesn't persist between conversations

### Making It a Project (Persistent)

If you want the skill always available without re-uploading:

1. Go to https://claude.ai
2. Click **Projects** in the sidebar
3. Create a new project (e.g., "Design Replicator")
4. Click **Project knowledge** → Upload `DESIGN-REPLICATOR-STANDALONE.md`
5. Now every chat in that project has the skill loaded automatically!

---

## Which Files Go Where — Quick Reference

| File | Purpose | Where It Goes |
|------|---------|---------------|
| `SKILL.md` | Main skill with YAML frontmatter | Claude Code CLI (`~/.claude/skills/design-replicator/`) |
| `DESIGN-REPLICATOR-STANDALONE.md` | Self-contained skill (no YAML) | Claude.ai web (upload as attachment) |
| `references/font-matching.md` | Font identification guide | Auto-loaded by Claude Code when needed |
| `references/pptx-coordinates.md` | PowerPoint coordinate reference | Auto-loaded by Claude Code when needed |
| `README.md` | Documentation | For you — not uploaded anywhere |
| `INSTALL-GUIDE.md` | This file | For you — not uploaded anywhere |

### Why Two Different Files?

- **`SKILL.md`** has YAML frontmatter (`---name: ...---`) that Claude Code uses for auto-discovery. It also references the `references/` folder for additional context. This is designed for the Claude Code plugin system.

- **`DESIGN-REPLICATOR-STANDALONE.md`** is a single self-contained file with ALL instructions and references baked in. No YAML frontmatter, no external references. This is designed for upload to Claude.ai web where you can't reference other files.

---

## Troubleshooting

### Claude Code doesn't detect the skill
- Make sure `SKILL.md` is at `~/.claude/skills/design-replicator/SKILL.md`
- Restart Claude Code (`claude` command)
- Try explicitly: "Use the design replicator skill to..."

### Claude.ai web doesn't follow the instructions
- Make sure you uploaded `DESIGN-REPLICATOR-STANDALONE.md` (not `SKILL.md`)
- Reference the skill in your prompt: "Follow the Design Replicator instructions I uploaded"
- Try a Claude Pro/Team plan for better instruction following

### Output doesn't match the source
- Ask Claude to "run visual QA and compare with the original"
- Specify: "iterate until the visual match is at least 95%"
- Provide a higher resolution source image

---

**Questions?** Open an issue at https://github.com/Hobnobdigital/design-replicator-skill/issues
