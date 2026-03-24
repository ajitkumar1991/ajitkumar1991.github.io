# Website Architecture Plan

## Current State

This is a Quarto-based academic portfolio website for Ajit Kumar Sorout, a Physics PhD student at UMass Amherst. The site currently has five main pages (Home, Research, Blog, Photos, About) and six substantial blog posts covering tensor networks, the worm algorithm, brane tilings, diffusion models, zeta regularization, and an interdisciplinary essay.

### Strengths
- Technically sophisticated blog posts with real mathematical content and working code
- Good interdisciplinary framing across string theory, condensed matter, and computation
- Clean Quarto setup with light/dark mode and professional typography
- Strong foundation in SCSS styling (Source Serif Pro, JetBrains Mono, academic blue palette)

### Weaknesses
- About page full of placeholder text (degrees, email, office, teaching courses)
- No dedicated publications or contact pages
- Topic pages are just blog listing filters, not substantive content
- All deep content lives in blog posts — no organized reference section
- Navigation doesn't scale for adding substantial new content
- Missing content on several important research topics

---

## Proposed Architecture

### Navigation Structure

**Navbar (6 items with dropdowns):**
- Home | Research | Writing (Notes, Blog) | Computational Tools | Publications | More (About, Contact & CV, Photos)

**Sidebars:**
- Notes sidebar: grouped by theme (String Theory & Geometry, Many-Body & Computation, Methods & Foundations)
- Tools sidebar: flat list of practical reference pages
- Blog sidebar: simplified

### New Sections

1. **Notes & Expositions** (`notes/`): Eight substantial technical pages (3000-8000+ words each) covering tensor networks, Monte Carlo methods, brane tilings, machine learning, quantum information, mirror symmetry, 2D CFT & swampland, and group theory in QM. Four absorb and expand existing blog posts; four are new.

2. **Computational Tools** (`tools/`): Three practical reference pages on Julia tensor network workflows, Monte Carlo error analysis, and data analysis methods.

3. **Publications** (`publications.qmd`): Dedicated page for papers, preprints, and talks.

4. **Contact** (`contact.qmd`): Clean contact page with CV download.

### Content Strategy

- Blog posts on existing topics are absorbed into Notes pages (blog files become stubs redirecting to Notes)
- Notes pages are evergreen reference material, not dated entries
- Each note has a difficulty level (introductory / advanced / research-level)
- Research page becomes a concise gateway linking to Notes for depth
- Topics directory is retired

### Editorial Principles

- Write like a technically strong graduate researcher, not like a summary generator
- Use proper LaTeX throughout
- Include working code examples (Julia for numerics, Python for ML/data analysis)
- Cite real papers — no hallucinated references
- Distinguish introductory, advanced, and research-level material
- Connect physics, mathematics, and computation naturally
