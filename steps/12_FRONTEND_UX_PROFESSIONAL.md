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


# Étape 12 — Interface professionnelle, responsive et mobile

## Objectif

Harmoniser l’expérience utilisateur et rendre l’application crédible pour un club structuré.

## Périmètre

- Design system
- Navigation
- Responsive
- Menus rétractables
- Tableaux
- Graphiques
- Accessibilité de base

## Prompt à donner à Claude Code

```text
Tu es Claude Code. Améliore l’UX/UI de CPN-Analytics pour obtenir une plateforme professionnelle, claire, rapide et utilisable sur desktop, tablette et mobile. Privilégie la lisibilité et les actions terrain.
```

## Tâches attendues

- [ ] Créer ou harmoniser layout principal.
- [ ] Ajouter navigation par rôles.
- [ ] Créer sidebar rétractable desktop/tablette.
- [ ] Optimiser les vues mobiles.
- [ ] Standardiser les tableaux : tri, filtre, recherche, pagination.
- [ ] Standardiser les cartes nageur/groupe/séance.
- [ ] Améliorer les graphiques interactifs.
- [ ] Ajouter états vides, chargement, erreurs.

## Critères d’acceptation

- [ ] L’application est cohérente visuellement.
- [ ] Les menus ne prennent pas trop de place sur mobile/tablette.
- [ ] Les entraîneurs accèdent vite aux séances.
- [ ] Les tableaux restent lisibles.
- [ ] Les erreurs sont compréhensibles.

## Vérifications à exécuter

- [ ] Build frontend.
- [ ] Test responsive manuel ou Playwright.
- [ ] Vérification navigation par rôle.
- [ ] Vérification affichage mobile/tablette.

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
git commit -m "step 12: interface professionnelle, responsive et mobile"
```
