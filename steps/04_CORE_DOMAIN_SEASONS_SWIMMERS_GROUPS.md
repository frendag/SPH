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


# Étape 04 — Socle métier : saisons, nageurs, groupes

## Objectif

Implémenter les entités métier centrales autour desquelles tous les autres modules vont s’articuler.

## Périmètre

- Saisons sportives
- Fiches nageurs
- Responsables légaux
- Groupes
- Affectations nageur-groupe
- Historique

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Implémente le noyau métier CPN-Analytics : saisons, nageurs, groupes et affectations. La règle structurante est que les groupes sont saisonniers et que l’historique des affectations doit être conservé.
```

## Tâches attendues

- [ ] Créer le modèle Season.
- [ ] Créer le modèle Swimmer avec date de naissance, sexe, statut, licence éventuelle.
- [ ] Créer le modèle LegalGuardian ou ParentLink.
- [ ] Créer le modèle Group avec type, niveau, capacité, saison, statut.
- [ ] Créer le modèle GroupMembership historisé avec dates début/fin.
- [ ] Créer les endpoints CRUD nécessaires.
- [ ] Créer les écrans frontend : liste nageurs, fiche nageur, liste groupes, détail groupe.
- [ ] Ajouter filtres par saison, groupe, sexe, âge, statut.

## Critères d’acceptation

- [ ] Un nageur peut être affecté à un groupe pour une saison.
- [ ] Un changement de groupe conserve l’historique.
- [ ] Un groupe est lié à une saison.
- [ ] La fiche nageur affiche groupe actuel et historique.
- [ ] Les listes sont filtrables.

## Vérifications à exécuter

- [ ] Tests modèle âge/catégorie.
- [ ] Tests affectation groupe.
- [ ] Tests capacité groupe.
- [ ] Tests endpoints CRUD.

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
git commit -m "step 04: socle métier : saisons, nageurs, groupes"
```
