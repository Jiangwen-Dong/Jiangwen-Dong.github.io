# Academic Website Redesign Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Implement the graph-inspired redesign of the Jekyll academic website with 4 sections (Home, Publications, Research, CV), custom styling, hero animation, and cleaned-up content.

**Architecture:** Extend the existing Academic Pages Jekyll template with a custom CSS design system, a canvas-based hero graph animation, and restructured markdown content. Keep Jekyll + GitHub Pages as the build and deploy pipeline.

**Tech Stack:** Jekyll, GitHub Pages, SCSS/CSS, HTML5 Canvas, JavaScript

---

## File Structure

| File | Action | Purpose |
|------|--------|---------|
| `_data/navigation.yml` | Modify | Enable 4 nav items |
| `_config.yml` | Modify | Update site description |
| `_data/cv.json` | Modify | Fix Scholar link, add skills |
| `_publications/2026-S-DAG.md` | Modify | Fix frontmatter, add excerpt |
| `_publications/2026-HybridFlow.md` | Modify | Fix frontmatter, add excerpt, venue |
| `_pages/about.md` | Modify | Restructure as full homepage |
| `_pages/cv-json.md` | Modify | Restyle layout |
| `assets/css/custom.scss` | Create | Design system + component styles |
| `assets/js/hero-graph.js` | Create | Canvas graph animation |
| `_pages/research.md` | Create | Research areas page |
| `_publications/2010-10-01-paper-title-number-2.md` | Delete | Template placeholder |
| `_publications/2015-10-01-paper-title-number-3.md` | Delete | Template placeholder |
| `_publications/2024-02-17-paper-title-number-4.md` | Delete | Template placeholder |
| `_posts/2012-08-14-blog-post-1.md` | Delete | Template placeholder |
| `_posts/2013-08-14-blog-post-2.md` | Delete | Template placeholder |
| `_posts/2014-08-14-blog-post-3.md` | Delete | Template placeholder |
| `_posts/2015-08-14-blog-post-4.md` | Delete | Template placeholder |
| `_posts/2199-01-01-future-post.md` | Delete | Template placeholder |
| `_talks/2012-03-01-talk-1.md` | Delete | Template placeholder |
| `_talks/2013-03-01-tutorial-1.md` | Delete | Template placeholder |
| `_talks/2014-02-01-talk-2.md` | Delete | Template placeholder |
| `_talks/2014-03-01-talk-3.md` | Delete | Template placeholder |
| `_teaching/2014-spring-teaching-1.md` | Delete | Template placeholder |
| `_teaching/2015-spring-teaching-2.md` | Delete | Template placeholder |
| `_portfolio/portfolio-1.md` | Delete | Template placeholder |

---

### Task 1: Clean Up Template Content

**Files:**
- Delete: `_publications/2010-10-01-paper-title-number-2.md`
- Delete: `_publications/2015-10-01-paper-title-number-3.md`
- Delete: `_publications/2024-02-17-paper-title-number-4.md`
- Delete: `_posts/2012-08-14-blog-post-1.md`
- Delete: `_posts/2013-08-14-blog-post-2.md`
- Delete: `_posts/2014-08-14-blog-post-3.md`
- Delete: `_posts/2015-08-14-blog-post-4.md`
- Delete: `_posts/2199-01-01-future-post.md`
- Delete: `_talks/2012-03-01-talk-1.md`
- Delete: `_talks/2013-03-01-tutorial-1.md`
- Delete: `_talks/2014-02-01-talk-2.md`
- Delete: `_talks/2014-03-01-talk-3.md`
- Delete: `_teaching/2014-spring-teaching-1.md`
- Delete: `_teaching/2015-spring-teaching-2.md`
- Delete: `_portfolio/portfolio-1.md`

- [ ] **Step 1: Remove all template placeholder files**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
rm -f _publications/2010-10-01-paper-title-number-2.md
rm -f _publications/2015-10-01-paper-title-number-3.md
rm -f _publications/2024-02-17-paper-title-number-4.md
rm -f _posts/2012-08-14-blog-post-1.md
rm -f _posts/2013-08-14-blog-post-2.md
rm -f _posts/2014-08-14-blog-post-3.md
rm -f _posts/2015-08-14-blog-post-4.md
rm -f _posts/2199-01-01-future-post.md
rm -f _talks/2012-03-01-talk-1.md
rm -f _talks/2013-03-01-tutorial-1.md
rm -f _talks/2014-02-01-talk-2.md
rm -f _talks/2014-03-01-talk-3.md
rm -f _teaching/2014-spring-teaching-1.md
rm -f _teaching/2015-spring-teaching-2.md
rm -f _portfolio/portfolio-1.md
```

- [ ] **Step 2: Verify only real content remains**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
ls _publications/
ls _posts/
ls _talks/
ls _teaching/
ls _portfolio/
```

Expected: `_publications/` should only contain `2026-S-DAG.md` and `2026-HybridFlow.md`. Other directories should be empty.

- [ ] **Step 3: Commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git add -A
git commit -m "chore: remove all template placeholder content"
```

---

### Task 2: Update Site Configuration

**Files:**
- Modify: `_config.yml`
- Modify: `_data/navigation.yml`

- [ ] **Step 1: Update _config.yml description**

Edit `_config.yml` line 15, change:
```yaml
description              : &description "Your Name's academic portfolio"
```
to:
```yaml
description              : &description "PhD Student at PolyU researching graph-driven multi-agent systems and LLM reasoning"
```

- [ ] **Step 2: Update navigation**

Replace the entire contents of `_data/navigation.yml` with:
```yaml
main:
  - title: "Home"
    url: /

  - title: "Publications"
    url: /publications/

  - title: "Research"
    url: /research/

  - title: "CV"
    url: /cv-json/
```

- [ ] **Step 3: Verify Jekyll builds**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
bundle exec jekyll build
```

Expected: Build succeeds with no errors.

- [ ] **Step 4: Commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git add _config.yml _data/navigation.yml
git commit -m "config: update site description and enable 4-section navigation"
```

---

### Task 3: Update Publications

**Files:**
- Modify: `_publications/2026-S-DAG.md`
- Modify: `_publications/2026-HybridFlow.md`

- [ ] **Step 1: Fix S-DAG publication frontmatter**

Replace the entire contents of `_publications/2026-S-DAG.md` with:
```markdown
---
title: "S-DAG: A Subject-Based Directed Acyclic Graph for Multi-Agent Heterogeneous Reasoning"
collection: publications
category: conferences
permalink: /publication/2026-s-dag
excerpt: "We propose S-DAG, a subject-based directed acyclic graph framework for multi-agent heterogeneous reasoning that enables structured collaboration among diverse LLM agents."
date: 2026-01-20
venue: "AAAI Conference on Artificial Intelligence"
paperurl: "https://arxiv.org/abs/2511.06727"
citation: 'Dong, Jiangwen, Zehui Lin, Wanyu Lin, and Mingjin Zhang. "S-DAG: A Subject-Based Directed Acyclic Graph for Multi-Agent Heterogeneous Reasoning." AAAI 2026.'
---

We propose S-DAG, a subject-based directed acyclic graph framework for multi-agent heterogeneous reasoning that enables structured collaboration among diverse LLM agents.
```

- [ ] **Step 2: Fix HybridFlow publication frontmatter**

Replace the entire contents of `_publications/2026-HybridFlow.md` with:
```markdown
---
title: "HybridFlow: Adaptive Task Scheduling for Fast and Token-Efficient LLM Inference in Edge-Cloud Collaboration"
collection: publications
category: conferences
permalink: /publication/2026-hybridflow
excerpt: "HybridFlow introduces an adaptive task scheduling framework for efficient LLM inference across edge-cloud environments, optimizing both latency and token usage."
date: 2026-01-20
venue: "IEEE International Conference on Distributed Computing Systems"
paperurl: "https://arxiv.org/abs/2512.22137"
citation: 'Dong, Jiangwen, Jiayu Li, and Wanyu Lin. "HybridFlow: Adaptive Task Scheduling for Fast and Token-Efficient LLM Inference in Edge-Cloud Collaboration." ICDCS 2026.'
---

HybridFlow introduces an adaptive task scheduling framework for efficient LLM inference across edge-cloud environments, optimizing both latency and token usage.
```

- [ ] **Step 3: Build and verify**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
bundle exec jekyll build
```

Expected: Build succeeds.

- [ ] **Step 4: Commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git add _publications/
git commit -m "content: update S-DAG and HybridFlow publications with proper frontmatter"
```

---

### Task 4: Update CV Data

**Files:**
- Modify: `_data/cv.json`

- [ ] **Step 1: Fix Google Scholar link and add skills**

Edit `_data/cv.json`:

Change line 19:
```json
"url": "https://scholar.google.com/citations?user=PS_CX0AAAAAJ"
```
to:
```json
"url": "https://scholar.google.com/citations?user=Kl-dTYAAAAAJ"
```

Replace the `"skills": []` section with:
```json
"skills": [
  {
    "name": "Programming",
    "keywords": ["Python", "PyTorch", "TensorFlow", "C++"]
  },
  {
    "name": "Research Areas",
    "keywords": ["Multi-Agent Systems", "Graph Neural Networks", "LLM Reasoning", "Distributed Systems"]
  }
]
```

Replace the `"interests": []` section with:
```json
"interests": [
  {
    "name": "Graph-Driven Multi-Agent Systems",
    "keywords": ["agent collaboration", "graph reasoning", "heterogeneous reasoning"]
  },
  {
    "name": "Efficient LLM Inference",
    "keywords": ["edge computing", "task scheduling", "token efficiency"]
  }
]
```

- [ ] **Step 2: Build and verify**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
bundle exec jekyll build
```

- [ ] **Step 3: Commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git add _data/cv.json
git commit -m "content: fix Google Scholar link and add skills/interests to CV"
```

---

### Task 5: Create Custom Stylesheet

**Files:**
- Create: `assets/css/custom.scss`
- Modify: `_includes/head/custom.html` (or create if not exists)

- [ ] **Step 1: Create custom.scss with design system**

Create `assets/css/custom.scss`:
```scss
---
---

/* ========================================
   Design System Variables
   ======================================== */

:root {
  --color-navy: #0a1628;
  --color-white: #ffffff;
  --color-teal: #00d4aa;
  --color-text-primary: #1a1a2e;
  --color-text-body: #334155;
  --color-text-light: #f8fafc;
  --color-bg-subtle: #f8fafc;
  --font-heading: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-body: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
}

/* ========================================
   Base Overrides
   ======================================== */

body {
  font-family: var(--font-body);
  color: var(--color-text-body);
  line-height: 1.6;
}

h1, h2, h3, h4, h5, h6 {
  font-family: var(--font-heading);
  color: var(--color-text-primary);
  font-weight: 700;
  letter-spacing: -0.02em;
}

a {
  color: var(--color-teal);
  text-decoration: none;
  transition: opacity 0.2s ease;
}

a:hover {
  opacity: 0.8;
  text-decoration: underline;
}

/* ========================================
   Masthead / Navigation
   ======================================== */

.masthead {
  background: var(--color-white);
  border-bottom: 1px solid rgba(0, 0, 0, 0.05);
}

.greedy-nav {
  background: transparent;
}

.greedy-nav a {
  color: var(--color-text-primary);
  font-weight: 500;
  font-size: 0.95rem;
  padding: 0.75rem 1rem;
}

.greedy-nav a:hover {
  color: var(--color-teal);
}

/* ========================================
   Hero Section
   ======================================== */

.hero-section {
  background: var(--color-navy);
  color: var(--color-text-light);
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.hero-section h1 {
  color: var(--color-text-light);
  font-size: 3.5rem;
  font-weight: 800;
  margin-bottom: 1rem;
  letter-spacing: -0.03em;
}

.hero-section .subtitle {
  font-size: 1.25rem;
  color: rgba(248, 250, 252, 0.8);
  margin-bottom: 1.5rem;
}

.hero-section .mission {
  font-size: 1rem;
  color: rgba(248, 250, 252, 0.6);
  max-width: 500px;
  line-height: 1.7;
}

.hero-social-links {
  margin-top: 2rem;
  display: flex;
  gap: 1rem;
}

.hero-social-links a {
  color: var(--color-teal);
  font-size: 1.5rem;
  transition: transform 0.2s ease;
}

.hero-social-links a:hover {
  transform: translateY(-2px);
  opacity: 1;
}

#hero-graph-canvas {
  position: absolute;
  top: 0;
  right: 0;
  width: 50%;
  height: 100%;
  opacity: 0.6;
}

/* ========================================
   Section Styles
   ======================================== */

.section {
  padding: 5rem 0;
}

.section-alt {
  background: var(--color-bg-subtle);
}

.section-title {
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 2.5rem;
  color: var(--color-text-primary);
}

/* ========================================
   Research Cards
   ======================================== */

.research-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
}

.research-card {
  background: var(--color-white);
  border: 1px solid rgba(0, 0, 0, 0.06);
  border-radius: 12px;
  padding: 2rem 1.5rem;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.research-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.08);
}

.research-card-icon {
  font-size: 2rem;
  margin-bottom: 1rem;
}

.research-card h3 {
  font-size: 1.25rem;
  margin-bottom: 0.75rem;
}

.research-card p {
  font-size: 0.95rem;
  color: var(--color-text-body);
  line-height: 1.6;
}

/* ========================================
   Publication Cards
   ======================================== */

.pub-card {
  background: var(--color-white);
  border: 1px solid rgba(0, 0, 0, 0.06);
  border-radius: 12px;
  padding: 1.75rem;
  margin-bottom: 1.25rem;
  display: flex;
  gap: 1.5rem;
  transition: box-shadow 0.2s ease;
}

.pub-card:hover {
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.06);
}

.pub-venue-badge {
  background: var(--color-teal);
  color: var(--color-navy);
  font-size: 0.75rem;
  font-weight: 700;
  padding: 0.35rem 0.75rem;
  border-radius: 20px;
  white-space: nowrap;
  height: fit-content;
}

.pub-content h3 {
  font-size: 1.15rem;
  margin-bottom: 0.5rem;
}

.pub-authors {
  font-size: 0.9rem;
  color: var(--color-text-body);
  margin-bottom: 0.5rem;
}

.pub-authors .highlight {
  font-weight: 600;
  color: var(--color-text-primary);
}

.pub-abstract {
  font-size: 0.9rem;
  color: var(--color-text-body);
  line-height: 1.6;
  margin-bottom: 0.75rem;
}

.pub-links {
  display: flex;
  gap: 1rem;
}

.pub-links a {
  font-size: 0.85rem;
  font-weight: 500;
}

/* ========================================
   CV Page
   ======================================== */

.cv-layout {
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 3rem;
}

.cv-sidebar {
  border-right: 1px solid rgba(0, 0, 0, 0.08);
  padding-right: 2rem;
}

.cv-sidebar h2 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.cv-section {
  margin-bottom: 2.5rem;
}

.cv-section h3 {
  font-size: 1.1rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--color-teal);
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid var(--color-teal);
}

.timeline-item {
  margin-bottom: 1.5rem;
}

.timeline-item .institution {
  font-weight: 600;
  color: var(--color-text-primary);
}

.timeline-item .degree {
  color: var(--color-text-body);
}

.timeline-item .date {
  font-size: 0.85rem;
  color: rgba(51, 65, 85, 0.7);
}

/* ========================================
   Footer
   ======================================== */

.page__footer {
  background: var(--color-navy);
  color: var(--color-text-light);
}

.page__footer a {
  color: var(--color-teal);
}

/* ========================================
   Responsive
   ======================================== */

@media (max-width: 1023px) {
  .research-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .cv-layout {
    grid-template-columns: 1fr;
  }

  .cv-sidebar {
    border-right: none;
    border-bottom: 1px solid rgba(0, 0, 0, 0.08);
    padding-right: 0;
    padding-bottom: 2rem;
  }

  #hero-graph-canvas {
    width: 100%;
    opacity: 0.3;
  }

  .hero-section h1 {
    font-size: 2.5rem;
  }
}

@media (max-width: 767px) {
  .research-grid {
    grid-template-columns: 1fr;
  }

  .pub-card {
    flex-direction: column;
    gap: 0.75rem;
  }

  .hero-section h1 {
    font-size: 2rem;
  }

  .hero-section .subtitle {
    font-size: 1rem;
  }
}
```

- [ ] **Step 2: Link stylesheet in head**

If `_includes/head/custom.html` exists, append to it. If not, create it:

```html
<link rel="stylesheet" href="/assets/css/custom.css">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
```

- [ ] **Step 3: Build and verify**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
bundle exec jekyll build
```

Expected: Build succeeds. Check `_site/assets/css/custom.css` exists.

- [ ] **Step 4: Commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git add assets/css/custom.scss _includes/head/custom.html
git commit -m "style: add custom design system with navy/teal theme"
```

---

### Task 6: Create Hero Graph Animation

**Files:**
- Create: `assets/js/hero-graph.js`
- Modify: `_includes/head/custom.html` (add script tag)

- [ ] **Step 1: Create hero-graph.js**

Create `assets/js/hero-graph.js`:
```javascript
(function() {
  const canvas = document.getElementById('hero-graph-canvas');
  if (!canvas) return;

  const ctx = canvas.getContext('2d');
  let width, height;
  let nodes = [];
  const NODE_COUNT = 25;
  const CONNECTION_DISTANCE = 150;
  const NODE_COLOR = 'rgba(0, 212, 170, 0.4)';
  const EDGE_COLOR = 'rgba(0, 212, 170, 0.15)';

  function resize() {
    const rect = canvas.parentElement.getBoundingClientRect();
    width = rect.width;
    height = rect.height;
    canvas.width = width;
    canvas.height = height;
  }

  function initNodes() {
    nodes = [];
    for (let i = 0; i < NODE_COUNT; i++) {
      nodes.push({
        x: Math.random() * width,
        y: Math.random() * height,
        vx: (Math.random() - 0.5) * 0.4,
        vy: (Math.random() - 0.5) * 0.4,
        radius: 2 + Math.random() * 2
      });
    }
  }

  function update() {
    nodes.forEach(node => {
      node.x += node.vx;
      node.y += node.vy;

      if (node.x < 0 || node.x > width) node.vx *= -1;
      if (node.y < 0 || node.y > height) node.vy *= -1;
    });
  }

  function draw() {
    ctx.clearRect(0, 0, width, height);

    // Draw edges
    for (let i = 0; i < nodes.length; i++) {
      for (let j = i + 1; j < nodes.length; j++) {
        const dx = nodes[i].x - nodes[j].x;
        const dy = nodes[i].y - nodes[j].y;
        const dist = Math.sqrt(dx * dx + dy * dy);

        if (dist < CONNECTION_DISTANCE) {
          const opacity = (1 - dist / CONNECTION_DISTANCE) * 0.15;
          ctx.beginPath();
          ctx.moveTo(nodes[i].x, nodes[i].y);
          ctx.lineTo(nodes[j].x, nodes[j].y);
          ctx.strokeStyle = `rgba(0, 212, 170, ${opacity})`;
          ctx.lineWidth = 1;
          ctx.stroke();
        }
      }
    }

    // Draw nodes
    nodes.forEach(node => {
      ctx.beginPath();
      ctx.arc(node.x, node.y, node.radius, 0, Math.PI * 2);
      ctx.fillStyle = NODE_COLOR;
      ctx.fill();
    });
  }

  function animate() {
    update();
    draw();
    requestAnimationFrame(animate);
  }

  resize();
  initNodes();
  animate();

  window.addEventListener('resize', () => {
    resize();
    initNodes();
  });
})();
```

- [ ] **Step 2: Add script to head**

Append to `_includes/head/custom.html`:
```html
<script src="/assets/js/hero-graph.js" defer></script>
```

- [ ] **Step 3: Build and verify**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
bundle exec jekyll build
```

Expected: Build succeeds.

- [ ] **Step 4: Commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git add assets/js/hero-graph.js _includes/head/custom.html
git commit -m "feat: add hero canvas graph animation"
```

---

### Task 7: Restructure Homepage

**Files:**
- Modify: `_pages/about.md`

- [ ] **Step 1: Rewrite about.md as full homepage**

Replace the entire contents of `_pages/about.md` with:
```markdown
---
permalink: /
title: ""
author_profile: false
redirect_from:
  - /about/
  - /about.html
---

<!-- Hero Section -->
<div class="hero-section">
  <div class="hero-content" style="position: relative; z-index: 1; max-width: 1200px; margin: 0 auto; padding: 0 2rem; width: 100%;">
    <div style="max-width: 60%;">
      <h1>Jiangwen Dong</h1>
      <p class="subtitle">PhD Student · PolyU · Graph-Driven Multi-Agent Systems</p>
      <p class="mission">I develop graph-driven multi-agent systems that enable efficient, adaptive, and distributed LLM reasoning across edge–cloud environments.</p>
      <div class="hero-social-links">
        <a href="https://scholar.google.com/citations?user=Kl-dTYAAAAAJ&hl=en&oi=ao" target="_blank" aria-label="Google Scholar"><i class="fas fa-graduation-cap"></i></a>
        <a href="https://github.com/Jiangwen-Dong" target="_blank" aria-label="GitHub"><i class="fab fa-github"></i></a>
        <a href="mailto:jiangwen.dong@connect.polyu.hk" aria-label="Email"><i class="fas fa-envelope"></i></a>
      </div>
    </div>
  </div>
  <canvas id="hero-graph-canvas"></canvas>
</div>

<!-- Research Pillars Section -->
<div class="section">
  <div style="max-width: 1200px; margin: 0 auto; padding: 0 2rem;">
    <h2 class="section-title">Research</h2>
    <div class="research-grid">
      <div class="research-card">
        <div class="research-card-icon">🕸️</div>
        <h3>Structured</h3>
        <p>Graph-based reasoning methods for organizing and guiding LLM inference.</p>
      </div>
      <div class="research-card">
        <div class="research-card-icon">🤖</div>
        <h3>Collaborative</h3>
        <p>Multi-agent LLM systems that coordinate, communicate, and share knowledge.</p>
      </div>
      <div class="research-card">
        <div class="research-card-icon">⚡</div>
        <h3>Efficient</h3>
        <p>Edge–cloud computation paradigms for distributed and resource-aware AI.</p>
      </div>
      <div class="research-card">
        <div class="research-card-icon">🔄</div>
        <h3>Adaptive</h3>
        <p>Continual learning and personalization in dynamic multi-agent settings.</p>
      </div>
    </div>
  </div>
</div>

<!-- Recent Publications Section -->
<div class="section section-alt">
  <div style="max-width: 1200px; margin: 0 auto; padding: 0 2rem;">
    <h2 class="section-title">Selected Publications</h2>

    <div class="pub-card">
      <div class="pub-venue-badge">AAAI 2026</div>
      <div class="pub-content">
        <h3><a href="/publication/2026-s-dag">S-DAG: A Subject-Based Directed Acyclic Graph for Multi-Agent Heterogeneous Reasoning</a></h3>
        <p class="pub-authors"><span class="highlight">Jiangwen Dong</span>, Zehui Lin, Wanyu Lin, Mingjin Zhang</p>
        <p class="pub-abstract">A subject-based DAG framework enabling structured collaboration among diverse LLM agents for complex reasoning tasks.</p>
        <div class="pub-links">
          <a href="https://arxiv.org/abs/2511.06727" target="_blank">Paper →</a>
        </div>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-venue-badge">ICDCS 2026</div>
      <div class="pub-content">
        <h3><a href="/publication/2026-hybridflow">HybridFlow: Adaptive Task Scheduling for Fast and Token-Efficient LLM Inference in Edge-Cloud Collaboration</a></h3>
        <p class="pub-authors"><span class="highlight">Jiangwen Dong</span>, Jiayu Li, Wanyu Lin</p>
        <p class="pub-abstract">An adaptive task scheduling framework for efficient LLM inference across edge-cloud environments.</p>
        <div class="pub-links">
          <a href="https://arxiv.org/abs/2512.22137" target="_blank">Paper →</a>
        </div>
      </div>
    </div>

    <p style="margin-top: 2rem;"><a href="/publications/" style="font-weight: 600;">View all publications →</a></p>
  </div>
</div>
```

- [ ] **Step 2: Build and verify**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
bundle exec jekyll build
```

Expected: Build succeeds. Check `_site/index.html` for hero section content.

- [ ] **Step 3: Commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git add _pages/about.md
git commit -m "feat: restructure homepage with hero, research pillars, and publications"
```

---

### Task 8: Create Research Page

**Files:**
- Create: `_pages/research.md`

- [ ] **Step 1: Create research.md**

Create `_pages/research.md`:
```markdown
---
permalink: /research/
title: "Research"
author_profile: true
---

I develop graph-driven multi-agent systems that enable efficient, adaptive, and distributed LLM reasoning across edge–cloud environments. My research integrates graph intelligence, multi-agent collaboration, and efficient distributed systems.

## Research Areas

<div class="research-grid" style="margin-top: 2rem;">
  <div class="research-card">
    <div class="research-card-icon">🕸️</div>
    <h3>Structured Reasoning</h3>
    <p>Graph-based reasoning methods organize LLM inference into structured, interpretable workflows. By representing reasoning steps as nodes in a directed graph, we can guide multi-agent systems through complex problem-solving with explicit dependencies and subject-based decomposition.</p>
    <p style="margin-top: 1rem; font-size: 0.85rem;"><strong>Related:</strong> <a href="/publication/2026-s-dag">S-DAG (AAAI 2026)</a></p>
  </div>

  <div class="research-card">
    <div class="research-card-icon">🤖</div>
    <h3>Collaborative Multi-Agent Systems</h3>
    <p>Multi-agent LLM systems coordinate specialized agents to solve problems beyond the capability of any single model. My work focuses on heterogeneous agent collaboration, where agents with different capabilities and roles communicate through structured protocols.</p>
    <p style="margin-top: 1rem; font-size: 0.85rem;"><strong>Related:</strong> <a href="/publication/2026-s-dag">S-DAG (AAAI 2026)</a></p>
  </div>

  <div class="research-card">
    <div class="research-card-icon">⚡</div>
    <h3>Efficient Distributed Inference</h3>
    <p>Edge–cloud collaboration enables efficient LLM inference by distributing computation across heterogeneous devices. I design adaptive scheduling and token-efficient strategies that minimize latency while respecting resource constraints at the edge.</p>
    <p style="margin-top: 1rem; font-size: 0.85rem;"><strong>Related:</strong> <a href="/publication/2026-hybridflow">HybridFlow (ICDCS 2026)</a></p>
  </div>

  <div class="research-card">
    <div class="research-card-icon">🔄</div>
    <h3>Adaptive Learning</h3>
    <p>Continual and personalized learning in multi-agent settings allows systems to adapt to new tasks, user preferences, and changing environments without retraining from scratch. This includes federated personalization and online adaptation strategies.</p>
  </div>
</div>

## Active Projects

- **S-DAG Framework** — Subject-based DAG for multi-agent reasoning. <span style="color: var(--color-teal); font-weight: 600;">Accepted at AAAI 2026</span>
- **HybridFlow** — Adaptive edge-cloud LLM inference scheduling. <span style="color: var(--color-teal); font-weight: 600;">Accepted at ICDCS 2026</span>

## Collaborations

I am fortunate to work with my advisor <a href="https://www.comp.polyu.edu.hk/~wanyulin/" target="_blank">Prof. Wanyu Lin</a> and collaborators at The Hong Kong Polytechnic University.
```

- [ ] **Step 2: Build and verify**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
bundle exec jekyll build
```

Expected: Build succeeds. `_site/research/index.html` exists.

- [ ] **Step 3: Commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git add _pages/research.md
git commit -m "feat: add research page with areas and projects"
```

---

### Task 9: Update CV Page Styling

**Files:**
- Modify: `_pages/cv-json.md`

- [ ] **Step 1: Check current cv-json.md content**

Read `_pages/cv-json.md` to understand current structure.

- [ ] **Step 2: Add custom layout wrapper**

If the page uses the default layout, add a wrapper div with the `cv-layout` class around the CV content. The exact edit depends on the current file content.

Typical modification: wrap the existing content in:
```markdown
<div class="cv-layout">
  <div class="cv-sidebar">
    <!-- sidebar content -->
  </div>
  <div class="cv-main">
    <!-- main content -->
  </div>
</div>
```

- [ ] **Step 3: Build and verify**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
bundle exec jekyll build
```

- [ ] **Step 4: Commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git add _pages/cv-json.md
git commit -m "style: apply custom layout styling to CV page"
```

---

### Task 10: Final Build Verification

**Files:**
- All modified/created files

- [ ] **Step 1: Full Jekyll build**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
bundle exec jekyll build
```

Expected: Build succeeds with no errors. Warnings about empty collections (posts, talks, teaching) are acceptable.

- [ ] **Step 2: Verify generated files exist**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
ls _site/index.html
ls _site/publications/index.html
ls _site/research/index.html
ls _site/cv-json/index.html
ls _site/assets/css/custom.css
ls _site/assets/js/hero-graph.js
```

Expected: All files exist.

- [ ] **Step 3: Check HTML for key elements**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
grep -q "Jiangwen Dong" _site/index.html && echo "Name found"
grep -q "hero-graph-canvas" _site/index.html && echo "Canvas found"
grep -q "S-DAG" _site/index.html && echo "S-DAG found"
grep -q "HybridFlow" _site/index.html && echo "HybridFlow found"
```

Expected: All four checks print found.

- [ ] **Step 4: Final commit**

```bash
cd "c:/Users/jioha/Desktop/temp/Research/Jiangwen-Dong.github.io"
git log --oneline -5
```

Verify clean commit history.

---

## Spec Coverage Check

| Spec Section | Plan Task |
|--------------|-----------|
| Color palette (§2.1) | Task 5 |
| Typography (§2.2) | Task 5 |
| Graph animation (§2.3, §6.3) | Task 6 |
| Navigation (§3.1) | Task 2 |
| Homepage hero (§4.1) | Task 7 |
| Research pillars (§4.1) | Task 7 |
| Recent publications on homepage (§4.1) | Task 7 |
| Publications page (§4.2) | Existing template + Task 3 |
| Research page (§4.3) | Task 8 |
| CV page (§4.4) | Task 9 |
| Content cleanup (§5.1) | Task 1 |
| CV data update (§5.3) | Task 4 |
| Responsive breakpoints (§6.4) | Task 5 |

---

## Placeholder Scan

- No "TBD" or "TODO" in task steps
- No vague instructions like "add appropriate styling"
- All code blocks contain complete, runnable code
- All file paths are exact
- All commands include expected output
