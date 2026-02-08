# 🎨 Design Replicator Skill

**Pixel-perfect 1:1 design replication for Claude Code & Claude.ai**

Converts any document design, website layout, flyer, brochure, or presentation from an image/screenshot into an editable format with exact text placement, font matching, image positioning, and layout structure.

---

## ✨ What It Does

| Input | Output | Method |
|-------|--------|--------|
| Screenshot/image of any design | **HTML/CSS** | Absolute positioning, exact coordinates |
| Screenshot/image of any design | **PDF** | HTML → Puppeteer → pixel-perfect PDF |
| Screenshot/image of any design | **Editable PowerPoint (.pptx)** | PptxGenJS with exact placement |

### Key Features

- ✅ **Exact text placement** — position, size, weight, color, alignment
- ✅ **Font matching** — identifies and maps to closest Google Font or system font
- ✅ **Image positioning** — exact coordinates and dimensions preserved
- ✅ **Color matching** — hex values sampled from source design
- ✅ **Layout structure** — grids, columns, spacing replicated exactly
- ✅ **Decorative elements** — borders, shadows, gradients, icons, rounded corners
- ✅ **Editable output** — text boxes in PPTX, HTML elements in web, form fields in PDF
- ✅ **Visual QA loop** — automated comparison with source to ensure ≥95% match

---

## 📁 Repository Structure

```
design-replicator-skill/
├── SKILL.md                          ← Main skill file (for Claude Code)
├── DESIGN-REPLICATOR-STANDALONE.md   ← Standalone version (upload to Claude.ai)
├── README.md                         ← This file
└── references/
    ├── font-matching.md              ← Font identification & Google Fonts mapping
    └── pptx-coordinates.md           ← PowerPoint coordinate system reference
```

---

## 🚀 Installation

### For Claude Code CLI

```bash
# Clone this repo into your Claude Code skills directory
git clone https://github.com/Hobnobdigital/design-replicator-skill.git ~/.claude/skills/design-replicator
```

Then just ask Claude Code:
> *"Replicate this design as an editable PowerPoint"*

Claude Code will automatically detect and use the skill.

### For Claude.ai (Web)

1. Go to [claude.ai](https://claude.ai)
2. Start a new chat
3. Click **Add content** (paperclip icon)
4. Upload `DESIGN-REPLICATOR-STANDALONE.md`
5. Upload your source design image
6. Ask: *"Replicate this design exactly as [HTML/PDF/PPTX]"*

### For Claude Code Plugins

```
/plugin install design-replicator
```

---

## 🔄 How It Works

```
1. You provide → Image/screenshot/PDF of a design
2. Claude analyzes → Layout, fonts, colors, positions, spacing
3. Claude generates → HTML/CSS or PPTX with exact coordinates
4. Visual QA → Screenshots output, compares with source
5. Iterate → Fixes differences until ≥95% visual match
```

### The Replication Pipeline

| Step | What Happens | Tools Used |
|------|-------------|------------|
| **1. Analyze** | Vision extracts layout, fonts, colors, positions | Claude Vision |
| **2. Extract** | OCR gets precise text bounding boxes | Tesseract OCR |
| **3. Match Fonts** | Identifies closest Google Font or system font | Font reference DB |
| **4. Generate** | Creates output with exact coordinates | PptxGenJS, Puppeteer, ReportLab |
| **5. QA** | Screenshots output, compares side-by-side | Puppeteer, LibreOffice |
| **6. Iterate** | Fixes position/size/color differences | 3-5 rounds typical |

---

## 📋 Supported Document Types

| Document Type | Best Output | Notes |
|--------------|-------------|-------|
| Flyer / Poster | HTML → PDF | Single page, absolute positioning |
| Brochure | HTML → PDF | Multi-page with @page rules |
| Presentation | PPTX | Fully editable slide deck |
| Website / Landing Page | HTML/CSS | Responsive with Grid/Flexbox |
| Business Card | HTML → PDF | High-DPI (3x scale) |
| Social Media Post | HTML → PNG | Puppeteer screenshot |
| Resume / CV | HTML → PDF | Clean typography focus |
| Menu / Price List | HTML → PDF | Table/grid structure |
| Certificate / Award | HTML → PDF | Decorative elements |

---

## 🔧 Dependencies

### Node.js
```bash
npm install puppeteer pptxgenjs
```

### Python
```bash
pip install pytesseract opencv-python reportlab Pillow pdfplumber
```

### System
```bash
# Tesseract OCR
sudo apt install tesseract-ocr        # Ubuntu/Debian
brew install tesseract                  # macOS

# LibreOffice (for PPTX → PDF conversion)
sudo apt install libreoffice-impress   # Ubuntu/Debian

# Poppler (for PDF → images)
sudo apt install poppler-utils         # Ubuntu/Debian
brew install poppler                    # macOS
```

---

## 💡 Tips for Best Results

1. **Provide high-resolution source images** — higher res = better analysis
2. **Specify the output format** — "as editable PPTX" or "as HTML/CSS"
3. **Mention specific requirements** — "all text must be editable" or "match fonts exactly"
4. **Include multiple views** if the design has multiple pages/slides
5. **Font matching is 80% of the battle** — nail the font and everything looks closer

---

## 📄 License

MIT License — free for personal and commercial use.

---

## 🤝 Contributing

1. Fork this repository
2. Create a feature branch
3. Add improvements to SKILL.md or references
4. Submit a pull request

---

**Built for designers, marketers, and anyone who needs pixel-perfect document replication.**

Created by **Kwame Sarkodee-Adoo** | [Hobnob Digital](https://github.com/Hobnobdigital)
