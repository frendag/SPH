# Plan de développement optimal — CPN-Analytics Club Platform

Ce dossier contient une suite de fichiers Markdown destinés à piloter le développement de la plateforme avec Claude Code.

La logique recommandée est volontairement progressive : d’abord le socle technique, puis le cœur métier club, puis les modules sportifs, puis l’analytics, puis l’industrialisation.

## Ordre recommandé

1. `01_BOOTSTRAP_REPO.md` — Initialisation du projet et conventions
2. `02_ARCHITECTURE_BACKEND_FRONTEND.md` — Architecture applicative cible
3. `03_AUTH_RBAC_SECURITY.md` — Authentification, rôles et permissions
4. `04_CORE_DOMAIN_SEASONS_SWIMMERS_GROUPS.md` — Saisons, nageurs, groupes
5. `05_REGISTRATIONS_ADMIN_DOCUMENTS.md` — Inscriptions, dossiers, documents
6. `06_COACHES_PLANNING_SESSIONS.md` — Entraîneurs, planning, séances
7. `07_ATTENDANCE_MOBILE_FIRST.md` — Émargement mobile et assiduité
8. `08_COMPETITION_PERFORMANCE_QUALIFICATIONS.md` — Compétitions, performances, qualifications
9. `09_TRAINING_PERFORMANCE_PHYSICAL_TESTS.md` — Performances entraînement et mesures physiques
10. `10_DASHBOARDS_ANALYTICS.md` — Tableaux de bord et indicateurs
11. `11_COMMUNICATION_NOTIFICATIONS_EXPORTS.md` — Communication, notifications, exports
12. `12_FRONTEND_UX_PROFESSIONAL.md` — UX professionnelle et responsive
13. `13_TESTING_DATA_QUALITY_NON_REGRESSION.md` — Tests, qualité métier et non-régression
14. `14_DEPLOYMENT_CI_CD_OPERATIONS.md` — Déploiement, CI/CD, exploitation
15. `15_AI_HANDOVER_AND_BACKLOG.md` — Passation IA, backlog et évolutions

## Stratégie de commits

Faire un commit Git à la fin de chaque étape :

```bash
git add .
git commit -m "step XX: description courte"
```

## Définition de fini globale

Une étape est terminée uniquement si :

- l’application démarre ;
- les tests existants passent ;
- le build frontend passe s’il existe ;
- les migrations sont cohérentes ;
- les endpoints principaux sont documentés ;
- les écrans créés sont utilisables ;
- les règles métier critiques sont couvertes par des tests.

## Stack recommandée

Cette proposition part sur une stack moderne, robuste et adaptée à un club professionnel :

- Backend : FastAPI ou Django REST Framework
- Frontend : React / Next.js
- Base : PostgreSQL
- Auth : JWT ou session sécurisée selon framework
- Mobile : PWA responsive en premier, application native ensuite si nécessaire
- Tests : Pytest côté backend, Playwright côté frontend, tests unitaires métier
- Déploiement : Docker, compose en dev, CI/CD GitHub Actions ou GitLab CI

Claude Code peut adapter la stack si le repository existant impose déjà une technologie. Dans ce cas, il doit conserver l’esprit modulaire et documenter les écarts.
