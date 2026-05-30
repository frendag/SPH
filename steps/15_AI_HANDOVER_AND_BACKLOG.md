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


# Étape 15 — Passation IA, backlog produit et évolutions avancées

## Objectif

Préparer la suite du développement avec une mémoire projet claire et un backlog priorisé.

## Périmètre

- Documentation IA
- Backlog
- Dette technique
- Évolutions SaaS
- Priorisation
- Prompts futurs

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Prépare la passation du projet CPN-Analytics pour les prochaines itérations IA/humain. Le prochain intervenant doit comprendre l’état du produit, les décisions prises, les limites et les prochaines priorités.
```

## Tâches attendues

- [ ] Créer `docs/AI_HANDOVER.md` avec état du projet.
- [ ] Créer `docs/BACKLOG.md` priorisé : MVP, V1, V2.
- [ ] Créer `docs/TECH_DEBT.md`.
- [ ] Lister les modules non terminés.
- [ ] Lister les risques métier et techniques.
- [ ] Préparer prompts de reprise pour les futures sessions Claude Code.
- [ ] Documenter les commandes utiles.

## Critères d’acceptation

- [ ] Un nouvel agent IA peut reprendre le projet sans réexpliquer tout le contexte.
- [ ] Le backlog est priorisé et actionnable.
- [ ] Les limites connues sont transparentes.
- [ ] Les prochaines étapes sont concrètes.

## Vérifications à exécuter

- [ ] Relire la documentation générée.
- [ ] Vérifier qu’elle correspond au code réel.
- [ ] Vérifier que les prompts de reprise sont utilisables.

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
git commit -m "step 15: passation ia, backlog produit et évolutions avancées"
```
