# CPN-Analytics — Charte graphique et UX/UI Web

## 1. Objectif du document

Ce document définit la charte graphique, l'organisation de l'interface web et les règles UX/UI de la plateforme **CPN-Analytics Club Manager**, plateforme professionnelle de gestion complète d'un club de natation.

L'objectif est de créer une interface :

- ultra moderne ;
- intuitive dès la première utilisation ;
- rapide à naviguer ;
- orientée club professionnel ;
- exploitable par le bureau, les entraîneurs, le directeur sportif, les parents et les nageurs ;
- cohérente avec une logique data, performance et pilotage sportif.

L'interface web doit permettre de passer facilement d'un module à l'autre sans perte de contexte.

---

# 2. Positionnement visuel

## 2.1 Intention graphique

L'identité visuelle doit évoquer :

- la natation ;
- la performance ;
- la précision ;
- la confiance ;
- la modernité ;
- la gestion professionnelle ;
- la donnée sportive.

Le rendu doit être plus proche d'un **SaaS sportif professionnel** que d'un simple outil associatif.

Références d'esprit :

- dashboard moderne type Linear, Vercel, Notion Calendar, Stripe Dashboard ;
- application sportive premium ;
- interface analytique sobre ;
- environnement clair, fluide, orienté action.

---

# 3. Palette de couleurs

## 3.1 Couleurs principales

### Bleu profond — couleur de marque principale

- Nom : `Deep Pool Blue`
- Hex : `#0B1F3A`
- Usage : sidebar, header premium, textes forts, fonds institutionnels.

### Bleu compétition — couleur d'action principale

- Nom : `Competition Blue`
- Hex : `#006DFF`
- Usage : boutons principaux, liens actifs, onglets sélectionnés, actions importantes.

### Cyan aquatique — couleur secondaire

- Nom : `Aqua Cyan`
- Hex : `#00C2FF`
- Usage : accents, badges sportifs, graphiques, focus states, éléments liés aux performances.

### Vert performance — validation et progression

- Nom : `Performance Green`
- Hex : `#16A34A`
- Usage : présence validée, objectif atteint, progression positive, dossier complet.

### Orange alerte — vigilance

- Nom : `Alert Orange`
- Hex : `#F97316`
- Usage : absence répétée, dossier incomplet, paiement partiel, attention sportive.

### Rouge critique

- Nom : `Critical Red`
- Hex : `#DC2626`
- Usage : erreur, absence non justifiée, paiement en retard, suppression, blessure importante.

---

## 3.2 Couleurs neutres

### Fond principal clair

- Hex : `#F6F8FB`
- Usage : fond global de l'application.

### Surface carte

- Hex : `#FFFFFF`
- Usage : cards, panels, tableaux, blocs de contenu.

### Bordure douce

- Hex : `#E5EAF2`
- Usage : contours de cartes, séparateurs, bordures de champs.

### Texte principal

- Hex : `#111827`
- Usage : titres, libellés importants.

### Texte secondaire

- Hex : `#6B7280`
- Usage : descriptions, métadonnées, labels secondaires.

### Texte désactivé

- Hex : `#9CA3AF`
- Usage : champs inactifs, informations non prioritaires.

---

## 3.3 Dégradés recommandés

### Bannière principale

```css
background: linear-gradient(135deg, #0B1F3A 0%, #006DFF 55%, #00C2FF 100%);
```

Usage : page d'accueil admin, login, header dashboard, page club.

### Bloc performance

```css
background: linear-gradient(135deg, #006DFF 0%, #00C2FF 100%);
```

Usage : cartes de performance, records personnels, progression.

### Bloc alerte douce

```css
background: linear-gradient(135deg, #FFF7ED 0%, #FFEDD5 100%);
```

Usage : alertes non critiques.

---

# 4. Typographie

## 4.1 Police recommandée

Utiliser une police moderne, lisible et professionnelle.

Recommandation principale :

```text
Inter
```

Alternatives :

- `Manrope`
- `Satoshi`
- `Plus Jakarta Sans`
- `Geist Sans`

## 4.2 Hiérarchie typographique

### Titre de page

- Taille : 28 à 32 px
- Poids : 700
- Couleur : `#111827`

### Titre de section

- Taille : 20 à 24 px
- Poids : 700

### Titre de carte

- Taille : 16 à 18 px
- Poids : 600

### Texte standard

- Taille : 14 à 15 px
- Poids : 400

### Métadonnées

- Taille : 12 à 13 px
- Poids : 500
- Couleur : `#6B7280`

---

# 5. Logo et identité club

## 5.1 Emplacements du logo

Le logo du club doit être prévu à plusieurs endroits :

1. écran de connexion ;
2. sidebar desktop ;
3. header mobile ;
4. page d'accueil dashboard ;
5. exports PDF ;
6. fiches nageurs imprimables ;
7. bilans de saison ;
8. emails automatiques ;
9. bannières de communication.

## 5.2 Formats à prévoir

Le système doit accepter :

- logo horizontal ;
- logo carré ;
- logo monochrome ;
- favicon ;
- icône mobile PWA.

## 5.3 Règles d'affichage

### Sidebar desktop

- Logo carré ou horizontal compact.
- Hauteur recommandée : 36 px.
- Placement : haut gauche.

### Login

- Logo centré.
- Hauteur recommandée : 72 px.
- Possibilité d'afficher une bannière visuelle liée au club.

### Exports

- Logo en haut à gauche.
- Nom du club à droite ou sous le logo.

---

# 6. Bannières

## 6.1 Types de bannières à prévoir

### Bannière institutionnelle

Usage : page d'accueil, dashboard direction, page club.

Contenu :

- logo club ;
- nom du club ;
- saison active ;
- phrase courte ;
- indicateur global.

Exemple :

```text
CPN-Analytics
Saison 2026-2027 — Pilotage sportif et administratif du club
```

### Bannière module

Chaque module important peut disposer d'une bannière compacte.

Exemples :

- Inscriptions ;
- Groupes ;
- Planning ;
- Présences ;
- Performances ;
- Compétitions ;
- Analytics.

### Bannière d'alerte

Usage : signaler une situation importante.

Exemples :

- dossiers incomplets ;
- séances non émargées ;
- paiements en retard ;
- conflits planning ;
- compétitions à préparer.

### Bannière événementielle

Usage : communication temporaire.

Exemples :

- stage vacances ;
- compétition du week-end ;
- fermeture bassin ;
- réunion parents ;
- assemblée générale.

---

## 6.2 Design des bannières

### Bannière principale dashboard

- hauteur : 180 à 240 px ;
- coins arrondis : 24 px ;
- fond dégradé bleu ;
- logo en haut à gauche ;
- titre fort ;
- chiffres clés en mini cards ;
- visuel abstrait aquatique possible côté droit.

### Bannière module

- hauteur : 96 à 128 px ;
- coins arrondis : 20 px ;
- icône du module ;
- titre ;
- description courte ;
- action principale.

### Bannière alerte

- hauteur : variable ;
- fond pastel ;
- icône d'alerte ;
- message court ;
- bouton d'action.

---

# 7. Organisation générale de l'interface web

## 7.1 Layout desktop recommandé

L'interface web doit être organisée en trois zones :

```text
+---------------------------------------------------------------+
| Topbar : recherche, saison, notifications, profil             |
+----------------------+----------------------------------------+
| Sidebar modules      | Contenu principal                      |
| Navigation           | Dashboard / fiches / tableaux          |
|                      |                                        |
+----------------------+----------------------------------------+
```

## 7.2 Sidebar principale

La sidebar doit être le centre de navigation principal.

### Largeur

- ouverte : 264 px ;
- réduite : 72 px.

### Comportement

- fixe sur desktop ;
- rétractable ;
- icônes toujours visibles ;
- libellés visibles uniquement en mode ouvert ;
- module actif clairement marqué ;
- sous-menus accessibles au clic ou au hover.

### Structure recommandée

```text
Logo club

Vue générale
- Dashboard
- Aujourd'hui
- Alertes

Gestion club
- Inscriptions
- Nageurs
- Groupes
- Entraîneurs
- Planning

Terrain
- Séances
- Émargement
- Tests entraînement

Performance
- Compétitions
- Performances
- Qualifications
- Records
- Analytics

Administration
- Documents
- Paiements
- Communication
- Exports
- Paramètres
```

## 7.3 Topbar

La topbar doit donner accès aux actions transverses.

Contenu recommandé :

- recherche globale ;
- saison active ;
- bouton changement rapide de saison ;
- raccourci création ;
- notifications ;
- profil utilisateur ;
- bouton aide ;
- statut synchronisation si nécessaire.

### Recherche globale

La recherche doit permettre de retrouver rapidement :

- nageur ;
- groupe ;
- entraîneur ;
- compétition ;
- séance ;
- document ;
- parent ;
- paiement.

Raccourci recommandé :

```text
Ctrl + K
```

---

# 8. Navigation inter-modules

## 8.1 Principe de switch rapide

L'utilisateur doit pouvoir passer d'un module à l'autre en un clic, sans revenir au dashboard.

Exemple depuis une fiche nageur :

- voir son groupe ;
- voir son planning ;
- voir ses présences ;
- voir ses performances ;
- voir ses documents ;
- voir ses paiements ;
- voir ses objectifs.

## 8.2 Navigation contextuelle

Chaque fiche importante doit contenir une navigation interne par onglets.

### Exemple fiche nageur

```text
Synthèse | Présences | Performances | Entraînement | Physique | Objectifs | Documents | Paiements | Historique
```

### Exemple fiche groupe

```text
Synthèse | Nageurs | Planning | Séances | Présences | Performances | Objectifs | Messages
```

### Exemple compétition

```text
Synthèse | Engagements | Résultats | Qualifications | Analyse | Documents
```

## 8.3 Fil d'Ariane

Chaque page profonde doit afficher un fil d'Ariane.

Exemple :

```text
Accueil > Groupes > Juniors Compétition > Fiche nageur > Tsiky
```

---

# 9. Dashboard principal

## 9.1 Objectif

Le dashboard principal doit répondre immédiatement à la question :

```text
Que se passe-t-il dans le club aujourd'hui et qu'est-ce qui nécessite une action ?
```

## 9.2 Composition

### Zone 1 — Bannière club

Contenu :

- logo ;
- nom du club ;
- saison active ;
- résumé rapide ;
- bouton action principale.

### Zone 2 — KPIs principaux

Cartes recommandées :

- adhérents actifs ;
- groupes actifs ;
- séances aujourd'hui ;
- taux de présence semaine ;
- dossiers incomplets ;
- paiements en attente ;
- qualifications récentes ;
- alertes sportives.

### Zone 3 — Aujourd'hui

Liste chronologique :

- séances du jour ;
- entraîneurs affectés ;
- groupes concernés ;
- statut émargement ;
- conflits éventuels.

### Zone 4 — Actions prioritaires

Exemples :

- valider 12 inscriptions ;
- compléter 8 dossiers ;
- émarger 3 séances ;
- traiter 4 paiements ;
- préparer 1 compétition.

### Zone 5 — Performance récente

- meilleures progressions ;
- nouveaux records ;
- qualifications obtenues ;
- nageurs à surveiller.

---

# 10. Modules et écrans principaux

## 10.1 Module Inscriptions

### Vue liste

- tableau des dossiers ;
- filtre par statut ;
- filtre par groupe souhaité ;
- filtre par âge ;
- filtre documents manquants ;
- actions rapides.

### Carte dossier

Chaque dossier doit afficher :

- nom nageur ;
- âge ;
- statut ;
- documents ;
- paiement ;
- dernière modification ;
- action recommandée.

### États visuels

- validé : vert ;
- incomplet : orange ;
- refusé : rouge ;
- en attente : bleu ;
- brouillon : gris.

---

## 10.2 Module Nageurs

### Vue liste

- table dense et filtrable ;
- photo ou avatar ;
- nom ;
- âge ;
- sexe ;
- groupe ;
- entraîneur ;
- statut inscription ;
- taux présence ;
- meilleure progression.

### Fiche nageur

La fiche nageur doit être une page pivot.

#### Header fiche nageur

Contenu :

- avatar ;
- nom/prénom ;
- âge/catégorie ;
- groupe actuel ;
- entraîneur référent ;
- badges : compétiteur, dossier complet, qualification, alerte.

#### Cartes synthèse

- présence mois ;
- meilleure performance ;
- dernière compétition ;
- progression principale ;
- objectifs en cours ;
- documents manquants.

#### Onglets

- Synthèse ;
- Présences ;
- Performances ;
- Entraînement ;
- Physique ;
- Objectifs ;
- Documents ;
- Paiements ;
- Historique.

---

## 10.3 Module Groupes

### Vue grille

Chaque groupe doit être affiché sous forme de card.

Contenu card :

- nom groupe ;
- type ;
- entraîneur ;
- effectif ;
- capacité ;
- taux présence ;
- prochaine séance ;
- indicateur niveau.

### Vue groupe

- bannière groupe ;
- effectif ;
- planning hebdomadaire ;
- entraîneurs ;
- indicateurs ;
- liste nageurs ;
- alertes.

---

## 10.4 Module Planning

### Vue calendrier

Modes obligatoires :

- jour ;
- semaine ;
- mois ;
- par groupe ;
- par entraîneur ;
- par bassin.

### Codes couleur planning

- bleu : entraînement classique ;
- cyan : test ;
- vert : séance validée ;
- orange : séance à émarger ;
- rouge : conflit ou annulation ;
- violet : compétition ;
- gris : événement club.

---

## 10.5 Module Émargement

### Interface web

L'interface doit permettre :

- sélection séance ;
- liste nageurs ;
- présence rapide ;
- absence excusée ;
- absence non excusée ;
- retard ;
- commentaire ;
- validation finale.

### Vue de contrôle

Pour les dirigeants :

- séances non émargées ;
- taux présence par groupe ;
- absences répétées ;
- entraîneurs n'ayant pas validé.

---

## 10.6 Module Performances

### Principes

Le module performance doit être premium et analytique.

### Écrans attendus

- performances compétition ;
- performances entraînement ;
- records personnels ;
- qualifications ;
- progression par nage ;
- comparaison groupe ;
- analyse bassin 25 m / 50 m ;
- grilles de qualification.

### Graphiques recommandés

- courbe d'évolution par épreuve ;
- barres de progression ;
- heatmap présence/performance ;
- radar technique ;
- timeline des records ;
- comparaison objectif/réalisé.

---

# 11. Composants UI standards

## 11.1 Boutons

### Bouton primaire

- fond : `#006DFF` ;
- texte blanc ;
- radius : 12 px ;
- hauteur : 40 à 44 px ;
- usage : action principale.

### Bouton secondaire

- fond blanc ;
- bordure `#E5EAF2` ;
- texte `#111827` ;
- usage : action secondaire.

### Bouton danger

- fond : `#DC2626` ;
- texte blanc ;
- usage : suppression ou action irréversible.

## 11.2 Cards

- fond blanc ;
- radius : 20 à 24 px ;
- ombre douce ;
- padding : 20 à 24 px ;
- bordure subtile.

## 11.3 Badges

Badges recommandés :

- `Présent` : vert ;
- `Absent` : rouge ;
- `Excusé` : orange ;
- `Qualifié` : bleu ;
- `Record` : cyan ;
- `Dossier complet` : vert ;
- `Incomplet` : orange ;
- `À traiter` : bleu.

## 11.4 Tableaux

Les tableaux doivent être :

- triables ;
- filtrables ;
- exportables ;
- avec colonnes masquables ;
- avec recherche ;
- avec actions rapides ;
- avec pagination ;
- avec sélection multiple.

## 11.5 Modales

Usage limité aux actions rapides.

Exemples :

- changer un groupe ;
- valider une inscription ;
- ajouter une performance ;
- créer une séance ;
- confirmer suppression.

---

# 12. Responsive web

## 12.1 Breakpoints

```css
mobile: 0 - 767px
tablette: 768 - 1023px
desktop: 1024 - 1439px
wide: 1440px+
```

## 12.2 Comportement desktop

- sidebar visible ;
- topbar fixe ;
- contenu en grille ;
- tableaux complets.

## 12.3 Comportement tablette

- sidebar rétractable ;
- cards en deux colonnes ;
- tableaux simplifiés ;
- filtres dans un panneau latéral.

## 12.4 Comportement mobile web

- navigation basse ;
- sidebar masquée ;
- cards empilées ;
- actions principales flottantes ;
- tableaux transformés en cartes.

---

# 13. Mode sombre

Un mode sombre doit être prévu dès la conception.

## Couleurs mode sombre

- fond principal : `#07111F` ;
- surface : `#0F172A` ;
- surface secondaire : `#111C2F` ;
- texte principal : `#F9FAFB` ;
- texte secondaire : `#CBD5E1` ;
- bordure : `#1E293B` ;
- bleu action : `#3B82F6` ;
- cyan : `#22D3EE`.

## Usage

Le mode sombre est particulièrement utile pour :

- consultation en soirée ;
- utilisation terrain ;
- dashboard TV ;
- entraîneurs en mobilité.

---

# 14. Micro-interactions

## Interactions recommandées

- hover subtil sur cards ;
- animation légère au changement d'onglet ;
- skeleton loader pendant chargement ;
- toast de confirmation ;
- feedback instantané après émargement ;
- transition douce sidebar ouverte/réduite ;
- compteur animé sur KPIs.

## Durées

- micro-transition : 150 ms ;
- changement de panel : 200 ms ;
- apparition modale : 180 ms ;
- skeleton : jusqu'à chargement.

---

# 15. Accessibilité

## Exigences

- contraste suffisant ;
- navigation clavier ;
- focus visible ;
- labels explicites ;
- boutons suffisamment grands ;
- ne pas dépendre uniquement de la couleur ;
- textes lisibles ;
- aria-label sur icônes.

## Cibles minimales

- taille bouton : 40 px minimum ;
- taille texte standard : 14 px minimum ;
- contraste texte principal : élevé ;
- focus ring visible en bleu.

---

# 16. Prompt Claude Code — UI Web

```text
Tu es un expert UI/UX senior spécialisé SaaS sportif, dashboard analytique et application web professionnelle.

Construis l'interface web de CPN-Analytics Club Manager selon la charte suivante :

- design premium, moderne, clair, professionnel ;
- identité natation, performance et data ;
- palette principale : Deep Pool Blue #0B1F3A, Competition Blue #006DFF, Aqua Cyan #00C2FF ;
- interface responsive desktop/tablette/mobile ;
- sidebar principale rétractable ;
- topbar avec recherche globale, saison active, notifications et profil ;
- navigation inter-modules rapide ;
- modules accessibles en un clic ;
- dashboard principal avec bannière club, KPIs, séances du jour, alertes et performances récentes ;
- fiches nageurs et groupes avec onglets contextuels ;
- composants cards, badges, tableaux, filtres, modales et graphiques ;
- prévoir emplacements pour logo club, bannières institutionnelles, bannières modules et bannières d'alerte ;
- prévoir mode sombre ;
- UX fluide, micro-interactions propres, transitions sobres.

Produis une interface cohérente avec une application SaaS professionnelle. Priorise la lisibilité, la rapidité d'accès aux modules et l'exploitation des données sportives.
```

---

# 17. Critères d'acceptation UI Web

L'interface web est validée si :

- les modules principaux sont accessibles en un clic depuis la sidebar ;
- le dashboard donne une vision immédiate de la situation du club ;
- le passage d'un module à l'autre est naturel ;
- les fiches nageurs et groupes sont compréhensibles sans formation ;
- les données importantes ressortent visuellement ;
- les couleurs sont cohérentes et professionnelles ;
- les bannières et logos sont prévus ;
- l'interface reste lisible sur tablette ;
- les tableaux sont exploitables ;
- le rendu est crédible pour un club de natation professionnel.
