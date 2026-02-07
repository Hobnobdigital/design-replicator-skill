# 🎨 Design Replicator Skill for Claude

A Claude Skill that replicates website, document, or report designs **exactly** from screenshots, PDFs, images, or mockups. Creates pixel-perfect code that matches the input design 1:1.

## 📦 Installation

### Option 1: Claude Code CLI
```bash
# Install directly from GitHub
/plugin add https://github.com/Hobnobdigital/design-replicator-skill

# Or install to specific agent
npx skills add Hobnobdigital/design-replicator-skill -a claude-code
```

### Option 2: Manual Installation
1. Download this repository
2. Copy the `design-replicator-skill` folder to your Claude Code skills directory:
   ```
   ~/.claude-code/skills/  (macOS/Linux)
   %APPDATA%\Claude\skills\  (Windows)
   ```
3. Restart Claude Code

### Option 3: Claude.ai Web Interface
1. Go to Settings > Capabilities
2. Enable Skills toggle
3. Click "Upload Skill"
4. Select the `design-replicator-skill` folder

## 🎯 What This Skill Does

This skill teaches Claude to:
- ✅ Analyze screenshots, PDFs, images, and mockups
- ✅ Extract exact design specifications (colors, fonts, spacing, layout)
- ✅ Generate pixel-perfect HTML/CSS/React code
- ✅ Match designs 1:1 without generic "AI slop"
- ✅ Handle responsive designs correctly
- ✅ Replicate any website, document, or report layout

## 🚀 Usage

Once installed, Claude will automatically use this skill when you:
- Upload a screenshot or image of a design
- Say "replicate this design"
- Say "clone this website"
- Say "exact replica of this layout"
- Provide a PDF to recreate

### Example Prompts:
```
"Replicate this website design exactly from the screenshot"
"Clone this landing page I uploaded"
"Match this PDF report layout perfectly"
"Recreate this dashboard design 1:1"
"Convert this Figma mockup to React code"
```

## 📋 How It Works

### Step 1: Analysis
Claude examines your input and extracts:
- Typography (fonts, sizes, weights)
- Colors (exact hex codes)
- Spacing (margins, padding, gaps)
- Layout (grid structure, alignment)
- Visual elements (buttons, cards, images)

### Step 2: Specification
Claude documents precise measurements:
```
- Primary Color: #3B82F6
- Heading Font: Georgia, 48px, bold
- Container: max-width 1200px, centered
- Section Padding: 80px vertical
```

### Step 3: Code Generation
Claude generates production-ready code:
- HTML + Tailwind CSS (recommended)
- React + Tailwind CSS (for interactive sites)
- HTML + CSS (for maximum control)

### Step 4: Verification
Claude verifies pixel-perfect matching:
- Colors match exactly
- Fonts are correct
- Spacing is identical
- Layout structure matches

## 🛠️ Supported Output Formats

- **HTML + Tailwind CSS** - Fast, utility-first styling
- **React + Tailwind CSS** - Component-based, interactive
- **Vue + Tailwind CSS** - Progressive framework
- **HTML + CSS** - Traditional, maximum control
- **Bootstrap** - Classic framework
- **Ionic + Tailwind** - Mobile-first
- **SVG** - For graphics and illustrations

## 🎨 Quality Standards

The replicated design will be:
- ✅ Visually indistinguishable from original
- ✅ Pixel-perfect measurements
- ✅ Exact color matches
- ✅ Proper responsive behavior
- ✅ Clean, production-ready code
- ✅ Fully commented with specs

## 📁 Skill Structure

```
design-replicator-skill/
├── SKILL.md          # Main skill instructions
├── README.md         # This file
└── examples/         # Example replications (optional)
```

## 🔄 Comparison with Other Tools

| Tool | Best For | Claude Skill Advantage |
|------|----------|------------------------|
| screenshot-to-code | Quick conversions | Better analysis, exact specs |
| Figma Dev Mode | Figma files | Works with any image/PDF |
| Manual coding | Full control | Automated + precise |
| **This Skill** | **Exact 1:1 replication** | **Pixel-perfect + documented** |

## 📝 Notes

- **Input Quality**: Better input images = better results
- **Complexity**: Simple designs replicate more accurately
- **Assets**: Provide fonts/images when possible for exact matches
- **Responsive**: Skill handles responsive breakpoints automatically

## 🤝 Contributing

Feel free to submit improvements:
- Better analysis techniques
- Additional output formats
- More example prompts
- Enhanced verification methods

## 📄 License

MIT License - Free to use, modify, and distribute

## 🆘 Support

For issues or questions:
1. Check the skill documentation in SKILL.md
2. Create an issue in this repository
3. Refer to Claude's skill documentation

---

**Ready to replicate designs exactly? Install this skill and start cloning!** 🎨
