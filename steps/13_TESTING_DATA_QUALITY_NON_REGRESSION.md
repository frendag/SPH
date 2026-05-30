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


# Étape 13 — Tests, qualité des données et non-régression métier

## Objectif

Sécuriser les règles critiques : qualifications, droits, présences, historiques, imports et exports.

## Périmètre

- Tests unitaires
- Tests intégration
- Tests API
- Tests frontend
- Fixtures métier natation
- Non-régression

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Mets en place une stratégie de tests solide pour CPN-Analytics. Les règles métier liées au sexe, à l’âge, aux performances et aux droits d’accès sont critiques et doivent être verrouillées.
```

## Tâches attendues

- [ ] Créer fixtures représentatives : nageurs filles/garçons, âges différents, groupes, compétitions, grilles.
- [ ] Ajouter tests qualification complets.
- [ ] Ajouter tests RBAC complets.
- [ ] Ajouter tests assiduité.
- [ ] Ajouter tests import/export.
- [ ] Ajouter tests de changement de groupe historisé.
- [ ] Ajouter pipeline de test local documenté.
- [ ] Créer fichier `docs/TEST_STRATEGY.md`.

## Critères d’acceptation

- [ ] Les bugs déjà identifiés ne peuvent pas revenir sans casser un test.
- [ ] Les règles sexe/âge/grille sont couvertes.
- [ ] Les droits parent/entraîneur/admin sont couverts.
- [ ] Les imports ont des tests de cas invalides.

## Vérifications à exécuter

- [ ] Exécuter toute la suite de tests.
- [ ] Vérifier couverture minimale si outil disponible.
- [ ] Vérifier absence de tests fragiles dépendants de l’heure courante sans contrôle.

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
git commit -m "step 13: tests, qualité des données et non-régression métier"
```
