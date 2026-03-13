<!-- markdownlint-disable MD033 -->
<div align="center">
  <img src="public/logo_ligue1.png" alt="Ligue 1 Logo" width="450" />
</div>
<!-- markdownlint-enable MD033 -->

# Case Study: Dynamic Ligue 1 Dashboard (Vibe Coding)

This document is the **definitive, step-by-step master handbook** for the Ligue 1 Dashboard project. It traces the entire journey from the initial strategic concept to the final live application. Developed following the **Vibe Coding** philosophy, this project was orchestrated by AI via the **Antigravity** toolset.

---

## 1. Strategic Framing & Project Vision

The first step of any Vibe Coding project is setting a rigid "Intention." We defined our scope as a single-page MVP (Most Valuable Product) that delivers high-density football data with a premium "Sport-Tech" feel.

> [!IMPORTANT]
> **Technical Bound**: We explicitly restricted the project to a single-view dashboard. By avoiding feature creep (no player searches, no team profiles), we ensured a polished and functional delivery within a record timeframe.

Resource: [projet.md](docs/I. Cadrage stratégique/projet.md) defines the core architecture and features.

---

## 2. Visual Research: The FootX Benchmark

To achieve a professional aesthetic, we used **FootX.fr** as our primary design reference. We didn't just look at it; we audited its information density and UI patterns across multiple sections.

### Benchmark Phase: Auditing the Reference
We captured the following specific views to guide our AI designer:

**Ref A: The Landing Experience**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_landing.png" alt="FootX Landing Page Reference" width="100%" />
</div>

**Ref B: The Ranking System (Ligue 1)**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_ranking.png" alt="FootX Ranking Reference" width="100%" />
</div>

**Ref C: Recent Match Results**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_results.png" alt="FootX Results Reference" width="100%" />
</div>

**Ref D: Upcoming Matches**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_upcoming.png" alt="FootX Upcoming Reference" width="100%" />
</div>

**Ref E: Deep Data & Value Picks**
<div align="center">
  <img src="docs/II. Créations graphiques/references/screenshots_footx/footx_data.png" alt="FootX Data Reference" width="100%" />
</div>

### Designing the "Vibe"
Using these captures, we prompted the AI to extract a coherent Design System.

<div align="center">
  <img src="docs/II. Créations graphiques/prompt_design.png" alt="AI-Driven Design Analysis" width="100%" />
</div>

> [!TIP]
> **Pro Tip**: Use the specific "Prompt Design Analysis" found in [prompt_design.md](docs/II. Créations graphiques/prompt_design.md) to replicate this process for any other reference site.

### The Final Design Tokens
The result is a dark, neon-accented theme that prioritizes legibility and data density.

<div align="center">
  <img src="docs/II. Créations graphiques/livrable.png" alt="Ligue 1 Dashboard Theme Deliverable" width="100%" />
</div>

---

## 3. Data Infrastructure: The API Portal

Our dashboard is "Smart"—it is fueled by real-time data from **football-data.org (v4)**.

### API Provider Discovery
We started by exploring the provider's ecosystem.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/api_quickstart_assets/logo.jpg" alt="Football Data API Provider" width="300" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_landing.png" alt="API Portal Home" width="100%" />
</div>

### Account Setup & Key Management
Every developer needs a unique `X-Auth-Token`.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_register.png" alt="API Registration Process" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_login.png" alt="Developer Login" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_profile.png" alt="Developer Profile" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_key.md.png" alt="API Key Management" width="100%" />
</div>

### Understanding Quotas & Technical Docs
We audited the free tier limits (10 requests/min) and studied the JSON endpoint documentation.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_pricing.png" alt="API Pricing and Limits Auditing" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_documentation.png" alt="Technical Documentation Study" width="100%" />
</div>

---

## 4. API Validation: The Postman Suite

Before writing the first line of code, we validated every single data point using **Postman**.

### Collection Setup
We imported the official football-data collection and configured our headers.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_postman_collection.png" alt="Finding the Postman Collection" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_postman_collection_save.png" alt="Saving API Collection" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_import.png" alt="Importing to Local Postman" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_url.png" alt="Configuring API Base URL" width="100%" />
</div>

### Exhaustive Endpoint Testing
We performed targeted calls to verify the structure of Ligue 1 (`FL1`) data.

**Step A: Verifying Competition Meta**
<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_get_competition.png" alt="Testing Competition Endpoint" width="100%" />
</div>

**Step B: Verifying League Standings**
<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_get_standings.png" alt="Testing Standings Endpoint" width="100%" />
</div>

**Step C: Verifying Match List**
<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_get_matches.png" alt="Testing Matches Endpoint" width="100%" />
</div>

**Step D: Verifying Teams & Icons**
<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_get_teams.png" alt="Testing Teams Endpoint" width="100%" />
</div>

### Data Sample Extraction
Finally, we exported the JSON results to our `mock/` folder to enable offline development.

<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_save_json.png" alt="Exporting JSON Samples" width="100%" />
</div>

---

## 5. Engineering the Solution

### Technical Architecture
The core system uses a **Vercel Serverless Function** as a proxy to keep our API key secure while delivering data to our Vanilla JS frontend.

<div align="center">
  <img src="docs/III. Architecture & API/livrable.png" alt="Technical Architecture Flow" width="100%" />
</div>

### Repository Scaffolding
We organized the repository using a strict hierarchy to maximize AI clarity.

```text
dashboard/
├── api/             # Secure Proxy
├── docs/            # Knowledge Base
├── public/          # Main UI (app.js, styles.css)
└── server.js        # Dev Server
```

---

## 6. Context Engineering: Orchestrating the AI

To build the dashboard, we provided the AI with two massive "Mega-Prompts" that contained the entire logic and design tokens.

**The Architecture Prompt**
<div align="center">
  <img src="docs/IV. Context Engineering/Contexte/prompt_architecture.png" alt="Scaffolding and Logic Prompt" width="100%" />
</div>

**The Data Mapping Prompt**
<div align="center">
  <img src="docs/IV. Context Engineering/Contexte/prompt_data.png" alt="Data Structure and Mapping Prompt" width="100%" />
</div>

---

## 7. The Final Build: Result & Outcomes

The result is a blazing fast, data-dense dashboard that respects every design token from our FootX benchmark.

<div align="center">
  <img src="docs/V. Vibecoding/Livrable.png" alt="Final Dynamic Dashboard Deliverable" width="100%" />
</div>

---

## Deployment & Resources

- **Source Code**: Explore `/public` for the UI and `/api` for the proxy.
- **Specifications**: [architecture.md](docs/III. Architecture & API/architecture.md) | [theme.md](docs/II. Créations graphiques/theme.md)
- **Status**: Production-ready, deployed on Vercel.

---

<p align="center">
  <i>"Football Data, Refined by Vibe Coding." — Documented by Antigravity.</i>
</p>
