<!-- markdownlint-disable MD033 -->
<div align="center">
  <img src="public/logo_ligue1.png" alt="Ligue 1 Logo" width="450" />
</div>
<!-- markdownlint-enable MD033 -->

# Case Study: Dynamic Ligue 1 Dashboard (Vibe Coding)

This document is the **complete chronological documentary** of the Ligue 1 Dashboard project. It follows the **Vibe Coding** philosophy—a paradigm where AI orchestrates the entire lifecycle of a product, from strategic framing to deployment.

This README is designed as an educational tutorial, showcasing every prompt, every technical decision, and every visual asset used to build this high-performance data application.

---

## Technical Stack

| Category | Technology Stack |
|---|---|
| **Frontend** | Vanilla JavaScript, CSS3 (Custom Design System), HTML5 |
| **Backend** | Node.js (Vercel Serverless Functions) |
| **Data Source** | [football-data.org](https://api.football-data.org/v4) API (v4) |
| **Orchestration** | Antigravity AI Agentic System |

---

## I. Strategic Framing (Axis 1)

The mission: Create a **single-page dashboard** for the French Ligue 1, focusing on real-time data visualization and a premium "Sport-Tech" aesthetic.

### 1. Project Specifications
We defined the project guardrails in the [projet.md](docs/I. Cadrage stratégique/projet.md) file to prevent "feature creep" and ensure a polished MVP delivery.

> [!IMPORTANT]
> **MVP Scope**: 
> - Single view experience.
> - High-density KPIs.
> - Dynamic Standings Table.
> - 4 Key Statistical Visualizations.
> - **Zero** complex navigation or secondary pages.

### 2. Strategic Deliverable
The roadmap was synthesized into a visual framing document.

<div align="center">
  <img src="docs/I. Cadrage stratégique/Livrable.png" alt="Strategic Framing Deliverable" width="100%" />
</div>

---

## II. Visual Creations & UI/UX (Axis 2)

We chose a "Dark Sport-Tech" aesthetic, heavily inspired by professional sports data portals like **FootX.fr**.

### 1. Benchmarking the Reference (FootX)
We performed an exhaustive audit of FootX's UI patterns to extract its "Data DNA."

**Ref 1: Home Narrative Page**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_landing.png" alt="FootX Landing Page Benchmark" width="100%" />
</div>

**Ref 2: Ligue 1 Ranking Structure**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_ranking.png" alt="FootX Ranking Table Benchmark" width="100%" />
</div>

**Ref 3: Recent Results Density**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_results.png" alt="FootX Results Benchmark" width="100%" />
</div>

**Ref 4: Upcoming Match Cards**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_upcoming.png" alt="FootX Upcoming Matches Benchmark" width="100%" />
</div>

**Ref 5: Advanced Data Analysis**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_data.png" alt="FootX Analysis Benchmark" width="100%" />
</div>

### 2. Design System Engineering
Based on these assets, we generated the [theme.md](docs/II. Créations graphiques/theme.md) document using a "Canonical UI Prompt."

**The Canonical Prompt Excerpt:**
> "You are a UI/UX expert specializing in dark-mode data dashboards. Produce a `theme.md` document based *only* on the provided FootX captures. Define HEX colors, typography scales, and component specifications."

<div align="center">
  <img src="docs/II. Créations graphiques/prompt_design.png" alt="UI Prompt Engineering Process" width="100%" />
</div>

### 3. Final Design Tokens
The result is a strict set of design tokens that power the entire CSS layer.

<div align="center">
  <img src="docs/II. Créations graphiques/livrable.png" alt="Final Design System Deliverable" width="100%" />
</div>

**Primary Palette:**
- **Background**: `#0B0D10` (Deep Space Dark)
- **Accents**: `#00E676` (Neo Green), `#2979FF` (Energy Blue)
- **Text**: `#F5F7FA` (High Contrast White)

---

## III. Data Architecture & API (Axis 3)

The dashboard is "Live-Mocked": it uses real production data but optimizes it for performance via local caching and proxying.

### 1. API Discovery & Credentials
We explored the **football-data.org** portal to secure an `X-Auth-Token`.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/api_quickstart_assets/logo.jpg" alt="API Provider Exploration" width="300" />
</div>

**Registration Process:**
<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_landing.png" alt="API Portal Home" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_register.png" alt="API Registration Flow" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_key.md.png" alt="API Key Management" width="100%" />
</div>

> [!CAUTION]
> **API Limits Audit**: The free tier restricts usage to **10 calls per minute**. Our architecture implements a "Batch and Static" loading strategy to never trigger 429 errors.

### 2. Postman Validation Suite
We validated the raw JSON structures before writing any code.

**Step A: Testing League Meta**
<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_get_competition.png" alt="Postman Call: Competition Meta" width="100%" />
</div>

**Step B: Testing Standings Complexity**
<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_get_standings.png" alt="Postman Call: Team Standings" width="100%" />
</div>

**Step C: Validating Teams & Icons**
<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_get_teams.png" alt="Postman Call: Team Assets" width="100%" />
</div>

**Exporting JSON Samples:**
We saved the production responses to verify keys like `goalsFor`, `points`, and `crest`.
[Access Samples Folder](docs/III. Architecture & API/postman/samples/)

### 3. Technical Blueprint
The [architecture.md](docs/III. Architecture & API/architecture.md) maps every API field to its UI counterpart.

<div align="center">
  <img src="docs/III. Architecture & API/livrable.png" alt="Technical Architecture Mapping" width="100%" />
</div>

---

## IV. Context Engineering (Axis 4)

We scaffolded the project to provide the AI agent with a perfect internal structure.

### 1. Project Repository Tree
The final arborescence follows a modular approach.

```text
dashboard/
├── api/             # Vercel Serverless Proxy
├── docs/            # Strategic Knowledge Base
├── public/          # Main Interface
│   ├── app.js       # Logic Engine
│   ├── index.html   # Main Structure
│   └── style.css    # Design System Implementation
└── server.js        # Local Development Node Server
```

### 2. Building the "Mental Map" for AI
We used "Mega-Prompts" to inject the technical and strategic context into the coding agent.

**Prompt A: The Global Architecture**
<div align="center">
  <img src="docs/IV. Context Engineering/Contexte/prompt_architecture.png" alt="Architecture Injection Prompt" width="100%" />
</div>

**Prompt B: The Data Mapping Engine**
<div align="center">
  <img src="docs/IV. Context Engineering/Contexte/prompt_data.png" alt="Data Mapping Logic Prompt" width="100%" />
</div>

---

## V. Vibe Coding Implementation (Axis 5)

The implementation was done in phases, moving from the "Invisible" (Backend) to the "Visible" (Frontend).

### 1. The Secure Proxy (`api/proxy.js`)
We hid the API key in environment variables and routed all requests through a Vercel Function.

```javascript
export default async function handler(req, res) {
    const { endpoint } = req.query;
    const API_KEY = process.env.API_KEY;
    const response = await fetch(`https://api.football-data.org/v4${endpoint}`, {
        headers: { 'X-Auth-Token': API_KEY }
    });
    const data = await response.json();
    res.status(200).json(data);
}
```

### 2. The Data Engine (`public/app.js`)
A monolithic logic layer that handles fetching, mapping, and rendering.

```javascript
async function loadDashboard() {
    const standings = await fetchAPI('/competitions/FL1/standings');
    const matches = await fetchAPI('/competitions/FL1/matches?season=2025');
    
    renderKPIs(standings, matches);
    renderTable(standings);
    renderCharts(standings, matches);
}
```

### 3. The Design Layer (`public/style.css`)
Applying the [theme.md](docs/II. Créations graphiques/theme.md) tokens via CSS variables.

```css
:root {
  --bg-primary: #0B0D10;
  --surface-1: #161A1F;
  --accent-primary: #00E676;
}

.kpi-card {
  background: var(--surface-1);
  border: 1px solid var(--border-default);
}
```

---

## VI. Final Delivery & Deployment

The project is live on Vercel, synchronized with a private GitHub repository for continuous integration.

### Final Dashboard View
The application delivers on every promise: high density, premium aesthetics, and real-time accuracy.

<div align="center">
  <img src="docs/V. Vibecoding/Livrable.png" alt="Final Dynamic Dashboard" width="100%" />
</div>

---

## Technical Resources

- **Full Documentation Portal**: [docs/README.md](docs/README.md)
- **API Reference**: [docs/III. Architecture & API/architecture.md](docs/III. Architecture & API/architecture.md)
- **UI Specification**: [docs/II. Créations graphiques/theme.md](docs/II. Créations graphiques/theme.md)

---
<p align="center">
  <i>"Football Data, Defined by Strategy, Pushed by Vibe." — Documented by Antigravity.</i>
</p>
