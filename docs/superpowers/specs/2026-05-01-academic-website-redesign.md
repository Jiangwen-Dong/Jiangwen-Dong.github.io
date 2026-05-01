# Academic Website Redesign — Design Spec

**Date:** 2026-05-01  
**Topic:** Jiangwen Dong Academic Pages Redesign  
**Status:** Approved

---

## 1. Overview

Redesign the existing Jekyll-based academic website (`jiangwen-dong.github.io`) with a bold, memorable, yet clean visual identity that reflects the owner's research focus on graph-driven multi-agent systems. The redesign covers visual design, site structure, and content organization.

### Goals
- Create a distinctive visual identity tied to research (graph/network motif)
- Present publications, research, and CV in a clear, scannable format
- Remove template placeholder content and organize real content coherently
- Maintain Jekyll + GitHub Pages hosting for easy updates

---

## 2. Design System

### 2.1 Color Palette

| Role | Hex | Usage |
|------|-----|-------|
| Primary Background | `#0a1628` | Hero section, footer |
| Content Background | `#ffffff` | Main content areas |
| Accent | `#00d4aa` | Links, buttons, active nav, graph nodes |
| Text Primary | `#1a1a2e` | Headings on light backgrounds |
| Text Body | `#334155` | Body text on light backgrounds |
| Text Light | `#f8fafc` | Text on dark backgrounds |
| Subtle Background | `#f8fafc` | Alternate section backgrounds |

### 2.2 Typography

- **Headings:** Inter or Geist (geometric sans-serif), bold weight, tight letter-spacing
- **Body:** Inter or Source Sans Pro, regular weight, line-height 1.6
- **Scale:**
  - Name (hero): 48–64px
  - Section titles: 32–40px
  - Body text: 16–18px
  - Card titles: 20–24px

### 2.3 Visual Motif

A subtle network/graph visualization (nodes + edges) appears in the hero section:
- 20–30 nodes connected by edges
- Teal color (`#00d4aa`): nodes at 40% opacity, edges at 15% opacity
- Slow, gentle drift animation
- Static fallback for no-JS browsers
- Canvas or SVG implementation, ~50 lines of JavaScript

---

## 3. Site Structure

### 3.1 Navigation (4 items)

```
Home (About) | Publications | Research | CV
```

Update `_data/navigation.yml` to uncomment and enable these four links.

### 3.2 Pages

| Page | Route | Purpose |
|------|-------|---------|
| Home | `/` | Introduction, research pillars, recent publications |
| Publications | `/publications/` | All papers, chronologically listed |
| Research | `/research/` | Research areas, projects, collaborations |
| CV | `/cv-json/` | JSON-rendered curriculum vitae |

---

## 4. Page Designs

### 4.1 Homepage (`/`, About)

Single-scroll page with four sections:

#### Hero Section (full viewport height, dark `#0a1628`)
- **Left (60%):**
  - Name: "Jiangwen Dong" (48–56px, white, bold)
  - Subtitle: "PhD Student · PolyU · Graph-Driven Multi-Agent Systems"
  - One-line mission statement
  - Social icon links: Google Scholar, GitHub, Email
- **Right (40%):**
  - Animated network graph visualization (see Design System §2.3)

#### Research Pillars Section (white background)
- Heading: "Research"
- Four cards in a row (responsive: 4 → 2×2 → 1):
  1. **Structured** — graph-based reasoning
  2. **Collaborative** — multi-agent LLMs
  3. **Efficient** — edge–cloud computation
  4. **Adaptive** — continual and personalized learning
- Each card: icon, title, one-sentence description

#### Recent Publications Section (`#f8fafc` background)
- Heading: "Selected Publications"
- 3 publication cards (most recent/important papers)
- Each card: title, venue badge, authors, one-line abstract, paper links
- "View all publications →" link to `/publications/`

#### Footer
- Minimal: email, social links, copyright

### 4.2 Publications Page (`/publications/`)

- Page header: "Publications" with paper count
- Chronological list, most recent first, grouped by year
- Each paper as a card:
  - Left: venue badge (e.g., "AAAI 2026" in teal)
  - Right:
    - Title (bold, clickable to paper detail page)
    - Author list (owner's name bolded)
    - Venue / status (e.g., "AAAI 2026 · Accepted")
    - Abstract summary (1 paragraph)
    - Action links: [PDF] [arXiv] [Code] [BibTeX]

**Individual Paper Pages:**
- Route: `/publications/<slug>/`
- Full citation, abstract, all links
- Optional: slides, poster, video embeds

### 4.3 Research Page (`/research/`)

- Page header: "Research"
- Overview paragraph (2–3 sentences on research direction)

**Research Areas (4 expanded cards):**
- Same 4 areas as homepage pillars
- Each with 2–3 paragraph description
- 1–2 tagged relevant papers below each

**Active Projects Section:**
- Grid/list of current projects
- Each: name, description, status badge, links

### 4.4 CV Page (`/cv-json/`)

- Page header: "Curriculum Vitae" + "Download PDF" button (teal)
- Two-column layout on desktop (30/70), single column on mobile

**Left column:**
- Name, contact info
- Links: Google Scholar, GitHub
- Skills, interests

**Right column (from `_data/cv.json`):**
- Education (timeline layout)
- Publications (synced from collection)
- Skills, languages, interests

---

## 5. Content Organization

### 5.1 Publications (3 papers)

| Paper | Venue | Status | File |
|-------|-------|--------|------|
| S-DAG: A Subject-Based Directed Acyclic Graph for Multi-Agent Heterogeneous Reasoning | AAAI 2026 | Accepted | `_publications/2026-S-DAG.md` |
| HybridFlow: Adaptive Task Scheduling for Fast and Token-Efficient LLM Inference in Edge-Cloud Collaboration | TBD | Accepted | `_publications/2026-HybridFlow.md` |
| [Third paper] | TBD | Accepted/Under Review | New file to create |

**Cleanup:** Remove template placeholder papers:
- `_publications/2010-10-01-paper-title-number-2.md`
- `_publications/2015-10-01-paper-title-number-3.md`
- `_publications/2024-02-17-paper-title-number-4.md`

### 5.2 Research Page Content

The 4 research pillars map to the About page description:
- **Structured:** Graph-based reasoning methods for organizing LLM inference
- **Collaborative:** Multi-agent LLM systems that coordinate and share knowledge
- **Efficient:** Edge–cloud computation paradigms for distributed AI
- **Adaptive:** Continual learning and personalization in multi-agent settings

### 5.3 CV Data

Continue using `_data/cv.json`. Update with:
- Correct Google Scholar link (currently has wrong user ID)
- Add skills (programming languages, frameworks)
- Add interests/research areas
- Sync publications with `_publications/` collection

---

## 6. Technical Approach

### 6.1 What Stays the Same
- Jekyll static site generator
- GitHub Pages hosting
- Existing content structure (`_publications/`, `_pages/`, `_data/`)
- Academic Pages template as base

### 6.2 What Changes

| Component | Change |
|-----------|--------|
| CSS | New custom stylesheet in `assets/css/` or `_sass/` implementing the design system |
| Navigation | Update `_data/navigation.yml` to show 4 active links |
| Hero | Add canvas/SVG graph animation script (~50 lines) |
| CV page | Restyle `_pages/cv-json.md` to match new design |
| Content | Remove template placeholders; add real publications |

### 6.3 Graph Animation Specification

- **Technology:** HTML5 Canvas or inline SVG
- **Node count:** 20–30
- **Behavior:**
  - Nodes drift slowly with random velocity
  - Edges connect nearby nodes (distance threshold)
  - Mouse interaction: nodes gently repel from cursor
- **Style:**
  - Node color: `#00d4aa` at 40% opacity
  - Edge color: `#00d4aa` at 15% opacity
  - Node size: 2–4px
- **Performance:** RequestAnimationFrame, throttled
- **Fallback:** Static geometric pattern or gradient if JS disabled

### 6.4 Responsive Breakpoints

| Breakpoint | Layout Changes |
|------------|----------------|
| ≥1024px | Full desktop: 2-column CV, 4-column research cards, hero side-by-side |
| 768–1023px | Tablet: 2×2 research cards, stacked hero, single-column CV |
| <768px | Mobile: single column everything, hamburger nav, reduced type sizes |

---

## 7. Files to Modify / Create

### Modify
- `_config.yml` — update description, theme settings if needed
- `_data/navigation.yml` — enable 4 nav items
- `_data/cv.json` — update content, fix links
- `_pages/about.md` — restructure as homepage content
- `_pages/cv-json.md` — restyle to match design
- `assets/css/main.scss` or create new stylesheet — implement design system

### Create
- `_pages/research.md` — new research page
- `_publications/[third-paper].md` — third paper entry
- `assets/js/hero-graph.js` — graph animation script
- `docs/superpowers/specs/2026-05-01-academic-website-redesign.md` — this document

### Delete / Archive
- `_publications/2010-10-01-paper-title-number-2.md`
- `_publications/2015-10-01-paper-title-number-3.md`
- `_publications/2024-02-17-paper-title-number-4.md`
- `_posts/` template blog posts (if not needed)
- `_talks/` template talks (if not needed)
- `_teaching/` template entries (if not needed)
- `_portfolio/` template entries (if not needed)

---

## 8. Open Questions / Decisions

1. **Third paper details:** Awaiting title, venue, and status from owner to create the publication entry.
2. **Hero graph implementation:** Canvas (better performance) vs. SVG (simpler, CSS-stylable) — recommend Canvas.
3. **Font loading:** Self-host Inter/Geist or use Google Fonts CDN — recommend Google Fonts for simplicity.
4. **CV PDF generation:** Manual export or automated from `cv.json` — recommend manual for now.

---

## 9. Success Criteria

- [ ] Homepage displays correctly with graph animation on desktop and mobile
- [ ] All 4 navigation items work and lead to correct pages
- [ ] Publications page lists all real papers with correct metadata
- [ ] Research page describes the 4 research pillars with relevant papers tagged
- [ ] CV page renders correctly from `cv.json` with new styling
- [ ] Template placeholder content is fully removed
- [ ] Site passes basic accessibility checks (contrast, keyboard nav, alt text)
- [ ] Site builds successfully with `jekyll build`
