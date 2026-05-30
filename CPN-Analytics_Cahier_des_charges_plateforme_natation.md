**CPN-ANALYTICS**

**Cahier des charges fonctionnel et technique**

**Plateforme complète de gestion d’un club de natation**

*Version de cadrage projet - orientation club professionnel*

| **Projet**       | CPN-Analytics - Extension gestion club                                 |
|------------------|------------------------------------------------------------------------|
| **Périmètre**    | Inscriptions, groupes, planning, émargement, performances et analytics |
| **Public cible** | Bureau, direction sportive, entraîneurs, nageurs, familles             |
| **Livrable**     | Cahier des charges + prompt détaillé + architecture modulaire          |
| **Date**         | 30 mai 2026                                                            |

# Sommaire

1.  1\. Vision générale et objectifs

2.  2\. Utilisateurs et rôles

3.  3\. Architecture fonctionnelle globale

4.  4\. Architecture technique cible

5.  5\. Cahier des charges par module

6.  6\. Modèle de données conceptuel

7.  7\. Règles métier structurantes

8.  8\. Parcours utilisateur principaux

9.  9\. Exigences UX/UI, sécurité et qualité

10. 10\. Roadmap recommandée et MVP

11. 11\. Prompt détaillé pour poursuivre le projet

# 1. Vision générale et objectifs

La plateforme vise à centraliser l’ensemble des processus d’un club de
natation dans un environnement numérique unique, structuré et
professionnel. Elle doit devenir un ERP sportif spécialisé natation,
intégrant une dimension métier forte : niveaux de pratique, catégories
d’âge, groupes de niveau, objectifs sportifs, assiduité, progression,
qualification, charge d’entraînement et analyse de performance.

- Centraliser les inscriptions, réinscriptions, dossiers administratifs
  et paiements.

- Piloter les groupes, les entraîneurs, les bassins, les créneaux et les
  séances.

- Assurer l’émargement rapide à chaque entraînement, notamment depuis
  mobile.

- Mesurer les performances en compétition et à l’entraînement.

- Suivre les mesures physiques autorisées : taille, poids, mobilité,
  force, fréquence cardiaque, tests internes.

- Produire des tableaux de bord exploitables par le bureau, la direction
  sportive, les entraîneurs, les familles et les nageurs.

- Capitaliser sur l’application mobile CPN existante et sur les modules
  CPN-Analytics déjà orientés compétition et performance.

## Objectifs opérationnels

| **Axe**         | **Objectif**                                                                               |
|-----------------|--------------------------------------------------------------------------------------------|
| Administratif   | Réduire le recours aux fichiers Excel dispersés et fiabiliser les dossiers adhérents.      |
| Sportif         | Permettre un suivi individualisé de la progression et des objectifs.                       |
| Organisationnel | Simplifier la constitution des groupes, l’affectation des entraîneurs et la planification. |
| Data            | Transformer les présences, tests et résultats en indicateurs pilotables.                   |
| Stratégique     | Faire évoluer le club vers un fonctionnement professionnel, scalable et mesurable.         |

# 2. Utilisateurs et rôles

| **Rôle**                     | **Responsabilités principales**                                                                     |
|------------------------------|-----------------------------------------------------------------------------------------------------|
| Administrateur général       | Paramétrage complet, gestion des utilisateurs, rôles, saisons, droits et supervision.               |
| Bureau du club               | Validation des inscriptions, suivi administratif, documents, paiements, exports et communications.  |
| Directeur sportif            | Structuration des groupes, affectation des entraîneurs, suivi des performances et pilotage sportif. |
| Entraîneur                   | Émargement, saisie des tests, consultation des fiches nageurs, commentaires et suivi des objectifs. |
| Nageur                       | Consultation du planning, des performances, objectifs et historique sportif.                        |
| Parent ou représentant légal | Inscription, documents, paiements, absences, planning et communications concernant ses enfants.     |

# 3. Architecture fonctionnelle globale

La plateforme doit être découpée en modules indépendants mais
interconnectés. Chaque module doit pouvoir évoluer sans remettre en
cause l’ensemble du système.

- Utilisateurs, rôles et droits

- Saisons sportives

- Inscriptions et réinscriptions

- Dossiers administratifs

- Nageurs

- Groupes

- Constitution automatique ou assistée des groupes

- Entraîneurs

- Planning

- Séances d’entraînement

- Émargement

- Performance sportive compétition

- Performance physique et biométrique

- Performance à l’entraînement

- Compétitions

- Objectifs sportifs

- Tableaux de bord et analytics

- Communication

- Finances et cotisations

- Documents et exports

- Notifications et alertes

- Paramétrage club

- API et intégrations externes

- Application mobile

- Sécurité, conformité et traçabilité

# 4. Architecture technique cible

L’architecture recommandée est une architecture modulaire : backend API
centralisé, frontend web responsive, application mobile ou PWA, base de
données relationnelle, couche analytics, système d’import/export et
gestion fine des rôles.

| **Couche**        | **Recommandation**                                                                    |
|-------------------|---------------------------------------------------------------------------------------|
| Backend           | Python FastAPI ou Django. API REST ou GraphQL. Authentification JWT/OAuth2.           |
| Frontend web      | React, Next.js ou Vue.js. Interface responsive desktop, tablette et mobile.           |
| Mobile            | PWA installable en priorité, puis Flutter ou React Native si besoin de natif.         |
| Base de données   | PostgreSQL, avec historisation des entités sensibles et vues analytiques.             |
| Cache / jobs      | Redis et workers pour imports volumineux, notifications et calculs différés.          |
| Stockage fichiers | S3 compatible, stockage privé ou cloud sécurisé pour documents.                       |
| Analytics         | Vues matérialisées, calculs de scoring, graphiques interactifs, exports XLSX/CSV/PDF. |
| DevOps            | Docker, CI/CD, environnements dev/staging/prod, sauvegardes et monitoring.            |

# 5. Cahier des charges par module

## 5.1 Utilisateurs, rôles et droits

Objectif : Gérer l’accès sécurisé à la plateforme selon le profil
utilisateur.

### Fonctionnalités principales

- Création de comptes

- Connexion sécurisée

- Récupération de mot de passe

- Gestion des rôles

- Permissions par groupe, saison et type de données

- Journalisation des connexions

### Règles métier / exigences

- Un entraîneur ne voit que ses groupes sauf délégation.

- Un parent ne voit que les données de ses enfants.

- Les données sensibles sont protégées par des permissions spécifiques.

## 5.2 Saisons sportives

Objectif : Structurer les données autour d’une saison sportive.

### Fonctionnalités principales

- Création de saison

- Duplication des paramètres précédents

- Archivage

- Comparaison intersaison

- Gestion des périodes et vacances

### Règles métier / exigences

- Les groupes sont rattachés à une saison.

- Les règles tarifaires, grilles et créneaux peuvent varier selon la
  saison.

## 5.3 Inscriptions et réinscriptions

Objectif : Permettre aux familles et nageurs de s’inscrire ou se
réinscrire en ligne.

### Fonctionnalités principales

- Formulaire d’inscription

- Réinscription préremplie

- Dépôt de documents

- Acceptation des règlements

- Choix du paiement

- Validation par le bureau

- Suivi du statut

### Règles métier / exigences

- Un dossier validé doit être complet.

- Le bureau doit pouvoir marquer un dossier incomplet avec commentaire.

- La validation sportive et administrative peuvent être séparées.

## 5.4 Dossiers administratifs

Objectif : Centraliser le suivi administratif des adhérents.

### Fonctionnalités principales

- Documents obligatoires

- Alertes documents manquants

- Expiration des certificats

- Validation documentaire

- Commentaires internes

- Export dossiers incomplets

### Règles métier / exigences

- Chaque document doit avoir un statut.

- Les documents expirés doivent déclencher une alerte.

## 5.5 Fiche nageur

Objectif : Disposer d’une fiche complète et historisée.

### Fonctionnalités principales

- Identité

- Coordonnées

- Responsables légaux

- Groupe actuel

- Planning

- Présences

- Performances compétition

- Tests entraînement

- Mesures physiques

- Objectifs

- Documents

- Paiements

### Règles métier / exigences

- La fiche nageur est le point central de consultation.

- Une vue synthétique et une vue détaillée doivent coexister.

## 5.6 Gestion des groupes

Objectif : Créer et piloter les groupes d’entraînement.

### Fonctionnalités principales

- Types de groupes

- Capacité maximale

- Niveau requis

- Âge cible

- Entraîneur référent

- Nageurs associés

- Historique des entrées/sorties

- Statistiques groupe

### Règles métier / exigences

- La capacité doit être contrôlée.

- Un groupe appartient à une saison.

- Les changements doivent être historisés.

## 5.7 Constitution automatique ou assistée des groupes

Objectif : Aider à affecter les nageurs dans les bons groupes.

### Fonctionnalités principales

- Moteur de proposition

- Règles paramétrables

- Scoring d’affectation

- Simulation de répartition

- Détection des incohérences

- Validation humaine

### Règles métier / exigences

- Le système propose mais n’impose pas.

- La validation finale reste humaine.

- Les critères doivent être transparents.

## 5.8 Entraîneurs

Objectif : Centraliser les fiches entraîneurs et affectations.

### Fonctionnalités principales

- Diplômes

- Spécialités

- Disponibilités

- Groupes affectés

- Créneaux associés

- Remplacement ponctuel

- Planning individuel

### Règles métier / exigences

- Un entraîneur ne peut pas être affecté sur deux créneaux simultanés.

- Les droits applicatifs découlent des affectations.

## 5.9 Planning

Objectif : Planifier les entraînements et événements.

### Fonctionnalités principales

- Planning hebdomadaire

- Créneaux par groupe

- Créneaux par entraîneur

- Bassins et lignes d’eau

- Jours fériés

- Annulations

- Séances exceptionnelles

- Stages et compétitions

### Règles métier / exigences

- Détecter les conflits bassin, groupe et entraîneur.

- Générer les séances réelles depuis le planning.

## 5.10 Séances d’entraînement

Objectif : Créer et suivre chaque séance réelle.

### Fonctionnalités principales

- Génération automatique

- Création manuelle

- Annulation

- Remplacement entraîneur

- Contenu de séance

- Objectif technique

- Volume prévu

- Intensité prévue

- Commentaires collectifs

### Règles métier / exigences

- Une présence doit toujours être liée à une séance.

- Une séance validée doit être historisée.

## 5.11 Émargement et assiduité

Objectif : Enregistrer rapidement les présences à chaque séance.

### Fonctionnalités principales

- Liste des nageurs attendus

- Présent / absent / retard / excusé

- Commentaire individuel

- Émargement mobile

- Validation de séance

- Statistiques d’assiduité

- Alertes absences répétées

### Règles métier / exigences

- L’émargement doit être réalisable en moins de deux minutes.

- Les modifications après validation doivent être tracées.

## 5.12 Performance sportive compétition

Objectif : Suivre les performances officielles.

### Fonctionnalités principales

- Import FFN ou fichier compétition

- Saisie manuelle

- Records personnels

- Records club

- Classements

- Grilles de qualification

- Graphiques par nage

- Comparaison bassin 25m / 50m

### Règles métier / exigences

- Le moteur doit tenir compte du sexe, âge, saison, épreuve, bassin,
  catégorie et grille applicable.

- Les temps doivent être stockés en centièmes pour fiabiliser les
  comparaisons.

## 5.13 Performance physique et biométrique

Objectif : Suivre l’évolution physique dans un cadre sécurisé.

### Fonctionnalités principales

- Taille

- Poids

- IMC

- Envergure

- Fréquence cardiaque de repos

- Mobilité

- Force

- Gainage

- Souplesse

- Blessures déclarées

- Restrictions d’entraînement

### Règles métier / exigences

- Les données physiques sont sensibles.

- L’accès doit être limité aux profils habilités.

- Les variations importantes peuvent déclencher des alertes.

## 5.14 Performance à l’entraînement

Objectif : Mesurer les performances réalisées pendant les séances.

### Fonctionnalités principales

- Tests chronométrés

- Séries d’entraînement

- Temps par répétition

- Départs

- Virages

- Coulées

- Fréquence de nage

- Amplitude

- RPE

- Charge d’entraînement

### Règles métier / exigences

- Les mesures doivent être saisissables depuis mobile.

- Les données doivent être liées à une séance, un nageur et un type de
  test.

## 5.15 Compétitions

Objectif : Gérer préparation, engagements et analyse.

### Fonctionnalités principales

- Calendrier

- Compétitions ciblées

- Nageurs sélectionnés

- Épreuves prévues

- Engagements

- Résultats

- Bilan compétition

- Suivi logistique

### Règles métier / exigences

- Une compétition passe par des statuts : prévue, engagements ouverts,
  engagée, terminée, résultats importés, archivée.

## 5.16 Objectifs sportifs individuels

Objectif : Définir et suivre des objectifs personnalisés.

### Fonctionnalités principales

- Objectifs par saison

- Objectifs par épreuve

- Objectifs chronométriques

- Objectifs techniques

- Objectifs d’assiduité

- Suivi de réalisation

- Bilan de période

### Règles métier / exigences

- Un objectif doit avoir une cible, une période et un statut.

- L’objectif peut être validé par l’entraîneur.

## 5.17 Tableaux de bord et analytics

Objectif : Fournir une vision claire de l’activité du club.

### Fonctionnalités principales

- Dashboard direction

- Dashboard directeur sportif

- Dashboard entraîneur

- Dashboard nageur

- Dashboard parent

- Graphiques interactifs

- Filtres saison/groupe/catégorie

### Règles métier / exigences

- Les indicateurs doivent être calculés de manière traçable.

- Les tableaux de bord doivent respecter les droits utilisateur.

## 5.18 Communication

Objectif : Faciliter les échanges entre club, familles et entraîneurs.

### Fonctionnalités principales

- Annonces globales

- Messages par groupe

- Messages par compétition

- Emails

- Notifications push

- SMS optionnels

- Accusés de lecture

- Historique

### Règles métier / exigences

- Les messages doivent pouvoir cibler une population précise.

- Les communications sensibles doivent être historisées.

## 5.19 Finances et cotisations

Objectif : Suivre paiements et cotisations.

### Fonctionnalités principales

- Tarifs par saison

- Tarifs par groupe

- Remises famille

- Paiement fractionné

- Échéances

- Statuts de paiement

- Relances

- Exports comptables

### Règles métier / exigences

- Un dossier peut être validé sportivement mais rester en attente de
  paiement.

- Les statuts de paiement doivent être visibles par le bureau.

## 5.20 Documents et exports

Objectif : Produire les fichiers nécessaires au pilotage.

### Fonctionnalités principales

- Exports adhérents

- Exports groupes

- Exports présences

- Exports absences

- Exports performances

- Exports paiements

- Bilans individuels

- Bilans groupe

### Règles métier / exigences

- Formats attendus : XLSX, CSV, PDF et JSON pour API.

## 5.21 Notifications et alertes

Objectif : Automatiser les rappels et signalements.

### Fonctionnalités principales

- Dossier incomplet

- Document expiré

- Paiement en retard

- Absences répétées

- Qualification atteinte

- Séance non émargée

- Conflit planning

### Règles métier / exigences

- Les alertes doivent être configurables.

- Chaque alerte doit avoir un statut de traitement.

## 5.22 Paramétrage club

Objectif : Adapter la plateforme au fonctionnement local.

### Fonctionnalités principales

- Logo

- Sites et bassins

- Saisons

- Groupes types

- Catégories

- Tarifs

- Documents requis

- Règles de groupe

- Grilles

- Modèles de messages

### Règles métier / exigences

- Les paramètres doivent être historisés par saison quand ils
  influencent les calculs.

## 5.23 API et intégrations

Objectif : Connecter la plateforme aux outils externes.

### Fonctionnalités principales

- FFN ou exports fédéraux

- Google/Outlook Calendar

- Paiement

- Email

- SMS

- Application mobile CPN

- Excel

- CSV

### Règles métier / exigences

- Toutes les API doivent être sécurisées.

- Les imports doivent produire un rapport d’erreurs.

## 5.24 Application mobile

Objectif : Offrir une interface terrain rapide.

### Fonctionnalités principales

- Séances du jour

- Émargement rapide

- Saisie performance

- Commentaire

- Fiche nageur

- Objectifs

- Notifications

- Signalement d’absence

### Règles métier / exigences

- Priorité à la rapidité et à l’usage bord de bassin.

- Prévoir un mode connexion instable avec synchronisation différée.

## 5.25 Sécurité, conformité et traçabilité

Objectif : Garantir la protection des données.

### Fonctionnalités principales

- Authentification sécurisée

- Mots de passe chiffrés

- Journalisation

- Historique des modifications

- Sauvegardes

- Consentements

- Export/suppression/anonymisation

- Protection des mineurs

### Règles métier / exigences

- Les données santé/physiques et mineurs doivent bénéficier d’un niveau
  de protection renforcé.

# 6. Modèle de données conceptuel

| **Entité**               | **Champs clés**                                                                                |
|--------------------------|------------------------------------------------------------------------------------------------|
| Utilisateur              | id, nom, prénom, email, téléphone, rôle, statut, date de création                              |
| Nageur                   | id, utilisateur lié, date de naissance, sexe, catégorie, statut, numéro licence, groupe actuel |
| Responsable légal        | id, nom, prénom, email, téléphone, lien avec le nageur                                         |
| Saison                   | id, nom, date début, date fin, statut                                                          |
| Groupe                   | id, nom, type, niveau, capacité, saison, entraîneur référent                                   |
| Entraîneur               | id, utilisateur lié, diplômes, spécialités, disponibilités                                     |
| Séance                   | id, groupe, entraîneur, date, heure début, heure fin, lieu, statut                             |
| Présence                 | id, séance, nageur, statut, commentaire                                                        |
| Performance compétition  | id, nageur, compétition, épreuve, temps, date, bassin, niveau qualification                    |
| Performance entraînement | id, nageur, séance, type test, mesure, valeur, commentaire                                     |
| Mesure physique          | id, nageur, date, type mesure, valeur, unité, commentaire                                      |
| Objectif                 | id, nageur, saison, type, cible, statut                                                        |
| Document                 | id, nageur, type, fichier, statut, date expiration                                             |
| Paiement                 | id, nageur, saison, montant, statut, échéance                                                  |

# 7. Règles métier structurantes

- Une performance doit toujours être contextualisée : nageur, date,
  épreuve, bassin, sexe, âge, catégorie, grille et saison.

- Une présence doit être liée à une séance réelle.

- Les groupes sont saisonniers et les changements de groupe doivent être
  historisés.

- Les droits doivent être contextuels : groupe, rôle, saison, relation
  parent/enfant.

- Les données physiques et de santé sont sensibles et ne doivent pas
  être visibles par défaut.

- Toute modification importante doit être tracée : groupe, performance,
  inscription, présence, document, entraîneur.

- Le système doit privilégier l’aide à la décision plutôt que
  l’automatisation irréversible.

# 8. Parcours utilisateur principaux

## Parcours inscription

12. Le parent crée un compte.

13. Il ajoute le nageur.

14. Il remplit le formulaire.

15. Il dépose les documents.

16. Il accepte les règlements.

17. Il sélectionne un mode de paiement.

18. Le dossier passe en validation.

19. Le bureau vérifie le dossier.

20. Le nageur est validé.

21. Le directeur sportif l’affecte à un groupe.

## Parcours constitution des groupes

22. Le directeur sportif ouvre la saison.

23. Les nageurs inscrits sont listés.

24. Le moteur propose des affectations.

25. Les entraîneurs consultent les propositions.

26. Les ajustements sont faits manuellement.

27. Les groupes sont validés.

28. Les familles sont notifiées.

## Parcours séance d’entraînement

29. La séance est générée depuis le planning.

30. L’entraîneur ouvre l’application mobile.

31. Il voit les nageurs attendus.

32. Il émarge les présences.

33. Il saisit les performances éventuelles.

34. Il ajoute un commentaire.

35. Il valide la séance.

36. Les statistiques sont mises à jour.

## Parcours analyse performance

37. Une performance est importée ou saisie.

38. Le système identifie le nageur.

39. Le temps est converti.

40. La grille applicable est sélectionnée.

41. Le niveau est calculé.

42. Les records personnels sont mis à jour.

43. Les graphiques sont actualisés.

44. Les alertes éventuelles sont générées.

# 9. Exigences UX/UI, sécurité et qualité

## Exigences UX/UI

- Navigation par modules

- Recherche globale

- Filtres puissants

- Tableaux triables

- Exports visibles

- Graphiques interactifs

- Fiches synthétiques

- Actions rapides

- Mode mobile simplifié

- Émargement en moins de deux minutes

## Exigences de performance

- Affichage fiche nageur : moins de 2 secondes

- Affichage groupe : moins de 2 secondes

- Sauvegarde présence : moins de 1 seconde

- Import compétition volumineux : traitement asynchrone

- Support de plusieurs centaines d’adhérents et plusieurs saisons
  historiques

## Tests prioritaires

- Tests unitaires

- Tests d’intégration

- Tests de droits

- Tests d’import

- Tests de calcul de qualification

- Tests de performance

- Tests mobile

- Tests de non-régression

- Vérification stricte sexe/âge/bassin/grille pour les qualifications

# 10. Roadmap recommandée et MVP

| **Phase**                          | **Contenu**                                                                                   |
|------------------------------------|-----------------------------------------------------------------------------------------------|
| Phase 1 - Socle administratif      | Utilisateurs, rôles, saisons, nageurs, inscriptions, documents, groupes simples.              |
| Phase 2 - Planning et émargement   | Groupes avancés, entraîneurs, créneaux, séances, émargement, assiduité.                       |
| Phase 3 - Performance compétition  | Import résultats, fiche performance, records, grilles, graphiques, tableaux de bord.          |
| Phase 4 - Performance entraînement | Tests internes, saisie mobile, séries, indicateurs, comparaison entraînement/compétition.     |
| Phase 5 - Analytics avancé         | Scoring nageur, constitution assistée des groupes, alertes, projections, bilans automatiques. |
| Phase 6 - Professionnalisation     | API, intégrations, paiement, communication, mobile complet, multi-sites, exports avancés.     |

## MVP recommandé

- Authentification

- Rôles utilisateurs

- Gestion des saisons

- Gestion des nageurs

- Gestion des groupes

- Affectation nageur/groupe

- Gestion des entraîneurs

- Planning simple

- Génération des séances

- Émargement mobile

- Import performances compétition

- Fiche nageur avec historique

- Dashboard entraîneur

- Dashboard direction

- Exports XLSX

## Hors MVP initial

- Paiement en ligne

- Communication SMS

- Scoring automatique avancé

- IA prédictive

- Application mobile native

- Multi-clubs

- Intégrations fédérales avancées

- Analyse biomécanique poussée

# 11. Prompt détaillé pour poursuivre le projet

## Prompt principal

> Tu es un architecte logiciel senior, expert en développement
> d’applications SaaS sportives, en gestion de club, en data analytics
> et en natation de compétition.
>
> Je veux concevoir une plateforme professionnelle complète de gestion
> d’un club de natation, dans la continuité d’un projet existant nommé
> CPN-Analytics.
>
> La plateforme doit couvrir l’ensemble des besoins d’un club de
> natation moderne : inscriptions, réinscriptions, gestion des
> adhérents, dossiers administratifs, documents, paiements, constitution
> des groupes, gestion des groupes, affectation des entraîneurs,
> planning des groupes, séances d’entraînement, émargement, suivi des
> absences, performances en compétition, performances à l’entraînement,
> mesures physiques, objectifs sportifs, tableaux de bord,
> communication, application mobile entraîneur, application mobile
> nageur/parent, sécurité, conformité, exports et intégrations.
>
> Je veux une architecture modulaire, robuste, évolutive et maintenable.
> La plateforme doit être pensée comme un ERP sportif spécialisé
> natation, utilisable par les administrateurs, le bureau du club, le
> directeur sportif, les entraîneurs, les nageurs et les parents.
>
> Propose une architecture complète avec : vision produit, rôles
> utilisateurs, modules fonctionnels, règles métier, modèle de données,
> parcours utilisateurs, écrans principaux, API nécessaires, contraintes
> techniques, exigences de sécurité, exigences RGPD, priorités de
> développement, roadmap MVP puis version avancée.
>
> Le module performance doit permettre de suivre les performances
> officielles en compétition, les temps par épreuve, les records
> personnels, les qualifications selon grilles, les performances à
> l’entraînement, les tests internes, les mesures physiques, la
> progression individuelle, la progression collective et les
> comparaisons par groupe, âge, sexe, catégorie et saison.
>
> Le moteur de qualification doit tenir compte du sexe, de l’âge, de la
> catégorie, de l’épreuve, du bassin, de la saison et de la grille
> applicable.
>
> Le module entraînement doit permettre aux entraîneurs de saisir
> rapidement depuis mobile les présences, absences, retards,
> performances chronométrées, commentaires, tests techniques, séries
> d’entraînement et indicateurs d’effort.
>
> Je veux une conception détaillée, avec une logique modulaire, une
> vision professionnelle et des recommandations concrètes pour commencer
> le développement.

## Prompt module par module

Pour chaque module, produire : objectif, utilisateurs concernés,
fonctionnalités principales, données manipulées, règles métier, écrans
nécessaires, API nécessaires, droits d’accès, cas particuliers, critères
d’acceptation, tests à prévoir et évolutions futures.

## Critères de réussite

- Le bureau peut gérer les inscriptions sans fichier Excel principal.

- Les entraîneurs peuvent émarger rapidement depuis mobile.

- Chaque nageur dispose d’une fiche complète.

- Les groupes sont exploitables et historisés.

- Les performances et qualifications sont fiables.

- Les dirigeants disposent d’indicateurs clairs.

- L’application est utilisable en bord de bassin.

- La plateforme peut évoluer sans refonte complète.

# Conclusion

La trajectoire recommandée est de construire d’abord un socle club
solide, puis de brancher progressivement les modules performance,
entraînement et analytics avancé. Cette approche limite les risques,
capitalise sur CPN-Analytics existant et prépare une évolution future
vers une plateforme SaaS multi-clubs.
