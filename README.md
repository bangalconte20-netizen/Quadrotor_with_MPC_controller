# Commande et Estimation d'État pour un Drone Quadrirotor en Simulation MATLAB

![Statut du projet](https://img.shields.io/badge/status-en--cours-yellow)
![Langage](https://img.shields.io/badge/langage-MATLAB-blue)
![Licence](https://img.shields.io/badge/licence-MIT-green)

Ce projet présente le développement d'un simulateur dynamique non-linéaire pour un drone quadrirotor et l'implémentation de stratégies de commande avancées. L'objectif est de valider en simulation des algorithmes de contrôle et d'estimation d'état applicables à des systèmes autonomes réels.

---

## 🚀 Démonstration

![GIF de la simulation](URL_DE_VOTRE_GIF_ICI.gif)

*(**CONSEIL IMPORTANT :** Créez un GIF animé de votre simulation qui montre le drone décollant et se stabilisant. C'est l'élément le plus percutant de votre README. Utilisez des outils comme LICEcap ou ScreenToGif pour capturer votre écran.)*

---

## 📋 Table des Matières

1.  [Objectifs du Projet](#-objectifs-du-projet)
2.  [Fonctionnalités Clés](#-fonctionnalités-clés)
3.  [Modèle Mathématique](#-modèle-mathématique)
4.  [Structure du Code](#-structure-du-code)
5.  [Prérequis et Installation](#-prérequis-et-installation)
6.  [Comment Lancer la Simulation](#-comment-lancer-la-simulation)
7.  [Résultats](#-résultats)
8.  [Prochaines Étapes (Future Work)](#-prochaines-étapes)
9.  [Auteur](#-auteur)
10. [Licence](#-licence)

---

### 🎯 Objectifs du Projet

*   Développer un modèle dynamique **non-linéaire** fidèle d'un quadrirotor basé sur les équations de Newton-Euler.
*   Implémenter une **structure de commande en cascade** (position et attitude) comme base de référence.
*   Concevoir et valider un **contrôleur prédictif (MPC)** pour le suivi de trajectoire.
*   Mettre en place un **filtre de Kalman étendu (EKF)** pour l'estimation d'état à partir de capteurs simulés et bruités.

---

### ✨ Fonctionnalités Clés

*   **Modèle Dynamique Complet** : Simulation 6-DoF (degrés de liberté) incluant les effets de poussée, de couple et de traînée.
*   **Contrôleur PID en Cascade** : Une architecture de contrôle classique et robuste pour la stabilisation et le suivi de point de consigne.
*   **Architecture Modulaire** : Le code est structuré pour permettre de remplacer facilement le contrôleur (PID -> MPC) ou d'ajouter des modules (bruit, estimateur).
*   **Visualisation des Résultats** : Scripts dédiés pour tracer la trajectoire 3D, l'évolution de la position et de l'attitude.

---

### 📐 Modèle Mathématique

La simulation est basée sur le modèle dynamique présenté dans le document de référence, qui utilise les équations de Newton-Euler pour décrire le mouvement du drone.

*   **Dynamique de Translation** :
    `m * ẍ = F_gravité + F_traînée + R * F_poussée`
*   **Dynamique de Rotation** :
    `J * ω̇ = -ω x (Jω) + τ`

Les forces et moments sont générés par les quatre rotors, dont les vitesses de rotation constituent les entrées de commande du système.

---

### 📁 Structure du Code

Le projet est organisé en plusieurs fichiers MATLAB pour une meilleure lisibilité et maintenabilité :

-   `main_simulation.m` : **Point d'entrée du programme.** Définit les conditions initiales, la consigne et lance le solveur ODE.
-   `initialize_params.m` : Centralise tous les paramètres physiques du drone (masse, inertie, etc.).
-   `quadrotor_model.m` : Contient les **équations différentielles** du modèle non-linéaire. C'est le cœur du simulateur.
-   `controller.m` : Implémente la **loi de commande**. Actuellement un PID, destiné à être remplacé par le MPC.
-   `plot_results.m` : Gère la création de tous les graphiques de résultats.

---

### 🛠️ Prérequis et Installation

1.  **Logiciel** : MATLAB R2020a ou plus récent.
2.  **Toolboxes** : Aucune toolbox spécifique n'est requise pour la version de base avec le contrôleur PID. *(Mentionnez ici si vous ajoutez des toolboxes pour le MPC ou autre)*.


Pour installer, il suffit de cloner ce dépôt :
```bash
git clone https://github.com/bangalconte20-netizen/Quadrotor_with_MPC_controller.git

---


