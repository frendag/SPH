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


# Étape 10 — Tableaux de bord et analytics

## Objectif

Transformer les données collectées en indicateurs exploitables par direction, entraîneurs, familles et nageurs.

## Périmètre

- Dashboard direction
- Dashboard directeur sportif
- Dashboard entraîneur
- Dashboard nageur
- Indicateurs assiduité
- Indicateurs performance
- Alertes

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Implémente les tableaux de bord CPN-Analytics. Les indicateurs doivent être utiles, rapides à charger et filtrables par saison, groupe, sexe, catégorie et période.
```

## Tâches attendues

- [ ] Créer endpoints analytics agrégés.
- [ ] Créer tableau de bord direction : adhérents, groupes, dossiers, présences, progression.
- [ ] Créer tableau de bord directeur sportif : progression, qualifications, stagnations, alertes.
- [ ] Créer tableau de bord entraîneur : séances, présences, tests récents, objectifs.
- [ ] Créer tableau de bord nageur : planning, records, progression, objectifs.
- [ ] Optimiser les requêtes avec index ou vues si nécessaire.
- [ ] Ajouter export des indicateurs clés.

## Critères d’acceptation

- [ ] Chaque rôle voit un dashboard adapté.
- [ ] Les données respectent les permissions.
- [ ] Les indicateurs sont cohérents avec les données sources.
- [ ] Les pages restent rapides sur volume moyen.

## Vérifications à exécuter

- [ ] Tests calcul indicateurs.
- [ ] Tests permissions dashboard.
- [ ] Tests performance requêtes principales.
- [ ] Tests visuels des graphiques si possible.

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
git commit -m "step 10: tableaux de bord et analytics"
```
