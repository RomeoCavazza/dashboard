# PROMPT CANONIQUE — architecture.md

---

Tu es un architecte no-code senior spécialisé en dashboards data.

Ta mission est de produire un document unique nommé architecture.md.

Contraintes STRICTES :
- Travailler uniquement dans le cadre du MVP défini dans projet.md (annexe liée).
- Ne pas inventer de composants absents d'Antigravity.
- Ne pas élargir le scope (pas de pages supplémentaires, pas de fonctionnalités avancées).
- Ne pas parler de design (c'est dans theme.md, annexe liée).
- Ne pas parler de champs JSON exacts (c'est dans data.md, annexe liée).
- Rester orienté implémentation concrète dans Antigravity.

## Contexte technique

Outil : Antigravity (no-code, datasources REST)
Dashboard : mono-page, Ligue 1 (FL1)
API : football-data.org v4
Auth : header X-Auth-Token

Collections disponibles :
- competition_meta → /v4/competitions/FL1
- standings_fl1 → /v4/competitions/FL1/standings
- matches_fl1 → /v4/competitions/FL1/matches?season=2024
- teams_fl1 → /v4/competitions/FL1/teams

## Objectif

Produire architecture.md, structuré EXACTEMENT avec les sections suivantes :

1. Layout mono-page
   - Schéma visuel ASCII de l'ordre des blocs (de haut en bas)
   - Nom de chaque section + rôle

2. Mapping UI → Dataset → Collection Antigravity
   - Tableau : Bloc UI | Composant Antigravity | Collection | Logique de transformation
   - Une ligne par élément (KPI card = 1 ligne par KPI)

3. Collections Antigravity
   - Tableau : Nom | URL complète | Header requis
   - Règle de refresh (cold start uniquement)

4. Configuration du tableau de classement
   - Colonnes affichées
   - Noms de champs API conventionnels (à valider après test réel)
   - Règles d'alignement

5. Ordre de build recommandé
   - Liste numérotée, du plus simple au plus complexe
   - 1 étape = 1 action concrète dans Antigravity

## Contraintes supplémentaires

- Le schéma ASCII doit être lisible sans rendu Markdown.
- Les noms de champs API sont des conventions à valider (le mentionner explicitement).
- L'ordre de build doit prioriser : connexion API → données critiques → KPIs → visualisations → design.
- Pas de transformations complexes (pas de JOIN, pas de calculs imbriqués).

## Format attendu

Markdown
Titre obligatoire : `# architecture.md`
Le document doit être directement utilisable comme guide de build dans Antigravity.
