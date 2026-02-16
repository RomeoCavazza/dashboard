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

## Comment reproduire (high-level)

1. **Clé API** — Créer un compte sur football-data.org, récupérer le token
2. **Tester les endpoints** — Importer `03_data/postman/postman_collection.customization` dans Postman
3. **Inspecter le JSON** — Identifier les champs exacts pour le mapping (voir `03_data/data.md`)
4. **Créer la page Antigravity** — Connecter l'API avec `X-Auth-Token` en header
5. **Construire les blocs** — Header → KPIs → Standings → Graphiques → Footer
6. **Appliquer le thème** — Palette dark définie dans `02_design/theme.md`

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
