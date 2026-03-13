<!-- markdownlint-enable MD033 -->
<div align="center">
  <img src="public/logo.png" alt="Ligue 1 Dashboard Logo" width="300" />
</div>
<!-- markdownlint-enable MD033 -->

## Overview

**Ligue 1 Dashboard** is a high-performance, single-page data visualization platform for French **Ligue 1 (FL1)** football statistics. This project was developed using a **No-Code/Vibe-Coding** methodology with Antigravity, featuring a premium design inspired by the **FootX** aesthetic.

- **Objective**: Rapidly prototyping a professional sports analytics MVP.
- **Data Source**: football-data.org v4 (Real-time integration via proxy).
- **Core Methodology**: No-code implementation with strategic custom serverless functions.
- **Documentation**: [**Technical Portal**](docs/README.md) (Specifications & Metrics).

### Structure

```text
Dashboard/
├── api/                # Vercel Serverless Functions (API Proxy)
├── public/             # Static Assets (HTML, CSS, JS)
├── server.js           # Local Development Server
├── docs/               # Technical Documentation Portal
└── 01_strategie/       # Project strategy & MVP scope
```

---

## Strategy & Scope

| Category | Detail |
| :--- | :--- |
| **Competition** | Ligue 1 (API Code: `FL1`) |
| **No-Code Platform** | Antigravity |
| **UI Reference** | FootX (Premium Dark Mode) |
| **Status** | ✅ Completed & Deployed |

---

## Technical Stack

![Antigravity](https://img.shields.io/badge/Platform-Antigravity-6366F1)
![Vercel](https://img.shields.io/badge/Hosting-Vercel-000000?logo=vercel&logoColor=white)
![JavaScript](https://img.shields.io/badge/Logic-JavaScript-F7DF1E?logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/Styling-FootX_CSS-1572B6?logo=css3&logoColor=white)

---

## Quick Start

### Installation

```bash
# Clone the repository
git clone https://github.com/RomeoCavazza/dashboard.git
cd dashboard

# Install dependencies
npm install

# Run locally
npm start
```

### Deployment

To deploy on **Vercel**:
1. Connect the repository.
2. Set the Root Directory to `04_implementation/dashboard`.
3. Configure the `API_KEY` environment variable.

---

## Dashboard Sections

| Section | Antigravity Block | Source Data |
| :--- | :--- | :--- |
| **Header** | competition-meta | `competitions/FL1` |
| **Global KPIs** | kpi-card-grid | `standings` + `matches` |
| **Official Standings** | data-table-dynamic | `standings` |
| **Top 5 Attack/Defense** | horizontal-bar-chart | `standings` |
| **Goals per Matchday** | histogram-v4 | `matches` |

---

## Skills Developed

- **No-Code Engineering**: Leveraging Antigravity for rapid UI assembly.
- **API Orchestration**: Building serverless proxies to handle third-party data securely.
- **Data Visualization**: Translating raw JSON into actionable bar charts and graphs.
- **Vibe Coding**: Rapidly iterating on design feedback to achieve a professional aesthetic.

---
<p align="center">
  <i>"Football Data, Refined."</i>
</p>
