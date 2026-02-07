---
name: design-replicator
description: Replicate website, document, or report designs exactly from screenshots, PDFs, images, or mockups. Creates pixel-perfect HTML/CSS/React code that matches the input design 1:1. Use when user says "replicate this design", "clone this website", "exact replica", "match this design", or provides an image/PDF of a design to recreate.
license: MIT
---

# Design Replicator Skill

This skill replicates website, document, or report designs exactly from visual inputs (screenshots, PDFs, images, mockups). It creates pixel-perfect code that matches the input design 1:1.

## When to Use This Skill

Use this skill when the user:
- Says "replicate this design", "clone this website", "exact replica"
- Says "match this design", "recreate this layout"
- Provides a screenshot, PDF, or image of a design
- Wants to recreate an existing website or document
- Needs to convert a Figma design or mockup to code

## Core Workflow

### Step 1: Analyze the Input Design

When the user provides an image, PDF, or screenshot:

1. **Examine the overall layout**
   - Grid structure (1-column, 2-column, sidebar layout, etc.)
   - Header, body, footer structure
   - Navigation placement
   - Content hierarchy

2. **Identify visual elements**
   - Typography (fonts, sizes, weights, line heights)
   - Color palette (backgrounds, text, accents, borders)
   - Spacing (margins, padding, gaps)
   - Images and graphics
   - Icons and decorative elements

3. **Note interactive elements**
   - Buttons (styles, hover states)
   - Forms and inputs
   - Links and navigation
   - Cards and containers

### Step 2: Extract Design Specifications

Document these specifications precisely:

**Typography:**
```
- Font families used
- Heading sizes (H1, H2, H3, etc.)
- Body text size and line height
- Special text treatments (bold, italic, uppercase)
```

**Colors:**
```
- Primary background color
- Secondary/accent colors
- Text colors
- Border colors
- Shadow colors
```

**Layout:**
```
- Container max-width
- Grid structure
- Column widths
- Gap sizes
- Responsive breakpoints
```

**Spacing:**
```
- Section padding
- Element margins
- Grid gaps
- Container padding
```

### Step 3: Generate Pixel-Perfect Code

Based on the analysis, generate code using ONE of these stacks:

**Option A: HTML + Tailwind CSS** (Recommended for simple sites)
- Use Tailwind utility classes for exact styling
- Match colors using arbitrary values (e.g., `bg-[#FF5733]`)
- Use exact pixel values (e.g., `w-[300px]`, `h-[200px]`)
- Include responsive variants

**Option B: React + Tailwind CSS** (For interactive sites)
- Create React components for reusable elements
- Use Tailwind for styling
- Add state management if needed
- Include hover/focus states

**Option C: HTML + CSS** (For maximum control)
- Use inline styles for pixel-perfect values
- Or create a dedicated CSS file
- Use CSS variables for repeated values

### Step 4: Verification Checklist

Before presenting the code, verify:

- [ ] Colors match exactly (use color picker values)
- [ ] Fonts match the original
- [ ] Spacing is identical (margins, padding, gaps)
- [ ] Layout structure matches
- [ ] Images are properly sized and positioned
- [ ] Typography matches (size, weight, line height)
- [ ] Responsive behavior works
- [ ] No placeholder content - everything is filled

## Critical Rules for Exact Replication

### 1. NO "AI Slop"
- Do NOT use generic purple gradients
- Do NOT use default rounded corners everywhere
- Do NOT use default fonts (Inter, Roboto, Arial)
- Do NOT center everything by default
- Match the EXACT design choices in the reference

### 2. Exact Measurements
- Use pixel-perfect values from the reference
- Do not approximate - measure precisely
- Use browser dev tools or image editor to get exact values
- Document the measurements in comments

### 3. Match Typography EXACTLY
- Identify the exact font family
- Match font sizes precisely
- Match font weights (400, 600, 700, etc.)
- Match letter-spacing and line-height
- Match text transformations (uppercase, capitalize)

### 4. Match Colors EXACTLY
- Extract hex codes using color picker
- Note opacity values
- Match gradient stops precisely
- Document all colors used

### 5. Match Layout EXACTLY
- Same grid structure
- Same column widths
- Same responsive breakpoints
- Same alignment (left, right, center, justify)

## Output Format

### For HTML/Tailwind:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Replicated Design</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Custom config for exact colors/fonts -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'brand-primary': '#EXACT_COLOR',
                        'brand-secondary': '#EXACT_COLOR',
                    },
                    fontFamily: {
                        'custom': ['Exact Font', 'sans-serif'],
                    }
                }
            }
        }
    </script>
</head>
<body>
    <!-- Exact replica of the design -->
</body>
</html>
```

### For React:
```jsx
// Component structure matching the design exactly
// Use exact values from analysis
```

## Handling Different Input Types

### Screenshots/Images:
- Analyze pixel-by-pixel
- Measure elements using grid overlay
- Extract colors precisely
- Note exact positioning

### PDFs:
- Convert pages to images if needed
- Extract text content accurately
- Note page structure
- Maintain multi-page layout if applicable

### Figma Designs:
- Note component structure
- Extract exact values from properties panel
- Match auto-layout behavior
- Export assets at correct sizes

### Existing Websites:
- Use browser dev tools to inspect
- Copy exact CSS values
- Note computed styles
- Extract assets (images, icons)

## Example Prompts to Use This Skill

User: "Replicate this website design exactly"
→ Use this skill to analyze and recreate pixel-perfect code

User: "Clone this landing page from the screenshot"
→ Extract all design elements and recreate 1:1

User: "Match this PDF report layout"
→ Replicate document structure and styling exactly

User: "Recreate this dashboard from the image"
→ Match layout, colors, typography precisely

## Quality Standards

The replicated design should be:
- ✅ Visually indistinguishable from the original
- ✅ Pixel-perfect measurements
- ✅ Exact color matches
- ✅ Proper responsive behavior
- ✅ Clean, production-ready code
- ✅ Properly commented with measurements

## Tools to Use

When available, use:
- Color picker tools for exact hex codes
- Image editors for measuring distances
- Browser dev tools for inspecting existing sites
- PDF viewers for extracting text content

## Important Notes

1. **Always ask for clarification** if the design intent is unclear
2. **Confirm the tech stack** preference (HTML, React, Vue, etc.)
3. **Note any animations** or interactions to replicate
4. **Document design decisions** in code comments
5. **Test at multiple screen sizes** for responsive designs
6. **Use placeholder images** only if user hasn't provided assets

## Output Deliverables

For each replication task, provide:
1. Complete source code file(s)
2. Design specification document (extracted values)
3. Instructions for running/using the code
4. List of any required assets (fonts, images)
5. Notes on responsive behavior

---

Remember: The goal is 1:1 replication. Every pixel matters. Measure twice, code once.
