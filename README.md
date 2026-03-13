<!-- markdownlint-disable MD033 -->
<div align="center">
  <img src="public/logo_ligue1.png" alt="Ligue 1 Logo" width="200" />
</div>
<!-- markdownlint-enable MD033 -->

# Cas d'usage : Créer un tableau de bord dynamique avec la Vibe Coding

Dans ce cas d'usage, nous allons créer un tableau de bord dynamique qui affiche les scores de la **Ligue 1** de football en récupérant les données auprès d'une API. Comme pour les précédents cas d'usage, nous allons procéder étape par étape et utiliser un nouvel outil : **Antigravity de Google**.

---

## Préambule

Avant de détailler chacune des étapes de la conception et de la création de ce tableau de bord, il nous semble essentiel de préciser plusieurs points :

- **Les modèles et chatbots évoluent très régulièrement.** Tout ce qui est présenté dans cette capsule est susceptible d'avoir changé lorsque vous parcourrez ce tutoriel.
- **Le Vibe Coding est avant tout une philosophie.** Cette pratique correspond à des besoins ponctuels ou du prototypage rapide (MVP).
- **Chaque demande génère une réponse différente.** L'important est l'échange productif avec le chatbot.

---

## 1. Cadrage stratégique et intention

La première étape consiste à définir précisément ce que nous voulons construire. Nous utilisons Gemini pour cadrer le projet et définir le périmètre du MVP (Most Valuable Product).

---

## 2. Définition de l'intention graphique

Pour donner une âme à notre dashboard, nous nous inspirons des codes visuels du site **FootX.fr**. Nous analysons l'esthétique "Sport-Tech" (Dark mode, accents néons).

### Analyse de la référence visuelle
Nous commençons par capturer l'essence de FootX pour guider notre design.

<div align="center">
  <img src="docs/II. Créations graphiques/references/livrable.png" alt="Inspiration FootX" width="100%" />
</div>

### Extraction des tokens de design
Nous utilisons un prompt spécifique pour demander à l'IA d'analyser les couleurs et la typographie à partir des captures.

<div align="center">
  <img src="docs/II. Créations graphiques/prompt_design.png" alt="Prompt Design Analysis" width="100%" />
</div>

### Validation du thème visuel
Le document de thème est finalisé, fixant le background anthracite et les accents vert néon.

<div align="center">
  <img src="docs/II. Créations graphiques/livrable.png" alt="Final Design Theme" width="100%" />
</div>

---

## 3. Mise en place de la source de données (API)

Notre dashboard repose sur les données en temps réel de **football-data.org**. Cette étape est cruciale pour comprendre comment récupérer les informations.

### Exploration du fournisseur de données
Nous nous rendons sur la plateforme pour comprendre le fonctionnement de l'API.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/api_quickstart_assets/logo.jpg" alt="Football Data API" width="300" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_landing.png" alt="API Website Landing" width="100%" />
</div>

### Création du compte développeur
L'inscription est nécessaire pour obtenir une clé d'accès (API Key).

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_register.png" alt="API Registration" width="100%" />
</div>

### Connexion et gestion du profil
Une fois inscrit, nous accédons à notre espace personnel.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_login.png" alt="API Login" width="100%" />
</div>

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_profile.png" alt="User Profile" width="100%" />
</div>

### Récupération de la clé API
C'est cette clé (`X-Auth-Token`) qui nous permettra d'authentifier nos requêtes.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_key.md.png" alt="API Key Management" width="100%" />
</div>

### Analyse des limites et de la tarification
Nous vérifions les quotas du plan gratuit (10 requêtes par minute) pour adapter notre code.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_pricing.png" alt="API Pricing and Limits" width="100%" />
</div>

### Consultation de la documentation technique
Nous étudions les endpoints disponibles, notamment pour la Ligue 1 (`FL1`).

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_documentation.png" alt="Technical Documentation" width="100%" />
</div>

---

## 4. Validation et test des données avec Postman

Avant de coder, nous testons les réponses de l'API avec Postman pour nous assurer de la structure des données JSON.

### Utilisation de la collection officielle
Nous récupérons le lien de la collection Postman fournie par l'API.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_postman_collection.png" alt="Postman Collection Link" width="100%" />
</div>

### Sauvegarde et préparation
Nous préparons l'importation de la collection dans notre espace de travail.

<div align="center">
  <img src="docs/III. Architecture & API/api_docs/screenshots/api_postman_collection_save.png" alt="Saving Collection" width="100%" />
</div>

### Importation dans Postman
Nous configurons la collection pour utiliser notre clé d'API.

<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_import.png" alt="Importing to Postman" width="100%" />
</div>

### Test de récupération de la compétition
Nous vérifions que nous pouvons accéder aux informations générales de la Ligue 1.

<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_get_competition.png" alt="API Call: Competition" width="100%" />
</div>

### Test de récupération du classement
Nous validons la structure du tableau des scores pour pouvoir le mapper correctement dans notre UI.

<div align="center">
  <img src="docs/III. Architecture & API/postman/screenshots/postman_get_standings.png" alt="API Call: Standings" width="100%" />
</div>

---

## 5. Architecture technique et schéma de flux

Nous formalisons maintenant l'architecture de l'application : comment les données circulent de l'API vers le dashboard via un serveur proxy.

<div align="center">
  <img src="docs/III. Architecture & API/livrable.png" alt="Architecture Diagram" width="100%" />
</div>

---

## 6. Context Engineering : Préparation de l'IA

Nous fournissons à l'agent IA (Antigravity) tout le contexte nécessaire : design, données et architecture.

### Prompt de structure technique
Nous demandons à l'IA d'organiser le code en respectant les schémas définis.

<div align="center">
  <img src="docs/IV. Context Engineering/Contexte/prompt_architecture.png" alt="Architecture Prompt" width="100%" />
</div>

### Prompt de mapping de données
Nous transmettons les échantillons JSON pour que l'IA génère les bonnes fonctions de récupération.

<div align="center">
  <img src="docs/IV. Context Engineering/Contexte/prompt_data.png" alt="Data Mapping Prompt" width="100%" />
</div>

---

## 7. Build et Vibe Coding final

C'est ici que la magie opère. L'IA assemble tous les composants pour créer le livrable final.

### Résultat de la génération
Le dashboard est prêt, dynamique et fidèle au design de référence.

<div align="center">
  <img src="docs/V. Vibecoding/Livrable.png" alt="Final Dashboard Delivery" width="100%" />
</div>

---

## Déploiement

L'application est finalement versionnée sur **GitHub** et déployée sur **Vercel** pour être accessible par tous.

<p align="center">
  <i>"Football Data, Refined by Vibe Coding."</i>
</p>
