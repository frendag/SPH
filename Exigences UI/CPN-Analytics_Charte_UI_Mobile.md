# CPN-Analytics — Charte graphique et UX/UI Mobile

## 1. Objectif du document

Ce document définit l'expérience mobile de la plateforme **CPN-Analytics Club Manager**.

L'interface mobile doit être pensée en priorité pour :

- les entraîneurs au bord du bassin ;
- les nageurs ;
- les parents ;
- le bureau en consultation rapide ;
- le directeur sportif en déplacement.

Le mobile ne doit pas être une simple version réduite du web. Il doit être une interface terrain, rapide, tactile, claire, avec des parcours courts.

---

# 2. Principes UX Mobile

## 2.1 Objectif principal

Sur mobile, l'utilisateur doit pouvoir réaliser une action importante en moins de trois interactions.

Exemples :

- émarger une séance ;
- déclarer une absence ;
- consulter le planning ;
- saisir une performance ;
- voir la fiche d'un nageur ;
- envoyer une notification de groupe ;
- consulter une alerte.

## 2.2 Philosophie mobile

L'interface mobile doit être :

- tactile ;
- fluide ;
- lisible en extérieur ou en bassin ;
- adaptée à une utilisation debout ;
- efficace avec une seule main ;
- rapide même avec une connexion moyenne ;
- centrée sur les tâches du jour.

---

# 3. Palette mobile

La palette mobile reprend l'identité web, avec des contrastes renforcés.

## Couleurs principales

### Fond clair

- Hex : `#F6F8FB`
- Usage : fond général.

### Surface card

- Hex : `#FFFFFF`
- Usage : cartes, listes, panels.

### Bleu principal

- Hex : `#006DFF`
- Usage : action principale, onglet actif, boutons flottants.

### Bleu profond

- Hex : `#0B1F3A`
- Usage : header, texte fort, fond premium.

### Cyan accent

- Hex : `#00C2FF`
- Usage : performance, chrono, records, progression.

### Vert présence

- Hex : `#16A34A`
- Usage : présent, validé, objectif atteint.

### Orange attention

- Hex : `#F97316`
- Usage : retard, excusé, dossier incomplet.

### Rouge absence

- Hex : `#DC2626`
- Usage : absent, erreur, alerte critique.

---

# 4. Logo et branding mobile

## 4.1 Emplacements du logo

Le logo doit être prévu dans :

- écran de lancement ;
- écran de connexion ;
- header de l'accueil mobile ;
- menu profil ;
- exports ou partages PDF ;
- notifications enrichies si possible ;
- icône PWA ou application native.

## 4.2 Logo mobile

Le format mobile prioritaire est le logo carré ou monogramme.

Recommandations :

- taille header : 32 à 40 px ;
- taille écran login : 80 à 96 px ;
- icône app : 1024 x 1024 px source ;
- favicon/PWA : 512 x 512 px minimum.

## 4.3 Bannière mobile

Les bannières mobiles doivent être compactes.

### Bannière accueil

- hauteur : 120 à 160 px ;
- radius : 24 px ;
- fond dégradé bleu ;
- logo ;
- message court ;
- indicateur du jour.

Exemple :

```text
Bonjour Coach
4 séances aujourd'hui · 2 à émarger
```

### Bannière groupe

- hauteur : 96 à 120 px ;
- nom groupe ;
- effectif ;
- prochaine séance ;
- bouton action.

### Bannière alerte

- hauteur : variable ;
- couleur douce ;
- icône ;
- message court ;
- action directe.

---

# 5. Architecture de navigation mobile

## 5.1 Navigation principale

La navigation mobile doit utiliser une **bottom navigation bar**.

### Onglets recommandés entraîneur

```text
Aujourd'hui | Groupes | Émargement | Performance | Plus
```

### Onglets recommandés parent

```text
Accueil | Planning | Présences | Messages | Plus
```

### Onglets recommandés nageur

```text
Accueil | Planning | Performances | Objectifs | Plus
```

### Onglets recommandés direction

```text
Dashboard | Alertes | Groupes | Planning | Plus
```

## 5.2 Bouton d'action flottant

Un bouton flottant doit être présent selon le contexte.

Exemples :

- `+ Performance` ;
- `Émarger` ;
- `Déclarer absence` ;
- `Message groupe` ;
- `Créer séance`.

Position :

- bas droite ;
- au-dessus de la bottom bar ;
- taille : 56 px ;
- radius : 50 % ;
- couleur : `#006DFF`.

## 5.3 Menu Plus

Le menu `Plus` doit regrouper les fonctions secondaires.

Contenu possible :

- profil ;
- documents ;
- paiements ;
- compétitions ;
- paramètres ;
- aide ;
- changement de saison ;
- déconnexion.

---

# 6. Accueil mobile par rôle

## 6.1 Accueil entraîneur

L'accueil entraîneur doit afficher en priorité les actions terrain.

### Contenu recommandé

1. bannière du jour ;
2. séances du jour ;
3. bouton émargement rapide ;
4. groupes affectés ;
5. alertes nageurs ;
6. performances récentes ;
7. raccourci saisie chrono.

### Exemple structure

```text
Bonjour Julien
Aujourd'hui — Mardi 12 septembre

[4 séances prévues]
[2 séances à émarger]
[1 alerte absence]

Prochaine séance
Juniors Compétition · 18:00 · Bassin 25 m
[Bouton : Ouvrir l'émargement]
```

## 6.2 Accueil parent

L'accueil parent doit être simple et rassurant.

### Contenu recommandé

- prochain entraînement ;
- statut présence récent ;
- documents à fournir ;
- paiements ;
- messages du club ;
- bouton déclarer absence.

## 6.3 Accueil nageur

L'accueil nageur doit être motivant.

### Contenu recommandé

- prochaine séance ;
- dernière performance ;
- progression ;
- objectif en cours ;
- record personnel ;
- message coach.

## 6.4 Accueil direction

L'accueil direction doit être synthétique.

### Contenu recommandé

- adhérents actifs ;
- séances du jour ;
- émargements manquants ;
- dossiers incomplets ;
- paiements en retard ;
- alertes sportives.

---

# 7. Module mobile Émargement

## 7.1 Objectif

Permettre à l'entraîneur d'émarger une séance complète en moins de deux minutes.

## 7.2 Écran liste des séances

Chaque séance doit être affichée en card.

Contenu :

- heure ;
- groupe ;
- bassin ;
- nombre de nageurs attendus ;
- statut émargement ;
- bouton ouvrir.

## 7.3 Écran émargement

### Header

- nom groupe ;
- horaire ;
- bassin ;
- compteur présents/total ;
- bouton valider.

### Liste nageurs

Chaque nageur est une ligne tactile.

Contenu :

- avatar ou initiales ;
- nom ;
- catégorie ;
- état de présence ;
- action rapide.

### Actions rapides

Pour chaque nageur :

- présent ;
- absent ;
- excusé ;
- retard ;
- blessé ;
- commentaire.

## 7.4 Interaction recommandée

Un tap sur la ligne fait passer rapidement :

```text
Non renseigné -> Présent -> Absent -> Excusé -> Retard
```

Un appui long ouvre les détails.

## 7.5 Barre de validation

En bas d'écran :

```text
18 présents · 2 absents · 1 retard
[Valider la séance]
```

---

# 8. Module mobile Performance entraînement

## 8.1 Objectif

Permettre la saisie rapide de chronos et mesures pendant ou après une séance.

## 8.2 Écran saisie chrono

Champs principaux :

- groupe ;
- séance ;
- nageur ;
- type de test ;
- distance ;
- nage ;
- temps ;
- commentaire.

## 8.3 Saisie rapide

L'interface doit proposer :

- pavé chrono ;
- sélection nageur rapide ;
- duplication du test pour plusieurs nageurs ;
- sauvegarde instantanée ;
- mode série.

## 8.4 Mode série

Exemple :

```text
8 x 50 NL départ 1'00
```

Pour chaque nageur :

- temps répétition 1 ;
- temps répétition 2 ;
- etc. ;
- moyenne ;
- meilleur temps ;
- régularité.

---

# 9. Module mobile Groupes

## 9.1 Vue groupes

Chaque groupe doit être une card claire.

Contenu :

- nom groupe ;
- entraîneur ;
- effectif ;
- prochaine séance ;
- taux présence ;
- alertes.

## 9.2 Fiche groupe mobile

Onglets recommandés :

```text
Synthèse | Nageurs | Planning | Présences | Perf
```

## 9.3 Liste nageurs

La liste doit être optimisée pour le tactile.

Chaque ligne :

- avatar ;
- nom ;
- âge/catégorie ;
- présence récente ;
- icône alerte si besoin.

---

# 10. Module mobile Fiche nageur

## 10.1 Header fiche nageur

Contenu :

- avatar ;
- nom ;
- âge ;
- catégorie ;
- groupe ;
- badges.

## 10.2 Cartes synthèse

- présence mois ;
- meilleure performance ;
- dernier chrono ;
- objectif principal ;
- progression ;
- alerte éventuelle.

## 10.3 Onglets

```text
Résumé | Présences | Performances | Tests | Objectifs | Docs
```

## 10.4 Actions rapides

Selon rôle :

- saisir performance ;
- ajouter commentaire ;
- déclarer absence ;
- envoyer message ;
- changer groupe ;
- consulter documents.

---

# 11. Module mobile Planning

## 11.1 Vue planning

Modes nécessaires :

- aujourd'hui ;
- semaine ;
- liste ;
- calendrier compact.

## 11.2 Card séance

Chaque séance affiche :

- heure ;
- groupe ;
- lieu ;
- entraîneur ;
- statut ;
- action.

## 11.3 Codes couleur

- bleu : prévue ;
- vert : validée ;
- orange : à émarger ;
- rouge : annulée/conflit ;
- violet : compétition.

---

# 12. Module mobile Messages et notifications

## 12.1 Centre de notifications

Classer les notifications :

- importantes ;
- séances ;
- documents ;
- paiements ;
- performances ;
- messages club.

## 12.2 Notification card

Contenu :

- icône ;
- titre ;
- message court ;
- date ;
- action directe.

## 12.3 Actions rapides

- confirmer lecture ;
- ouvrir séance ;
- ouvrir document ;
- déclarer absence ;
- répondre si autorisé.

---

# 13. Composants mobiles

## 13.1 Cards

- radius : 20 à 24 px ;
- padding : 16 px ;
- fond blanc ;
- ombre douce ;
- séparation claire entre les sections.

## 13.2 Boutons

### Bouton principal

- hauteur : 48 à 52 px ;
- radius : 14 px ;
- fond bleu ;
- texte blanc ;
- pleine largeur si action majeure.

### Boutons segmentés

Utilisés pour :

- filtres ;
- statuts présence ;
- onglets courts.

### Boutons présence

- `Présent` : vert ;
- `Absent` : rouge ;
- `Excusé` : orange ;
- `Retard` : bleu ;
- `Blessé` : violet ou rouge doux.

## 13.3 Inputs

- hauteur : 48 px minimum ;
- radius : 12 px ;
- label visible ;
- aide contextuelle ;
- clavier adapté selon type.

## 13.4 Bottom sheets

À utiliser pour :

- filtres ;
- sélection nageur ;
- commentaire ;
- détail présence ;
- options avancées.

## 13.5 Toasts

Exemples :

- présence enregistrée ;
- séance validée ;
- performance sauvegardée ;
- message envoyé ;
- synchronisation réussie.

---

# 14. Offline et synchronisation

## 14.1 Besoin

L'environnement bassin peut avoir une connexion instable.

Le mobile doit prévoir un fonctionnement partiel hors ligne pour :

- émargement ;
- saisie de performances ;
- commentaires de séance ;
- consultation des séances déjà chargées.

## 14.2 États de synchronisation

- synchronisé ;
- en attente ;
- erreur ;
- conflit ;
- brouillon local.

## 14.3 Affichage

Un indicateur discret doit être visible :

```text
Synchronisé
3 éléments en attente
Connexion instable
```

---

# 15. Mode sombre mobile

## 15.1 Usage prioritaire

Le mode sombre doit être particulièrement soigné sur mobile.

Il est utile pour :

- utilisation le soir ;
- consultation rapide ;
- confort visuel ;
- usage terrain prolongé.

## 15.2 Couleurs

- fond : `#07111F` ;
- surface : `#0F172A` ;
- surface élevée : `#111C2F` ;
- texte principal : `#F9FAFB` ;
- texte secondaire : `#CBD5E1` ;
- bordure : `#1E293B` ;
- action : `#3B82F6` ;
- accent : `#22D3EE`.

---

# 16. Gestes tactiles

## Gestes recommandés

- tap : action principale ;
- long press : options avancées ;
- swipe droite : marquer présent ;
- swipe gauche : marquer absent ;
- pull to refresh : mise à jour ;
- bottom sheet drag : fermeture ;
- haptic feedback sur validation importante.

## Attention

Les gestes ne doivent jamais être la seule manière d'effectuer une action. Un bouton visible doit toujours exister pour les actions importantes.

---

# 17. Accessibilité mobile

## Exigences

- zones tactiles de 44 px minimum ;
- contraste élevé ;
- texte minimum 14 px ;
- boutons principaux 48 px minimum ;
- focus visible ;
- compatibilité lecteur d'écran ;
- états non basés uniquement sur la couleur ;
- feedback visuel et textuel.

---

# 18. Prompt Claude Code — UI Mobile

```text
Tu es un expert UI/UX mobile senior spécialisé application terrain, SaaS sportif et expérience tactile rapide.

Construis l'interface mobile de CPN-Analytics Club Manager selon la charte suivante :

- mobile-first ;
- interface premium, moderne, sportive et professionnelle ;
- usage principal au bord du bassin par les entraîneurs ;
- navigation par bottom tab bar ;
- actions importantes accessibles en moins de trois interactions ;
- émargement d'une séance en moins de deux minutes ;
- saisie rapide des performances d'entraînement ;
- fiches nageurs claires et synthétiques ;
- planning lisible ;
- cards tactiles ;
- boutons larges ;
- bottom sheets pour les actions secondaires ;
- bouton d'action flottant selon le contexte ;
- prévoir logo, splash screen, icône PWA/app, bannières compactes ;
- prévoir mode sombre ;
- prévoir états offline/synchronisation ;
- palette : Deep Pool Blue #0B1F3A, Competition Blue #006DFF, Aqua Cyan #00C2FF, Performance Green #16A34A, Alert Orange #F97316, Critical Red #DC2626.

L'application mobile ne doit pas être une simple réduction du web. Elle doit être une application de terrain, rapide, fluide, tactile et centrée sur les tâches du jour.
```

---

# 19. Critères d'acceptation UI Mobile

L'interface mobile est validée si :

- un entraîneur peut accéder à l'émargement depuis l'accueil en un tap ;
- l'émargement complet d'un groupe est réalisable rapidement ;
- la saisie d'un chrono est simple et utilisable sur le terrain ;
- les modules principaux sont accessibles depuis la bottom bar ;
- les parents comprennent immédiatement le planning et les messages ;
- les nageurs voient facilement leurs performances et objectifs ;
- les bannières et logos sont intégrés proprement ;
- le mode sombre est lisible ;
- les états hors ligne sont clairs ;
- l'expérience mobile est plus rapide que l'interface web pour les tâches terrain.
