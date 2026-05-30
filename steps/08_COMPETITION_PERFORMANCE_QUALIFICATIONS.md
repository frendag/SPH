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


# Étape 08 — Compétitions, performances officielles et qualifications

## Objectif

Intégrer le cœur historique de CPN-Analytics : résultats, temps, grilles, niveaux et qualifications.

## Périmètre

- Compétitions
- Résultats
- Épreuves
- Conversion temps
- Records personnels
- Grilles qualification
- Calcul niveau

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Implémente ou refactorise le module performance compétition. Le calcul des qualifications est critique : il doit tenir compte du sexe, de l’âge, de la saison, de l’épreuve, du bassin et de la grille applicable.
```

## Tâches attendues

- [ ] Créer modèle Competition.
- [ ] Créer modèle Event/SwimEvent : distance, nage, bassin, sexe si applicable.
- [ ] Créer modèle CompetitionPerformance.
- [ ] Créer utilitaire robuste de conversion temps vers centièmes.
- [ ] Créer modèle QualificationGrid et QualificationThreshold.
- [ ] Créer service `qualification_engine`.
- [ ] Créer import CSV/XLSX si pertinent.
- [ ] Créer fiche performance nageur avec records personnels.
- [ ] Créer graphiques progression par épreuve.

## Critères d’acceptation

- [ ] Une performance est toujours contextualisée.
- [ ] Le moteur de qualification différencie sexe et âge.
- [ ] Les records personnels sont calculés correctement.
- [ ] Les performances peuvent être filtrées par saison, bassin, nage, distance.
- [ ] Les erreurs d’import sont explicites.

## Vérifications à exécuter

- [ ] Tests conversion temps.
- [ ] Tests qualification fille/garçon.
- [ ] Tests âge à date de compétition.
- [ ] Tests bassin 25/50.
- [ ] Tests non-régression sur exemples connus.

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
git commit -m "step 08: compétitions, performances officielles et qualifications"
```
