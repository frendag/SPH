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


# Étape 11 — Communication, notifications et exports

## Objectif

Permettre au club de communiquer efficacement et d’extraire les données utiles.

## Périmètre

- Messages ciblés
- Notifications
- Emails
- Exports XLSX/CSV/PDF
- Relances
- Historique communication

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Implémente les fonctions de communication et d’export utiles au fonctionnement quotidien du club. Les exports doivent remplacer progressivement les fichiers Excel manuels.
```

## Tâches attendues

- [ ] Créer modèle Message/Announcement.
- [ ] Créer ciblage par groupe, rôle, compétition, dossier incomplet.
- [ ] Créer système de notification interne.
- [ ] Prévoir adaptateur email sans imposer de fournisseur.
- [ ] Créer exports XLSX/CSV : nageurs, groupes, présences, performances, dossiers incomplets, paiements.
- [ ] Créer historique des communications.
- [ ] Créer modèles de messages paramétrables.

## Critères d’acceptation

- [ ] Un admin peut envoyer une annonce à un groupe.
- [ ] Les destinataires sont calculés correctement.
- [ ] Les exports respectent les filtres et permissions.
- [ ] Les exports sont lisibles et exploitables.

## Vérifications à exécuter

- [ ] Tests ciblage destinataires.
- [ ] Tests génération XLSX/CSV.
- [ ] Tests permissions export.
- [ ] Tests historique message.

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
git commit -m "step 11: communication, notifications et exports"
```
