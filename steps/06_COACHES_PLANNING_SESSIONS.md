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


# Étape 06 — Entraîneurs, planning, créneaux et séances

## Objectif

Structurer l’organisation sportive : entraîneurs, groupes, créneaux récurrents et séances générées.

## Périmètre

- Fiches entraîneurs
- Disponibilités
- Affectation groupe-entraineur
- Créneaux hebdomadaires
- Séances générées
- Conflits planning

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Implémente le module planning d’un club de natation professionnel. Le planning doit gérer groupes, entraîneurs, bassins, lignes d’eau et séances générées automatiquement.
```

## Tâches attendues

- [ ] Créer modèle Coach lié à User.
- [ ] Créer modèle Pool/Site si nécessaire.
- [ ] Créer modèle TrainingSlot : jour, heure début, heure fin, groupe, entraîneur, bassin, ligne.
- [ ] Créer modèle TrainingSession généré depuis les créneaux.
- [ ] Créer service de génération des séances sur période.
- [ ] Créer détection de conflits : entraîneur, groupe, bassin, ligne, horaire.
- [ ] Créer vues planning par groupe, par entraîneur, par jour.
- [ ] Créer action annuler/déplacer séance.

## Critères d’acceptation

- [ ] Un groupe peut avoir plusieurs créneaux.
- [ ] Une séance réelle peut être générée depuis un créneau.
- [ ] Les conflits de planning sont signalés.
- [ ] L’entraîneur voit ses séances.
- [ ] Le directeur sportif peut modifier le planning.

## Vérifications à exécuter

- [ ] Tests génération séances.
- [ ] Tests conflits horaires.
- [ ] Tests annulation séance.
- [ ] Tests droits entraîneur/directeur sportif.

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
git commit -m "step 06: entraîneurs, planning, créneaux et séances"
```
