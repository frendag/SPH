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


# Étape 09 — Performances entraînement, tests internes et mesures physiques

## Objectif

Étendre la mesure de performance au quotidien, dans la continuité de l’application mobile CPN.

## Périmètre

- Tests entraînement
- Chronos séance
- Séries
- RPE
- Mesures physiques
- Historique individuel
- Confidentialité

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Implémente le suivi des performances à l’entraînement et des mesures physiques. Les données physiques sont sensibles : leur accès doit être limité et audité.
```

## Tâches attendues

- [ ] Créer modèle TrainingTestDefinition.
- [ ] Créer modèle TrainingPerformance lié à séance et nageur.
- [ ] Créer saisie de séries : répétitions, distance, temps, récupération, allure cible.
- [ ] Créer modèle PhysicalMeasurement : type, valeur, unité, date, commentaire.
- [ ] Créer permissions spécifiques pour données physiques.
- [ ] Créer graphiques d’évolution individuels.
- [ ] Créer comparaison entraînement/compétition par épreuve lorsque possible.
- [ ] Créer interface mobile de saisie rapide test.

## Critères d’acceptation

- [ ] Un entraîneur peut saisir un test pendant une séance.
- [ ] Les mesures physiques sont historisées.
- [ ] Les parents/nageurs ne voient que les données autorisées.
- [ ] Les graphiques affichent l’évolution dans le temps.
- [ ] Les données sont filtrables par type de test.

## Vérifications à exécuter

- [ ] Tests permissions données physiques.
- [ ] Tests saisie séries.
- [ ] Tests évolution mesure.
- [ ] Tests corrélation simple si implémentée.

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
git commit -m "step 09: performances entraînement, tests internes et mesures physiqu"
```
