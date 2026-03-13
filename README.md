<!-- markdownlint-disable MD033 -->
<div align="center">
  <img src="public/logo_ligue1.png" alt="Ligue 1 Logo" width="450" />
  <br />
  <img src="https://img.shields.io/badge/Architecture-Vibe_Coding-6366f1?style=for-the-badge" alt="Architecture Badge" />
  <img src="https://img.shields.io/badge/Visuals-Midjourney-00e676?style=for-the-badge" alt="Visuals Badge" />
  <img src="https://img.shields.io/badge/Stack-Vanilla_JS-f7df1e?style=for-the-badge" alt="Stack Badge" />
  <img src="https://img.shields.io/badge/API-Football_Data-2979ff?style=for-the-badge" alt="API Badge" />
</div>
<!-- markdownlint-enable MD033 -->

# Master Course: Dynamic Ligue 1 Dashboard

Welcome to the **complete chronological handbook** for the Ligue 1 Dashboard project. This project is not just a dashboard—it is a live demonstration of the **Vibe Coding** philosophy. It shows how an AI developer (Antigravity) orchestrates the entire lifecycle of a tech product: from market framing and UI audit to fullstack development and industrial deployment.

---

## Technical Core

| Layer | Implementation |
|---|---|
| **Philosophy** | ![Vibe Coding](https://img.shields.io/badge/Philosophy-Vibe_Coding-6366f1?style=flat-square) |
| **Interface** | ![Vanilla JS](https://img.shields.io/badge/Interface-Vanilla_JS-f7df1e?style=flat-square) ![CSS3](https://img.shields.io/badge/Style-CSS3-1572b6?style=flat-square) |
| **Security** | ![Vercel Proxy](https://img.shields.io/badge/Security-Vercel_Proxy-000000?style=flat-square) |
| **Data Engine** | ![API v4](https://img.shields.io/badge/Data-API_v4-2979ff?style=flat-square) |

---

## I. Strategic Framing (Phase 1)

Every project begins with a clear **Intention**. We refused "Feature Creep" and defined a strict MVP scope to ensure a premium delivery within record time. This phase is crucial as it sets the boundaries for the AI and the developer.

### 1. Project Specifications
We established our guardrails in the [projet.md](docs/I.%20Cadrage%20strat%C3%A9gique/projet.md) file. This document acts as the "Contract" between the strategy and the execution. The goal was to build a single-page, high-density dashboard for the French Ligue 1.

> [!IMPORTANT]
> **MVP Scope Definition**: 
> - Single view experience (no sub-pages).
> - High-density KPIs for instant reading.
> - Dynamic Standings Table with real-time API binding.
> - 4 Key Statistical Visualizations (Bar charts & Histograms).
> - **Zero** complex navigation to maintain speed and focus.

### 2. Strategic Deliverable
All the strategic research was synthesized into a visual framing document that allows the team to align on the final product vision before any code is written.

<div align="center">
  <img src="docs/V.%20Vibecoding/Livrable.png" alt="Strategic Framing Deliverable" width="100%" />
</div>

---

## II. Visual Audit: The FootX Benchmark (Phase 2)

To avoid a "generic" or "empty" feel, we audited **FootX.fr**, a gold standard in professional sports data visualization. We captured 5 key views to teach our AI the specific "Data DNA" of French football.

**Step 2.1: Analyzing the Landing Hierarchy**
The landing page audit helps us understand how to greet the user with immediate, high-value information.
<div align="center">
  <img src="docs/II.%20Cr%C3%A9ations%20graphiques/references/screenshots_footx/footx_landing.png" alt="FootX Landing Benchmark" width="100%" />
</div>

**Step 2.2: Auditing Data-Dense Tables**
Football fans crave density. We studied how FootX handles the Ligue 1 table to replicate its efficient use of horizontal space.
<div align="center">
  <img src="docs/II.%20Cr%C3%A9ations%20graphiques/references/screenshots_footx/footx_ranking.png" alt="FootX Ranking Benchmark" width="100%" />
</div>

**Step 2.3: Balancing Results & Performance**
We observed how recent match results are displayed with high contrast, ensuring that scores are the most visible element.
<div align="center">
  <img src="docs/II.%20Cr%C3%A9ations%20graphiques/references/screenshots_footx/footx_results.png" alt="FootX Results Benchmark" width="100%" />
</div>

**Step 2.4: Managing Upcoming Match Rhythm**
The upcoming schedule requires a "cleaner" look. We noted the use of team crests and timing info.
<div align="center">
  <img src="docs/II.%20Cr%C3%A9ations%20graphiques/references/screenshots_footx/footx_upcoming.png" alt="FootX Upcoming Matches Benchmark" width="100%" />
</div>

**Step 2.5: Deep Analytical Components**
Finally, we looked at advanced stats and "Value Picks" to see how to integrate secondary data without cluttering the main view.
<div align="center">
  <img src="docs/II.%20Cr%C3%A9ations%20graphiques/references/screenshots_footx/footx_data.png" alt="FootX Data Analysis Benchmark" width="100%" />
</div>

### Engineering the UI Prompt
We didn't just tell the AI to "make it dark." We provided an exhaustive audit prompt to extract specific tokens.

> [!TIP]
> **Mega-Prompt Restoration**: The full design audit prompt is saved in [prompt_design.md](docs/II.%20Cr%C3%A9ations%20graphiques/prompt_design.md). It instructs the AI to sample HEX codes, border radii, and spacing scales directly from the benchmark images.

**Step 2.6: The AI Design Analysis**
The AI processes the benchmark images and outputs a structured set of design rules.
<div align="center">
  <img src="docs/II.%20Cr%C3%A9ations%20graphiques/prompt_design.png" alt="AI UI Audit Workflow" width="100%" />
</div>

### The Final Design System
The result is [theme.md](docs/II.%20Cr%C3%A9ations%20graphiques/theme.md), which serves as our visual constitution throughout the build.

<div align="center">
  <img src="docs/II.%20Cr%C3%A9ations%20graphiques/livrable.png" alt="Final Design System" width="100%" />
</div>

---

## III. Data Infrastructure & API Validation (Phase 3)

The dashboard is "Live-Mocked": it uses real production data from the **football-data.org (v4)** API.

### Step-by-Step API Setup

**Step 3.1: Discovering the Provider**
We started by exploring the official provider website to understand the data availability for Ligue 1.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/api_docs/api_quickstart_assets/logo.jpg" alt="Provider Exploration" width="100%" />
</div>

**Step 3.2: Accessing the API Portal**
Navigating to the main developer portal to review the Quickstart guide and integration requirements.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/api_docs/screenshots/api_landing.png" alt="API Portal" width="100%" />
</div>

**Step 3.3: Account Registration**
Creating a developer account to obtain a unique `X-Auth-Token`.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/api_docs/screenshots/api_register.png" alt="API Registration" width="100%" />
</div>

**Step 3.4: Reviewing Usage Plans**
Auditing the "Free Tier" limitations. We noted that the 10 calls/min limit requires a smart caching strategy.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/api_docs/screenshots/api_pricing.png" alt="API Quotas & Pricing" width="100%" />
</div>

**Step 3.5: Accessing the Developer Profile**
Verifying the email and unlocking the personal dashboard for key management.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/api_docs/screenshots/api_profile.png" alt="User Profile" width="100%" />
</div>

**Step 3.6: Securing the API Key**
The final step of the setup is retrieving the `API_KEY` that will be used in our secure proxy.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/api_docs/screenshots/api_key.md.png" alt="API Key Management" width="100%" />
</div>

---

## IV. Postman Validation Suite (Phase 4)

Before writing a single line of code, we validated every JSON structure. This "Postman First" strategy ensures that our data models are 100% accurate.

### Step-by-Step Validation

**Step 4.1: Locating the Official Collection**
We found the official Postman collection provided by the API team to speed up our testing.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/api_docs/screenshots/api_postman_collection.png" alt="Postman Collection Discovery" width="100%" />
</div>

**Step 4.2: Importing the Environment**
We imported the collection into our local Postman workspace to begin customization.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/postman/screenshots/postman_import.png" alt="Collection Import" width="100%" />
</div>

**Step 4.3: Configuring Variables**
Setting the base URL and authentication headers to enable automated testing across all endpoints.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/postman/screenshots/postman_url.png" alt="Postman Config" width="100%" />
</div>

**Step 4.4: Testing Competition Metadata**
Verifying that we can correctly retrieve the Ligue 1 name, season, and current matchday.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/postman/screenshots/postman_get_competition.png" alt="Verifying Competition Meta" width="100%" />
</div>

**Step 4.5: Validating Standings & Statistics**
Ensuring the "Table" endpoint returns positions, points, and goal differences for all 18 teams.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/postman/screenshots/postman_get_standings.png" alt="Verifying League Standings" width="100%" />
</div>

**Step 4.6: Auditing Technical Assets**
Confirming that team crests (logos) are provided as valid URLs that our frontend can display.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/postman/screenshots/postman_get_teams.png" alt="Verifying Team Assets" width="100%" />
</div>

**Step 4.7: Exporting Production JSON Samples**
We saved the live responses into local JSON files to build a "Static Mock" and enable offline development.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/postman/screenshots/postman_save_json.png" alt="Saving JSON Mock Samples" width="100%" />
</div>

Check the exported samples here: [postman/samples/](docs/III.%20Architecture%20%26%20API/postman/samples/)

---

## V. Technical Blueprint (Phase 5)

We established the architecture using a decoupled client-proxy model to ensure security and performance.

### Request Flow Diagram (Mermaid)

```mermaid
graph LR
    U([Browser]) -- Requests --> P[Vercel Serverless Proxy]
    P -- Sanitizes & Appends Key --> A[Football-Data API]
    A -- JSON Response --> P
    P -- Cleaned Data --> U
```

### The Visual Mapping
We mapped every UI block to its respective API collection as defined in our [architecture.md](docs/III.%20Architecture%20%26%20API/architecture.md).

<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/livrable.png" alt="Data-to-UI Mapping Blueprint" width="100%" />
</div>

---

## VI. Context Engineering: Scaffolding (Phase 6)

We didn't just write files; we built a project structure that is "AI-Transparent," providing full clarity to the coding agent.

### Project Arborescence
```text
dashboard/
├── api/             # Vercel Secure Proxy (Node.js)
├── docs/            # Master Knowledge Base
├── public/          # Production UI
│   ├── app.js       # Data Hydration Engine
│   ├── index.html   # Semantic Structure
│   └── style.css    # Sport-Tech CSS System
└── server.js        # Local Dev Node Server
```

### The Scaffolding Prompts
To build this, we provided the AI with two massive logic injections.

**Step 6.1: Injecting Architecture Rules**
Providing the AI with the structural roadmap for file creation.
<div align="center">
  <img src="docs/IV.%20Context%20Engineering/Contexte/prompt_architecture.png" alt="Architecture Scaffolding Mega-Prompt" width="100%" />
</div>

**Step 6.2: Injecting Data Mapping Rules**
Defining exactly how keys from the API (like `playedGames`) should navigate into the DOM.
<div align="center">
  <img src="docs/IV.%20Context%20Engineering/Contexte/prompt_data.png" alt="Data Logic Mega-Prompt" width="100%" />
</div>

---

## VII. Build Implementation (Phase 7)

### Phase 7.1: The Secure API Proxy (`api/proxy.js`)
We hid the secret `API_KEY` in environment variables and created a Node runtime to bypass CORS issues and protect our credentials.

```javascript
/* Secure Backend Proxy Logic */
export default async function handler(req, res) {
    const { endpoint } = req.query;
    const API_KEY = process.env.API_KEY; // Managed by Vercel
    const response = await fetch(`https://api.football-data.org/v4${endpoint}`, {
        headers: { 'X-Auth-Token': API_KEY }
    });
    const data = await response.json();
    res.status(200).json(data);
}
```

### Phase 7.2: The Data Engine (`public/app.js`)
A centralized hydration engine that fetches data once on load and populates the dashboard components.

```javascript
/* High-Density Hydration Engine */
async function loadDashboard() {
    const standingsData = await apiFetch('/competitions/FL1/standings');
    const matchesData = await apiFetch('/competitions/FL1/matches?season=2025');
    
    renderKPIs(standingsData, matchesData);
    renderTable(standingsData);
    renderCharts(standingsData, matchesData);
}
```

### Phase 7.3: Applying Design Tokens (`public/style.css`)
We implemented the [theme.md](docs/II.%20Cr%C3%A9ations%20graphiques/theme.md) directly into the CSS using custom properties for instant styling updates.

```css
:root {
  --bg-primary: #0B0D10;
  --surface-1: #161A1F;
  --accent-primary: #00E676; /* The iconic Ligue 1 Green */
}

/* Dense Data Table Style */
.standings-table {
  width: 100%;
  background: var(--surface-1);
  border-collapse: collapse;
}
```

---

## VIII. Final Delivery & Deployment (Phase 8)

The result is a fully functional, high-density football dashboard that delivers on its professional visual promise.

<div align="center">
  <img src="docs/V.%20Vibecoding/Livrable.png" alt="Final Dashboard Delivery" width="100%" />
</div>

### Continuous Deployment
The project is live, synchronized with GitHub and deployed via Vercel for maximum reliability.

**Vercel Integration & Monitoring**
We audit the deployment status to ensure the API key is correctly injected in the production environment.
<div align="center">
  <img src="docs/III.%20Architecture%20%26%20API/vercel.png" alt="Vercel Monitoring" width="100%" />
</div>

**Live Sync with GitHub**
<div align="center">
  <img src="docs/V.%20Vibecoding/Deployement/vercel.png" alt="Live Deployment Success" width="100%" />
</div>

---

## Technical Resources

- **Framing Specification**: [docs/I.%20Cadrage%20strat%C3%A9gique/projet.md](docs/I.%20Cadrage%20strat%C3%A9gique/projet.md)
- **UI Architecture**: [docs/III.%20Architecture%20%26%20API/architecture.md](docs/III.%20Architecture%20%26%20API/architecture.md)
- **Design System**: [docs/II.%20Cr%C3%A9ations%20graphiques/theme.md](docs/II.%20Cr%C3%A9ations%20graphiques/theme.md)

---
<p align="center">
  <i>"Football Data, Defined by Strategy, Pushed by Vibe." — Course Documented by Antigravity.</i>
</p>
