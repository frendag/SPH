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


# Étape 07 — Émargement mobile-first et assiduité

## Objectif

Permettre aux entraîneurs de faire l’appel en bord de bassin en moins de deux minutes.

## Périmètre

- Émargement séance
- Présent/absent/retard/excusé
- Commentaires
- Statistiques assiduité
- Interface mobile rapide

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Implémente le module d’émargement mobile-first. L’expérience entraîneur doit être ultra rapide, lisible sur smartphone/tablette et utilisable en bord de bassin.
```

## Tâches attendues

- [ ] Créer modèle Attendance lié à TrainingSession et Swimmer.
- [ ] Ajouter statuts : present, absent_non_excuse, absent_excuse, retard, blesse, dispense, autre.
- [ ] Créer endpoint pour charger la séance du jour avec nageurs attendus.
- [ ] Créer endpoint de sauvegarde rapide en lot.
- [ ] Créer écran mobile séance du jour.
- [ ] Créer composants gros boutons et mode liste compacte.
- [ ] Ajouter statistiques taux de présence individuel et groupe.
- [ ] Ajouter alerte absence répétée.

## Critères d’acceptation

- [ ] Un entraîneur peut émarger tous les nageurs d’une séance rapidement.
- [ ] La sauvegarde en lot fonctionne.
- [ ] Les modifications sont historisées ou auditées.
- [ ] Les statistiques d’assiduité se mettent à jour.
- [ ] L’interface est utilisable sur mobile.

## Vérifications à exécuter

- [ ] Tests sauvegarde présence.
- [ ] Tests taux présence.
- [ ] Tests permissions entraîneur.
- [ ] Tests responsive ou Playwright mobile.

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
git commit -m "step 07: émargement mobile-first et assiduité"
```
