# 🛋️ FurniFeedback

> *La voix de vos clients, au cœur de votre showroom.*

Plateforme web de collecte et d'analyse des retours clients après l'achat de meubles : satisfaction produit, qualité de livraison, expérience de montage et service après-vente.

---

![Build](https://img.shields.io/badge/build-passing-brightgreen)
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-yellow)
![Node](https://img.shields.io/badge/node-%3E%3D18.0.0-success)
![Contributions](https://img.shields.io/badge/contributions-welcome-orange)

---





## 📖 Description

Dans le secteur du mobilier, l'expérience client ne s'arrête pas à la vente : elle se prolonge à travers la livraison, le montage et l'usage quotidien du produit. Pourtant, beaucoup d'enseignes peinent à structurer ces retours et à en tirer des décisions concrètes.

**FurniFeedback** répond à cette problématique en proposant une solution clé en main pour :

- 📨 Solliciter automatiquement les clients après chaque achat
- 📊 Centraliser les avis dans un tableau de bord clair et exploitable
- 🎯 Identifier les axes d'amélioration produit et logistique
- 🤝 Renforcer la relation client grâce à un suivi personnalisé

**Public cible :** magasins de mobilier indépendants, chaînes de distribution, e-commerces spécialisés et fabricants souhaitant rapprocher leurs équipes du ressenti terrain.

---

## ✨ Fonctionnalités principales

- 📝 **Questionnaires post-achat** — envoi automatisé par e-mail ou SMS, avec relance configurable
- ⭐ **Notation multi-critères** — qualité du produit, livraison, montage, rapport qualité/prix, SAV
- 💬 **Commentaires libres** — collecte de verbatims pour une analyse qualitative
- 📈 **Tableau de bord analytique** — indicateurs en temps réel (NPS, CSAT, taux de réponse)
- 🗂️ **Gestion multi-rôles** — accès différenciés pour clients, vendeurs et administrateurs
- 📤 **Export des données** — formats CSV, Excel et PDF pour reporting
- 🔔 **Alertes intelligentes** — notification immédiate en cas d'avis négatif
- 🌍 **Multilingue** — interface disponible en français, anglais et arabe

---

## 🛠️ Stack technique

| Couche | Technologie |
|--------|-------------|
| **Frontend** | React 18, TypeScript, TailwindCSS |
| **Backend** | Node.js, Express, REST API |
| **Base de données** | PostgreSQL (données relationnelles) + Redis (cache) |
| **Authentification** | JWT + OAuth 2.0 |
| **Notifications** | Nodemailer (e-mail), Twilio (SMS) |
| **Tests** | Jest, React Testing Library |
| **CI/CD** | GitHub Actions |
| **Hébergement** | Docker, déployable sur Render, Railway ou AWS |

---

## 🏗️ Architecture

```
furnifeedback/
├── client/                 # Application React (interface utilisateur)
│   ├── src/
│   │   ├── components/     # Composants réutilisables
│   │   ├── pages/          # Pages (dashboard, formulaires, login)
│   │   └── services/       # Appels API
├── server/                 # API Node.js / Express
│   ├── controllers/        # Logique métier
│   ├── models/             # Schémas de données
│   ├── routes/             # Endpoints REST
│   └── middleware/         # Auth, validation, logs
├── database/               # Migrations et seeds PostgreSQL
├── docs/                   # Documentation technique
└── docker-compose.yml      # Orchestration des services
```

**Flux principal :** Vente enregistrée → Déclenchement du questionnaire → Réponse client → Stockage et analyse → Restitution sur le dashboard.

---

## 🚀 Prérequis et installation

### Prérequis

- Node.js ≥ 18
- PostgreSQL ≥ 14
- Docker (optionnel mais recommandé)

### Étapes d'installation

```bash
# 1. Cloner le dépôt
git clone https://github.com/<votre-utilisateur>/furnifeedback.git
cd furnifeedback

# 2. Installer les dépendances
npm install
cd client && npm install && cd ..

# 3. Configurer les variables d'environnement
cp .env.example .env
# Renseigner DB_URL, JWT_SECRET, SMTP_*, etc.

# 4. Initialiser la base de données
npm run db:migrate
npm run db:seed

# 5. Lancer l'application en mode développement
npm run dev
```

L'application sera disponible sur `http://localhost:3000` (front) et `http://localhost:5000` (API).

### Lancement via Docker

```bash
docker-compose up --build
```

---

## 💻 Utilisation

### Création d'une campagne de feedback

```bash
curl -X POST http://localhost:5000/api/campaigns \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"name": "Canapés - Été 2026", "delay_days": 7}'
```

### Aperçus de l'interface

> 📸 *Captures d'écran à venir*
>
> - `docs/screenshots/dashboard.png` — Tableau de bord
> - `docs/screenshots/survey.png` — Formulaire de satisfaction
> - `docs/screenshots/analytics.png` — Vue analytique

---

## 🗺️ Roadmap

- [x] MVP — questionnaires, dashboard, gestion des rôles
- [x] Export CSV / Excel
- [ ] 🤖 Analyse de sentiment automatique sur les commentaires (NLP)
- [ ] 🔗 Intégrations CRM (HubSpot, Salesforce, Odoo)
- [ ] 📱 Application mobile (React Native)
- [ ] 🛒 Connecteurs e-commerce (Shopify, WooCommerce, PrestaShop)
- [ ] 🧠 Recommandations IA pour répondre aux avis négatifs
- [ ] 📍 Géolocalisation des retours par point de vente

---

## 🤝 Contribution

Les contributions sont les bienvenues ! Pour participer :

1. **Fork** ce dépôt
2. Créer une branche : `git checkout -b feature/ma-fonctionnalite`
3. Commiter vos modifications : `git commit -m "Ajout : ..."`
4. Pousser la branche : `git push origin feature/ma-fonctionnalite`
5. Ouvrir une **Pull Request**

Merci de consulter [`CONTRIBUTING.md`](CONTRIBUTING.md) pour les conventions de code, et d'ouvrir une *issue* avant tout changement majeur.

---

## 📜 Licence

Ce projet est distribué sous licence **MIT**. Voir le fichier [`LICENSE`](LICENSE) pour plus de détails.

---

## 📬 Contact

- **Auteur :** *Votre Nom*
- **E-mail :** votre.email@exemple.com
- **GitHub :** [@votre-utilisateur](https://github.com/votre-utilisateur)
- **LinkedIn :** [linkedin.com/in/votre-profil](https://linkedin.com/in/votre-profil)

---

<p align="center">
  Conçu avec ❤️ pour rapprocher les artisans du mobilier de leurs clients.
</p>
