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


# Étape 03 — Authentification, rôles, permissions et sécurité de base

## Objectif

Créer un socle sécurisé avec gestion fine des rôles : administrateur, bureau, directeur sportif, entraîneur, parent, nageur.

## Périmètre

- Connexion
- Comptes utilisateurs
- Rôles
- Permissions
- Protection routes API
- Protection routes frontend
- Journalisation actions sensibles

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Implémente le socle d’authentification et de permissions de CPN-Analytics. La plateforme gère des mineurs et des données sportives/physiques sensibles : la sécurité doit être conçue dès le départ.
```

## Tâches attendues

- [ ] Créer le modèle utilisateur.
- [ ] Ajouter les rôles standards : super_admin, admin_club, bureau, directeur_sportif, entraineur, parent, nageur.
- [ ] Implémenter login/logout ou JWT selon la stack.
- [ ] Hasher les mots de passe avec un algorithme robuste.
- [ ] Créer des guards/middlewares de permission.
- [ ] Créer des helpers `can_access_swimmer`, `can_manage_group`, `can_view_physical_data`.
- [ ] Ajouter une table ou un mécanisme d’audit pour actions sensibles.
- [ ] Créer des tests de permissions.

## Critères d’acceptation

- [ ] Un utilisateur non connecté ne peut pas accéder aux endpoints privés.
- [ ] Un parent ne voit que ses enfants.
- [ ] Un entraîneur ne voit que ses groupes sauf permission explicite.
- [ ] Les données physiques sont protégées par permission spécifique.
- [ ] Les actions sensibles sont auditables.

## Vérifications à exécuter

- [ ] Tests unitaires auth.
- [ ] Tests API accès refusé / autorisé.
- [ ] Vérification absence de mot de passe en clair dans logs ou base.

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
git commit -m "step 03: authentification, rôles, permissions et sécurité de base"
```
