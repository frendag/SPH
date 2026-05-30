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


# Étape 05 — Inscriptions, réinscriptions, dossiers administratifs et documents

## Objectif

Permettre la gestion administrative complète d’un adhérent et réduire la dépendance aux fichiers Excel.

## Périmètre

- Formulaire inscription
- Réinscription
- Statuts dossier
- Documents obligatoires
- Validation bureau
- Pièces justificatives

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Implémente le module d’inscription et de dossier administratif pour un club de natation. Le bureau doit pouvoir suivre rapidement les dossiers incomplets, les documents manquants et les validations à faire.
```

## Tâches attendues

- [ ] Créer modèle Registration avec statut : brouillon, soumis, incomplet, attente_paiement, attente_validation, valide, refuse, archive.
- [ ] Créer modèle AdministrativeDocument avec type, fichier, statut, expiration.
- [ ] Créer paramétrage des documents requis par saison.
- [ ] Créer workflow de validation bureau.
- [ ] Créer écran tableau des inscriptions.
- [ ] Créer fiche dossier administratif du nageur.
- [ ] Ajouter upload sécurisé de documents si stockage disponible.
- [ ] Ajouter exports dossiers incomplets.

## Critères d’acceptation

- [ ] Le bureau voit les dossiers à traiter.
- [ ] Un dossier ne peut être validé que si les documents requis sont conformes ou explicitement dérogés.
- [ ] Les documents expirés sont identifiables.
- [ ] La fiche nageur affiche le statut administratif.

## Vérifications à exécuter

- [ ] Tests statuts inscription.
- [ ] Tests documents requis.
- [ ] Tests permissions parent/bureau.
- [ ] Tests upload ou simulation upload.

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
git commit -m "step 05: inscriptions, réinscriptions, dossiers administratifs et doc"
```
