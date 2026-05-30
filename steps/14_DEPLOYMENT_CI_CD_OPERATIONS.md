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


# Étape 14 — Déploiement, CI/CD, sauvegardes et exploitation

## Objectif

Préparer une mise en production fiable et maintenable.

## Périmètre

- Docker production
- CI/CD
- Migrations
- Sauvegardes
- Logs
- Monitoring
- Rollback

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Prépare l’industrialisation de CPN-Analytics : déploiement, CI/CD, sauvegardes, logs et procédures d’exploitation. L’objectif est de pouvoir maintenir la plateforme sans intervention artisanale permanente.
```

## Tâches attendues

- [ ] Créer Dockerfile backend et frontend si nécessaire.
- [ ] Créer configuration production via variables d’environnement.
- [ ] Créer workflow CI : lint, tests, build.
- [ ] Documenter migrations base de données.
- [ ] Ajouter script sauvegarde PostgreSQL.
- [ ] Prévoir logs structurés.
- [ ] Ajouter healthchecks.
- [ ] Créer `docs/DEPLOYMENT.md` et `docs/RUNBOOK.md`.

## Critères d’acceptation

- [ ] La CI vérifie automatiquement le code.
- [ ] La procédure de déploiement est documentée.
- [ ] Une sauvegarde peut être lancée et restaurée en théorie documentée.
- [ ] Les logs permettent de diagnostiquer les erreurs.

## Vérifications à exécuter

- [ ] Tester build Docker.
- [ ] Tester workflow local si possible.
- [ ] Tester script de sauvegarde sur base dev.
- [ ] Vérifier documentation runbook.

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
git commit -m "step 14: déploiement, ci/cd, sauvegardes et exploitation"
```
