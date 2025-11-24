# ResQ - Système de Dispatching d'Ambulances

## 📋 Description

ResQ est une application web de gestion et de dispatching d'ambulances en temps réel. Elle permet aux opérateurs de régulation de gérer efficacement la flotte d'ambulances, les incidents d'urgence, et d'optimiser les interventions grâce à une interface cartographique intuitive et des outils d'aide à la décision.

## ✨ Fonctionnalités Principales

### 🗺️ Cartographie Interactive
- Visualisation en temps réel de la position des ambulances
- Affichage des incidents avec codes couleur selon la gravité
- Popups d'information détaillées au clic
- Filtres d'affichage et outils de navigation (zoom, centrage)

### 🚨 Gestion des Incidents
- Création d'incidents avec formulaire de saisie structuré
- Assignation intelligente des ambulances (calcul distance/ETA)
- Suivi en temps réel des statuts (En attente → En cours → Terminé)
- Notifications visuelles pour les incidents critiques

### 📊 Dashboard & Monitoring
- KPIs en temps réel (ambulances disponibles, incidents actifs, temps de réponse)
- Graphiques de performance et charge de travail
- Flux d'activité avec historique des actions récentes

### 🚑 Gestion de Flotte
- Vue tabulaire complète des véhicules
- Gestion des statuts (En service, Pause, Maintenance)
- Administration des équipements et équipages

## 🛠️ Stack Technique

- **Frontend Framework**: React 18 + TypeScript
- **Build Tool**: Vite
- **State Management**: Redux Toolkit
- **Data Fetching**: TanStack Query (React Query)
- **Mapping**: React-Leaflet
- **UI Components**: Tailwind CSS + Shadcn/ui
- **Forms**: React Hook Form + Zod
- **Backend Mock**: JSON Server

## 📦 Prérequis

- Node.js >= 18.0.0
- npm >= 9.0.0

## 🚀 Installation

### 1. Cloner le projet

```bash
git clone https://github.com/Keltoummalouki/ResQ
cd resq
```

### 2. Installer les dépendances

```bash
npm install
```

### 3. Installer JSON Server (globalement)

```bash
npm install -g json-server
```

### 4. Configuration de l'environnement

Créer un fichier `.env` à la racine du projet :

```env
VITE_API_URL=http://localhost:5000
VITE_MAP_CENTER_LAT=48.8566
VITE_MAP_CENTER_LNG=2.3522
VITE_MAP_DEFAULT_ZOOM=12
```

## 🎯 Démarrage

### Lancer le serveur API (JSON Server)

```bash
json-server --watch db.json --port 5000
```

### Lancer l'application en mode développement

```bash
npm run dev
```

L'application sera accessible sur `http://localhost:5173`

## 📁 Structure du Projet

```
resq/
├── src/
│   ├── components/
│   │   ├── ui/              # Composants UI réutilisables (Shadcn)
│   │   ├── map/             # Composants cartographiques
│   │   ├── dashboard/       # Composants du tableau de bord
│   │   ├── fleet/           # Composants de gestion de flotte
│   │   └── incidents/       # Composants de gestion d'incidents
│   ├── pages/
│   │   ├── Dashboard.tsx    # Page tableau de bord
│   │   ├── DispatchMap.tsx  # Page carte de dispatching
│   │   ├── Fleet.tsx        # Page gestion de flotte
│   │   └── Incidents.tsx    # Page historique incidents
│   ├── store/
│   │   ├── slices/          # Redux slices
│   │   └── store.ts         # Configuration Redux
│   ├── hooks/               # Custom hooks
│   ├── services/            # Services API
│   ├── types/               # Types TypeScript
│   ├── utils/               # Utilitaires
│   └── App.tsx              # Composant racine
├── db.json                  # Base de données JSON Server
├── package.json
├── tsconfig.json
├── vite.config.ts
└── tailwind.config.js
```

## 🎨 Pages de l'Application

### Dashboard (`/`)
Vue d'ensemble avec KPIs, graphiques de performance et flux d'activité

### Carte de Dispatching (`/map`)
Interface opérationnelle principale avec carte interactive et panneau de gestion

### Gestion de Flotte (`/fleet`)
Administration des véhicules et de leurs statuts

### Historique Incidents (`/incidents`)
Journal complet des interventions passées avec filtres

## 👥 User Stories

### Régulateur
- Visualiser la position des ambulances sur la carte
- Créer et gérer des incidents d'urgence
- Assigner des ambulances aux incidents
- Filtrer les ressources par statut
- Consulter l'historique des interventions

### Chef de Parc
- Superviser l'état de la flotte
- Gérer la disponibilité des véhicules
- Ajouter/retirer des véhicules de la flotte active

## 🔧 Scripts Disponibles

```bash
npm run dev          # Démarre le serveur de développement
npm run build        # Build de production
npm run preview      # Prévisualisation du build
npm run lint         # Vérification ESLint
npm run type-check   # Vérification TypeScript
```

## 🧪 Tests

```bash
npm run test         # Lancer les tests
npm run test:watch   # Tests en mode watch
npm run test:coverage # Rapport de couverture
```

## 📝 Bonnes Pratiques

- **Validation**: Toutes les entrées utilisateur sont validées avec Zod
- **Performance**: Lazy loading des composants lourds (cartes)
- **Sécurité**: Ségrégation des configurations via variables d'environnement
- **Architecture**: Composants atomiques réutilisables (Atomic Design)
- **State Management**: Flux de données unidirectionnel via Redux

## 🤝 Contribution

1. Créer une branche feature (`git checkout -b feature/AmazingFeature`)
2. Commit les changements (`git commit -m 'Add some AmazingFeature'`)
3. Push vers la branche (`git push origin feature/AmazingFeature`)
4. Ouvrir une Pull Request

## 📄 Licence

Ce projet est sous licence MIT.

## 👨‍💻 Auteur

Développé dans le cadre du référentiel **Concepteur⋅rice développeur⋅se d'applications [2025]**

## 📞 Support

Pour toute question ou problème, veuillez ouvrir une issue sur le repository.

---

**Note**: Ce projet utilise JSON Server pour simuler une API REST. En production, remplacer par une vraie API backend.
