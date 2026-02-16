# Dashboard Ligue 1

Dashboard mono-page de visualisation des données de la **Ligue 1 (FL1)**.
Construit en **no-code avec Antigravity**, design inspiré de **FootX**.

---

## Scope

| | |
|---|---|
| Compétition | Ligue 1 — code API : `FL1` |
| Source de données | football-data.org v4 |
| Outil no-code | Antigravity |
| Référence UI | FootX |
| Type | Mono-page, MVP uniquement |
| Contexte | Projet académique — Ynov |

---

## Structure du repo

```
Dashboard/
├── 01_strategie/       Définition projet, périmètre MVP, blocs fonctionnels
├── 02_design/          Système de couleurs, typographie, références visuelles FootX
├── 03_data/            Mapping API, documentation endpoints, collection Postman
├── 04_implementation/  Setup Antigravity, exports, screenshots de build
│   ├── dashboard/      Code source du dashboard (HTML/CSS/JS)
│   └── docs/           Documentation consolidée
├── 05_prompts/         Prompts de cadrage par domaine + captures sessions IA
├── 06_documentation/   Rétrospective, méthodo, notes vibe coding
└── README.md
```

---

## Source de données

**API football-data.org v4** — Plan gratuit

| Endpoint | Usage |
|---|---|
| `/v4/competitions/FL1` | Infos générales de la compétition |
| `/v4/competitions/FL1/standings` | Classement général |
| `/v4/competitions/FL1/matches` | Matchs et scores par journée |

Authentification : header `X-Auth-Token` requis.
Limite : 10 requêtes/minute. Pas de données live.

---

## Structure du projet

```
/
├── api/                # Vercel Serverless Functions (Proxy)
├── public/             # Static Assets (HTML, CSS, JS)
├── server.js           # Local Development Server
├── package.json        # Project Dependencies
└── README.md           # Documentation
```

## Setup & Installation

1.  **Clone the repository**
2.  **Install dependencies**
    ```bash
    npm install
    ```
3.  **Run locally**
    ```bash
    npm start
    ```


---

## Sections du dashboard

| Section | Composant Antigravity | Données |
|---|---|---|
| Header compétition | Texte statique + image | `competitions/FL1` |
| KPIs globaux (×5) | KPI card | `standings` + `matches` |
| Classement général | Table | `standings` |
| Top 5 équipes (points) | Bar chart horizontal | `standings` |
| Meilleures attaques | Bar chart horizontal | `standings` |
| Meilleures défenses | Bar chart horizontal | `standings` |
| Buts par journée | Histogramme | `matches` |
| Footer source | Texte statique | — |

---

## État du projet

✅ **Terminé & Déployé** 🚀

### Fonctionnalités implémentées
- [x] Cadrage & Design System (`01_strategie`, `02_design`)
- [x] Data Engineering & Proxy API (`03_data`, `ap/proxy.js`)
- [x] Dashboard complet (`04_implementation/dashboard`)
    - Header dynamique
    - KPIs temps réel
    - Classement officiel (points, diff, V/N/D)
    - Graphiques (Top 5)
    - Mode sombre responsive

## Déploiement

Le projet est conçu pour être déployé sur **Vercel** :
1. Importer le repo.
2. Définir le dossier racine sur `04_IMPLEMENTATION/dashboard`.
3. Ajouter la variable d'environnement `API_KEY`.
4. Deploy !
