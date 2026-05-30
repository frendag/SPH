# CPN-Analytics — Développement assisté par IA / Claude Code

> Objectif : fournir à Claude Code une instruction autonome, testable et progressive.
> Chaque fichier doit être exécuté dans l’ordre, après commit Git de l’étape précédente.

## Règles générales pour Claude Code

- Lire d’abord le `README_DEV_PLAN.md`, puis le fichier d’étape courant.
- Ne pas modifier le périmètre d’une étape sans raison technique documentée.
- Livrer du code fonctionnel, lisible, typé et maintenable.
- Privilégier une architecture modulaire plutôt qu’un fichier monolithique.
- Ajouter ou mettre à jour les tests à chaque étape.
- Mettre à jour la documentation technique si les choix évoluent.
- Ne jamais supprimer une fonctionnalité existante sans justification.
- Avant de terminer, exécuter les commandes de vérification disponibles : lint, typecheck, tests, build.
- À la fin de chaque étape, produire un résumé : fichiers créés, fichiers modifiés, décisions techniques, tests effectués, limites restantes.

---


# Étape 01 — Initialisation du repository et conventions projet

## Objectif

Créer une base projet propre, exécutable localement, prête pour un développement modulaire assisté par IA.

## Périmètre

- Structure du repository
- Conventions de nommage
- Configuration environnement
- Docker local
- Documentation de démarrage
- Commandes standardisées

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Initialise ou normalise le repository CPN-Analytics Club Platform pour qu’il soit propre, maintenable et prêt à recevoir les modules métier. Analyse l’existant avant de créer de nouveaux fichiers. Si une structure existe déjà, conserve-la autant que possible et améliore-la sans casser le fonctionnement.
```

## Tâches attendues

- [ ] Créer ou vérifier l’arborescence `backend/`, `frontend/`, `docs/`, `scripts/`, `infra/`, `tests/`.
- [ ] Ajouter un `.env.example` documenté.
- [ ] Ajouter un `README.md` orienté développeur.
- [ ] Ajouter des commandes de démarrage local.
- [ ] Préparer `docker-compose.yml` avec PostgreSQL si pertinent.
- [ ] Ajouter un fichier `CONTRIBUTING.md` court avec conventions Git, branches, commits.
- [ ] Ajouter un fichier `docs/ARCHITECTURE_DECISIONS.md` pour journaliser les décisions.

## Critères d’acceptation

- [ ] Un développeur peut cloner le projet et comprendre comment le lancer.
- [ ] Les variables d’environnement nécessaires sont listées.
- [ ] Aucune donnée sensible n’est commitée.
- [ ] La structure permet d’ajouter backend, frontend et infra sans confusion.

## Vérifications à exécuter

- [ ] Lancer l’application si elle existe déjà.
- [ ] Vérifier que Docker démarre les services configurés.
- [ ] Vérifier que le README contient les commandes utiles.

## Sortie attendue de Claude Code

À la fin de cette étape, Claude Code doit fournir :

- la liste des fichiers créés ;
- la liste des fichiers modifiés ;
- les migrations ajoutées ;
- les tests ajoutés ;
- les commandes exécutées ;
- les résultats des tests ;
- les limites ou points à reprendre à l’étape suivante.

## Commit recommandé

```bash
git add .
git commit -m "step 01: initialisation du repository et conventions projet"
```
