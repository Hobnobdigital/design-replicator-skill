# 🎨 Design Replicator Skill v2.0 (LATEST - February 2026)

> ⚡ **THIS IS THE LATEST VERSION** — Created Feb 8, 2026
> 
> Previous versions: `design-to-document-skill`, `editable-design-replicator`
> 
> **What's new in v2.0:** Complete rewrite with font matching database, PowerPoint coordinate system, OCR-assisted layout extraction, visual QA loop, and multi-format output (HTML/CSS, PDF, PPTX).

---

**Pixel-perfect 1:1 design replication for Claude Code & Claude.ai**

Converts any document design, website layout, flyer, brochure, or presentation from an image/screenshot into an editable format with exact text placement, font matching, image positioning, and layout structure.

---

## 📦 Which File Goes Where?

| Platform | File to Use | How to Install |
|----------|-------------|----------------|
| **Claude Code CLI** | Entire `skills/` folder | Clone repo into `~/.claude/skills/` |
| **Claude.ai (Web)** | `DESIGN-REPLICATOR-STANDALONE.md` | Upload as attachment in chat |

**See [INSTALL-GUIDE.md](INSTALL-GUIDE.md) for detailed step-by-step instructions.**

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
- ✅ **Editable output** — text boxes in PPTX, HTML elements in web
- ✅ **Visual QA loop** — automated comparison with source to ensure ≥95% match

---

## 📁 Repository Structure

```
design-replicator-skill/
├── SKILL.md                          ← Main skill (Claude Code loads this)
├── DESIGN-REPLICATOR-STANDALONE.md   ← Self-contained version (Claude.ai web upload)
├── INSTALL-GUIDE.md                  ← Step-by-step installation instructions
├── README.md                         ← This file
└── references/
    ├── font-matching.md              ← Font identification & Google Fonts mapping
    └── pptx-coordinates.md           ← PowerPoint coordinate system reference
```

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

### System (Linux)
```bash
sudo apt install tesseract-ocr libreoffice-impress poppler-utils
```

### System (macOS)
```bash
brew install tesseract poppler libreoffice
```

---

## 📄 License

MIT License — free for personal and commercial use.

---

**Created by Kwame Sarkodee-Adoo** | [Hobnob Digital](https://github.com/Hobnobdigital)

**Version:** 2.0 | **Last Updated:** February 8, 2026
