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


# Étape 02 — Architecture backend, frontend et modèle modulaire

## Objectif

Mettre en place l’architecture logicielle cible avant d’implémenter les modules métier.

## Périmètre

- Architecture backend
- Architecture frontend
- Découpage modules
- Pattern services/repositories
- Gestion des migrations
- API versionnée

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Mets en place une architecture modulaire pour une plateforme professionnelle de gestion de club de natation. Le code doit permettre d’ajouter les modules inscriptions, groupes, planning, émargement, performances et analytics sans créer de dépendances circulaires.
```

## Tâches attendues

- [ ] Créer une architecture backend par domaines : auth, users, seasons, swimmers, groups, planning, attendance, performances, analytics.
- [ ] Créer une architecture frontend par features, pages, components, hooks, services API.
- [ ] Mettre en place une version d’API, par exemple `/api/v1`.
- [ ] Créer une convention de DTO/schemas.
- [ ] Prévoir une couche service pour les règles métier.
- [ ] Prévoir une couche repository ou ORM isolée.
- [ ] Documenter les modules dans `docs/MODULES.md`.

## Critères d’acceptation

- [ ] Les nouveaux modules peuvent être ajoutés sans modifier massivement le cœur.
- [ ] Les routes API sont regroupées clairement.
- [ ] Les règles métier ne sont pas écrites directement dans les contrôleurs.
- [ ] Le frontend distingue pages, composants UI, appels API et logique métier.

## Vérifications à exécuter

- [ ] Vérifier le démarrage backend.
- [ ] Vérifier le build frontend si présent.
- [ ] Vérifier qu’une route healthcheck existe.

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
git commit -m "step 02: architecture backend, frontend et modèle modulaire"
```
