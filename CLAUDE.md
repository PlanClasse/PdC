# PlanClasse

Application web mono-fichier (index.html + sw.js) pour gestion de classe au collège, par un prof de techno. Utilisée sur iPad et PC.

## Architecture
- Tout est dans un seul fichier index.html (HTML + CSS + JS inline, ~45000 lignes)
- Service Worker sw.js pour le mode offline (PWA)
- Stockage local via localStorage clé 'pc6'
- Sync optionnelle via API Dropbox (PKCE OAuth)

## Conventions de versioning
- Version semver : v10.XXX (ou v10.XXX.Y pour patches mineurs)
- `const APP_VERSION` dans index.html ET `const CACHE_NAME` dans sw.js doivent toujours être bumpés en parallèle
- Chaque modification commentée avec un marqueur "V020-vXXX" indiquant la version d'introduction

## Règles à respecter
- Pas de framework, pas de build, JavaScript vanilla
- Pas de dépendance npm ni de CDN externe (offline-first strict)
- Toujours vérifier après modif : balance HTML équilibrée (compter div/span/button ouvrants vs fermants)
- Toujours vérifier après modif : node --check sur les scripts inline extraits
- Préserver les commentaires "V020-vXXX" existants

## Ne JAMAIS faire sans accord explicite
- Modifier la fonction saveS (centrale, propagée partout)
- Modifier les structures de données stockées (S.cl, S.seances, S.studentData...)
- Ajouter une dépendance externe

## Style de réponse
- Réponses concises, sans flatterie
- Recap structuré à chaque livraison : Cause, Modifs, Tests, Limites
- Pour les modifications complexes : présenter un plan avant d'exécuter
