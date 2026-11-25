# ORION DevOps Lab

**From Code to Production.** Laboratoire interactif pour apprendre Docker et le DevOps, du premier container jusqu'au déploiement sur AWS. Tout tient dans **un seul fichier HTML** : aucune installation, aucun serveur, aucune dépendance à gérer.

## Démarrage rapide

1. Télécharge `ORION_DevOps_Lab.html`.
2. Ouvre-le dans un navigateur récent (Chrome, Firefox, Edge, Safari).
3. C'est tout. Une connexion Internet sert uniquement à charger les polices Google Fonts (le site reste utilisable sans, avec des polices de secours).

## Contenu : 25 modules

| Groupe | Modules |
|---|---|
| Démarrer | Tableau de bord |
| Fondations | Comprendre Docker · Architecture · Images et containers |
| Pratique Docker | Command Center · Explorateur de commandes · Dockerfile · Docker Compose · Réseaux · Volumes · Registry et Docker Hub |
| Outils | Linux et terminal · Git et GitHub |
| DevOps | CI/CD · GitHub Actions |
| Cloud | AWS et Cloud · IAM et identités · Déploiement complet |
| Production | Sécurité Docker · Monitoring et debug · Kubernetes |
| Pratique | Projets pratiques · DevOps Missions |
| Évaluation | Quiz et examens (6 niveaux) |
| Référence | Glossaire · Cheat sheet |

## Fonctionnalités

- **Terminal Docker simulé** (`docker run`, `ps`, `build`, `exec`, `volume`, `network`, `compose`, et une simulation AWS CLI) : on pratique sans risque, rien n'est exécuté sur ta machine.
- **Visualisations animées** : architecture Docker, cycle de vie d'un container, couches d'image et cache, pipeline CI/CD, graphe Compose.
- **Éditeurs avec analyse** : linter de Dockerfile, validateur de `docker-compose.yml` et de workflows GitHub Actions, évaluateur de politiques IAM.
- **Explorateur de commandes** : décompose une commande saisie (commande, options, valeurs, image) et explique chaque morceau.
- **Questions de compréhension** à la fin de chaque module, **quiz à 6 niveaux**, missions et projets guidés.
- **Progression** : XP, 6 niveaux de compétence, série de jours, temps passé, lacunes identifiées par thème.
- **Responsive** : le menu devient un tiroir sur mobile, `prefers-reduced-motion` est respecté.

### Ajouts de la version 1.1

- **Palette de navigation** : `Ctrl+K` (ou `Cmd+K`, ou `/`) ouvre une recherche instantanée parmi les modules, insensible aux accents. Un bouton « Ctrl K » est aussi dans la barre du haut.
- **Raccourcis clavier** : `Alt+←` et `Alt+→` pour passer au module précédent ou suivant.
- **Sauvegarde de la progression** : sur le tableau de bord, boutons **Exporter** (fichier JSON daté) et **Importer** pour déplacer ta progression d'un navigateur ou d'un appareil à l'autre.

## Sauvegarde des données

La progression est stockée dans le `localStorage` du navigateur (clé `orion-devops-lab-v1`). Elle est donc propre à chaque navigateur et disparaît si tu vides les données du site. Utilise **Exporter** régulièrement pour en garder une copie.

## Raccourcis

| Raccourci | Action |
|---|---|
| `Ctrl/Cmd + K` ou `/` | Ouvrir la palette de navigation |
| `↑` `↓` puis `Entrée` | Choisir un module dans la palette |
| `Échap` | Fermer la palette |
| `Alt + ←` / `Alt + →` | Module précédent / suivant |

## Structure technique

- Un seul fichier : HTML + CSS + JavaScript, sans framework ni build.
- Routage par ancre (`#dockerfile`, `#cicd`, `#quiz`…) : chaque module a un lien direct partageable.
- Données pédagogiques (modules, commandes, quiz, projets) déclarées en tête du script ; moteur et vues plus bas, une vue par module dans l'objet `VIEWS`.
- Le simulateur (`DockerSim`) garde un état en mémoire : images, containers, volumes, réseaux.

### Ajouter un module

1. Ajoute une entrée `{id, t, g}` dans le tableau `MODULES`.
2. Déclare `VIEWS.<id> = { html(){…}, mount(root){…} }`.
3. (Optionnel) ajoute des questions dans `QUIZ` avec `tag:'<id>'` pour la section « Vérifier ma compréhension ».

## Limites

- Le terminal est une **simulation** : les résultats sont pédagogiques et ne remplacent pas un vrai Docker, ni un vrai compte AWS.
- La progression n'est pas synchronisée entre appareils, sauf via export/import manuel.

## Pistes d'évolution

Thème clair, mode révision par répétition espacée des questions ratées, export PDF de la cheat sheet, version anglaise.
