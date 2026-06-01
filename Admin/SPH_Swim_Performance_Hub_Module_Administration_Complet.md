# SPH - Swim Performance Hub - Module d'administration complet

## 1. Positionnement du module d'administration

Le module d'administration est le centre de contrôle de toute la plateforme SPH - Swim Performance Hub. Il ne doit pas être considéré comme un simple écran de réglages, mais comme une console de pilotage complète permettant de configurer, sécuriser, superviser, maintenir et faire évoluer l'application.

Dans le cahier des charges global, l'administration était présente à travers les rôles, les saisons, les paramètres club, les droits, la sécurité et les exports. Le présent document détaille l'architecture complète du module d'administration afin d'en faire un vrai socle applicatif professionnel.

Le module doit permettre à un club de natation de gérer son fonctionnement sans dépendre d'un développeur pour les opérations courantes : création de saison, paramétrage des groupes, gestion des droits, activation des modules, configuration des grilles, supervision des imports, contrôle des données et audit des actions sensibles.

## 2. Objectifs du module

### 2.1 Objectifs fonctionnels

- Centraliser toute la configuration de l'application.
- Gérer les utilisateurs, rôles, profils et permissions.
- Configurer les saisons sportives.
- Paramétrer les modules métiers.
- Administrer les groupes, catégories, niveaux, bassins et créneaux types.
- Gérer les référentiels sportifs : épreuves, nages, catégories, grilles de qualification.
- Superviser les imports, exports, traitements et synchronisations.
- Surveiller la qualité des données.
- Gérer les notifications, modèles de messages et communications système.
- Piloter les droits d'accès aux données sensibles.
- Auditer les actions importantes.
- Préparer l'évolution vers une architecture multi-clubs si nécessaire.

### 2.2 Objectifs techniques

- Isoler clairement les fonctions d'administration des modules métier.
- Fournir des API sécurisées pour chaque action administrative.
- Garantir la traçabilité des modifications critiques.
- Prévenir les erreurs de configuration pouvant impacter les données sportives.
- Permettre des exports de configuration.
- Permettre des sauvegardes et restaurations contrôlées.
- Préparer les migrations entre saisons.

### 2.3 Objectifs UX

- Fournir une console claire, lisible et structurée.
- Éviter les menus dispersés.
- Donner une vision immédiate de l'état du système.
- Prioriser les alertes importantes.
- Permettre une configuration guidée étape par étape.
- Rendre les actions sensibles explicites et confirmées.

## 3. Utilisateurs concernés

### 3.1 Super administrateur

Profil ayant tous les droits sur l'application.

Responsabilités :

- paramétrage global ;
- gestion des modules ;
- gestion des administrateurs ;
- sécurité ;
- audit ;
- sauvegardes ;
- configuration technique ;
- supervision globale.

### 3.2 Administrateur club

Profil principal côté club.

Responsabilités :

- gestion des saisons ;
- groupes ;
- inscriptions ;
- documents ;
- utilisateurs ;
- permissions métier ;
- modèles de communication ;
- exports.

### 3.3 Bureau du club

Profil administratif.

Responsabilités :

- validation des inscriptions ;
- documents ;
- paiements ;
- exports adhérents ;
- communications familles ;
- suivi des dossiers incomplets.

### 3.4 Directeur sportif

Profil sportif avec accès avancé au paramétrage métier.

Responsabilités :

- groupes ;
- catégories ;
- affectations ;
- grilles sportives ;
- compétitions ;
- objectifs ;
- règles d'analyse ;
- tableaux de bord sportifs.

### 3.5 Responsable technique ou développeur

Profil optionnel réservé à la maintenance.

Responsabilités :

- supervision des jobs ;
- logs techniques ;
- webhooks ;
- intégrations ;
- état des services ;
- API ;
- erreurs applicatives.

## 4. Principe d'architecture du module

Le module d'administration doit être organisé en domaines fonctionnels indépendants.

Architecture recommandée :

```text
Administration
|-- Tableau de bord admin
|-- Organisation du club
|-- Saisons sportives
|-- Utilisateurs et accès
|-- Rôles et permissions
|-- Paramétrage des modules
|-- Référentiels sportifs
|-- Groupes et affectations
|-- Inscriptions et dossiers
|-- Planning et équipements
|-- Performances et grilles
|-- Communication et notifications
|-- Paiements et documents
|-- Imports / exports
|-- Qualité des données
|-- Audit et journalisation
|-- Sécurité et conformité
|-- Intégrations externes
|-- Maintenance et supervision
`-- Sauvegarde / restauration
```

Chaque sous-module doit disposer :

- d'un écran de liste ;
- d'un écran de détail ;
- d'un formulaire de création / modification ;
- d'une recherche ;
- d'un système de filtres ;
- d'un historique des modifications si nécessaire ;
- de droits d'accès spécifiques ;
- d'API dédiées.

## 5. Navigation de la console d'administration

### 5.1 Accès général

L'administration doit être accessible depuis le menu principal uniquement pour les profils autorisés.

Accès recommandé :

```text
Menu principal > Administration
```

Le menu Administration doit ouvrir une interface dédiée, distincte des écrans d'exploitation quotidienne.

### 5.2 Organisation visuelle

L'interface doit être organisée en trois niveaux :

1. **Sidebar d'administration** : accès aux grandes familles.
2. **Zone de contenu principale** : configuration ou supervision.
3. **Panneau contextuel droit** : aide, statut, risques, actions rapides.

### 5.3 Groupes de menus recommandés

```text
Administration
|-- Vue d'ensemble
|-- Club
|   |-- Identité du club
|   |-- Sites et bassins
|   |-- Lignes d'eau
|   `-- Paramètres généraux
|-- Saisons
|   |-- Saisons sportives
|   |-- Périodes
|   |-- Vacances
|   `-- Duplication saison
|-- Accès
|   |-- Utilisateurs
|   |-- Rôles
|   |-- Permissions
|   |-- Invitations
|   `-- Sessions actives
|-- Sportif
|   |-- Groupes
|   |-- Catégories
|   |-- Niveaux
|   |-- Épreuves
|   |-- Grilles de qualification
|   `-- Objectifs
|-- Inscriptions
|   |-- Formulaires
|   |-- Documents requis
|   |-- Statuts de dossier
|   `-- Règles de validation
|-- Planning
|   |-- Créneaux types
|   |-- Bassins
|   |-- Indisponibilités
|   `-- Règles de conflit
|-- Communication
|   |-- Modèles de messages
|   |-- Notifications
|   |-- Canaux
|   `-- Bannières applicatives
|-- Data
|   |-- Imports
|   |-- Exports
|   |-- Qualité des données
|   |-- Réconciliation
|   `-- Archives
|-- Sécurité
|   |-- Audit
|   |-- RGPD
|   |-- Données sensibles
|   `-- Politique de conservation
`-- Technique
    |-- Jobs
    |-- Logs
    |-- Intégrations
    |-- API
    `-- Sauvegardes
```

## 6. Tableau de bord administrateur

### 6.1 Objectif

Donner une vue immédiate de l'état de l'application et des actions prioritaires.

### 6.2 Cartes de synthèse

Le dashboard admin doit afficher :

- nombre d'adhérents actifs ;
- inscriptions en attente ;
- dossiers incomplets ;
- paiements en attente ;
- groupes actifs ;
- entraîneurs actifs ;
- séances non émargées ;
- imports en erreur ;
- alertes de sécurité ;
- documents expirés ;
- conflits planning ;
- stockage utilisé ;
- dernière sauvegarde ;
- jobs en échec.

### 6.3 Alertes critiques

Les alertes doivent être classées par niveau :

- critique ;
- important ;
- information ;
- réussite.

Exemples d'alertes critiques :

- aucune sauvegarde depuis plus de 24 heures ;
- compte administrateur sans MFA si cette option est activée ;
- import compétition en erreur ;
- grille de qualification incomplète ;
- conflit de planning non résolu ;
- séance non émargée depuis plus de 72 heures ;
- document légal expiré sur plusieurs dossiers.

### 6.4 Actions rapides

Actions directement accessibles :

- créer une saison ;
- importer des nageurs ;
- créer un groupe ;
- inviter un utilisateur ;
- lancer un export ;
- ouvrir les dossiers incomplets ;
- vérifier les imports ;
- consulter l'audit.

## 7. Administration de l'identité du club

### 7.1 Objectif

Configurer les informations institutionnelles du club.

### 7.2 Données à gérer

- nom officiel du club ;
- nom court ;
- sigle ;
- numéro d'affiliation ;
- adresse ;
- téléphone ;
- email principal ;
- site web ;
- réseaux sociaux ;
- logo principal ;
- logo secondaire ;
- favicon ;
- couleurs officielles ;
- mentions légales ;
- politique de confidentialité ;
- règlement intérieur.

### 7.3 Logos et identité visuelle

Le module doit permettre de gérer :

- logo clair ;
- logo sombre ;
- logo carré ;
- logo horizontal ;
- icône application mobile ;
- bannière club ;
- bannière compétition ;
- bannière inscription ;
- image de fond login.

Formats recommandés :

- SVG pour les logos principaux ;
- PNG transparent pour les icônes ;
- WebP pour les bannières ;
- taille maximale contrôlée ;
- prévisualisation avant validation.

### 7.4 Règles métier

- Un logo principal doit toujours être défini.
- Les couleurs doivent être conformes aux critères de contraste.
- Une modification d'identité doit être historisée.
- Les images doivent être optimisées automatiquement.

## 8. Administration des saisons sportives

### 8.1 Objectif

Piloter l'organisation annuelle du club.

### 8.2 Fonctionnalités

- création d'une saison ;
- duplication d'une saison précédente ;
- archivage ;
- activation / désactivation ;
- définition des dates ;
- définition des périodes ;
- gestion des vacances ;
- fermeture administrative ;
- verrouillage sportif ;
- migration des groupes ;
- réinscription automatique.

### 8.3 Statuts de saison

- brouillon ;
- préparation ;
- ouverte aux inscriptions ;
- active ;
- clôturée ;
- archivée.

### 8.4 Assistant de création de saison

Un assistant guidé doit proposer :

1. choix du nom de saison ;
2. dates de début et de fin ;
3. duplication des groupes ;
4. duplication des tarifs ;
5. duplication des documents requis ;
6. duplication des créneaux ;
7. choix des entraîneurs ;
8. ouverture ou non des inscriptions.

### 8.5 Règles métier

- Une seule saison peut être active par défaut.
- Les données historiques ne doivent jamais être écrasées.
- Une saison clôturée ne peut plus être modifiée sans droit spécial.
- La duplication doit créer de nouvelles entités saisonnières et non réutiliser les anciennes relations.

## 9. Administration des utilisateurs

### 9.1 Objectif

Gérer tous les comptes ayant accès à l'application.

### 9.2 Fonctionnalités

- liste des utilisateurs ;
- création manuelle ;
- invitation par email ;
- activation / désactivation ;
- réinitialisation mot de passe ;
- assignation de rôles ;
- rattachement à un nageur ;
- rattachement à un ou plusieurs groupes ;
- consultation des dernières connexions ;
- verrouillage temporaire ;
- suppression ou anonymisation ;
- export utilisateurs.

### 9.3 Fiche utilisateur

La fiche doit contenir :

- identité ;
- email ;
- téléphone ;
- rôle principal ;
- rôles secondaires ;
- statut du compte ;
- groupes accessibles ;
- enfants associés ;
- dernières connexions ;
- sessions actives ;
- historique des changements ;
- préférences de notification.

### 9.4 Statuts utilisateur

- invité ;
- actif ;
- inactif ;
- suspendu ;
- verrouillé ;
- supprimé ;
- anonymisé.

### 9.5 Règles métier

- Un compte parent ne doit accéder qu'aux nageurs rattachés.
- Un entraîneur ne doit voir que les groupes autorisés.
- Un utilisateur suspendu ne doit plus pouvoir se connecter.
- Les comptes administrateurs doivent être protégés par des confirmations renforcées.

## 10. Administration des rôles et permissions

### 10.1 Objectif

Créer un système de droits fin, lisible et sécurisé.

### 10.2 Rôles standards

- Super administrateur ;
- Administrateur club ;
- Bureau ;
- Directeur sportif ;
- Entraîneur principal ;
- Entraîneur assistant ;
- Responsable de groupe ;
- Parent ;
- Nageur ;
- Lecteur ;
- Support technique.

### 10.3 Permissions types

Les permissions doivent être organisées par domaine :

```text
users.read
users.create
users.update
users.delete
roles.manage
seasons.manage
swimmers.read
swimmers.create
swimmers.update
groups.manage
sessions.manage
attendance.write
performances.read
performances.write
physical_data.read
physical_data.write
qualifications.manage
payments.read
payments.manage
documents.validate
exports.run
audit.read
settings.manage
```

### 10.4 Matrice de permissions

L'interface doit proposer une matrice avec :

- lignes = modules ;
- colonnes = actions ;
- cases = autorisé / refusé / hérité ;
- filtre par rôle ;
- simulation d'accès ;
- aperçu des impacts.

### 10.5 Permissions contextuelles

Le modèle doit gérer les permissions contextuelles :

- par saison ;
- par groupe ;
- par nageur ;
- par type de donnée ;
- par niveau de sensibilité ;
- par module activé.

### 10.6 Règles métier

- Les permissions critiques doivent nécessiter une confirmation.
- Une modification de rôle doit être auditée.
- Les permissions sensibles doivent être refusées par défaut.
- Le principe du moindre privilège doit être appliqué.

## 11. Administration des modules applicatifs

### 11.1 Objectif

Permettre d'activer, désactiver et configurer les modules de l'application.

### 11.2 Modules administrables

- inscriptions ;
- dossiers administratifs ;
- groupes ;
- planning ;
- émargement ;
- performances compétition ;
- performances entraînement ;
- mesures physiques ;
- objectifs ;
- compétitions ;
- communication ;
- paiements ;
- exports ;
- notifications ;
- application mobile ;
- API externe.

### 11.3 États de module

- activé ;
- désactivé ;
- masqué ;
- lecture seule ;
- bêta ;
- réservé administrateurs.

### 11.4 Règles métier

- Un module désactivé ne doit plus apparaître dans la navigation standard.
- Les données du module ne doivent pas être supprimées lors d'une désactivation.
- Certains modules peuvent dépendre d'autres modules.
- Exemple : le module émargement dépend du module séances.

## 12. Administration des référentiels sportifs

### 12.1 Objectif

Centraliser toutes les données de référence sportives.

### 12.2 Référentiels à gérer

- nages ;
- distances ;
- épreuves ;
- types de bassin ;
- catégories d'âge ;
- sexes ;
- niveaux sportifs ;
- types de compétitions ;
- types de tests ;
- types de séances ;
- unités de mesure ;
- statuts de performance ;
- règles de qualification.

### 12.3 Épreuves

Chaque épreuve doit contenir :

- distance ;
- nage ;
- bassin ;
- sexe applicable ;
- catégorie applicable ;
- statut actif ;
- code interne ;
- correspondance import.

### 12.4 Catégories

Les catégories doivent être calculées selon :

- année de naissance ;
- saison ;
- sexe si nécessaire ;
- règles fédérales configurables.

### 12.5 Règles métier

- Les référentiels utilisés par des performances historiques ne doivent pas être supprimés physiquement.
- Une désactivation doit être préférée à une suppression.
- Toute modification d'une règle de catégorie doit déclencher une alerte de recalcul potentiel.

## 13. Administration des grilles de qualification

### 13.1 Objectif

Gérer les grilles qui servent au calcul des niveaux de qualification.

### 13.2 Fonctionnalités

- création d'une grille ;
- import XLSX / CSV ;
- versioning ;
- activation par saison ;
- mapping des colonnes ;
- prévisualisation ;
- validation des données ;
- simulation sur nageur ;
- comparaison de versions ;
- recalcul des qualifications ;
- export de grille.

### 13.3 Données d'une ligne de grille

- saison ;
- sexe ;
- âge ;
- catégorie ;
- épreuve ;
- bassin ;
- niveau ;
- temps seuil ;
- ordre de priorité ;
- source ;
- date d'import.

### 13.4 Contrôles obligatoires

Le système doit vérifier :

- présence du sexe ;
- présence de l'âge ou catégorie ;
- correspondance épreuve ;
- format temps valide ;
- absence de doublons ;
- cohérence des seuils ;
- cohérence bassin 25 m / 50 m ;
- compatibilité saison.

### 13.5 Simulation

L'administrateur doit pouvoir tester :

- un nageur ;
- une épreuve ;
- un temps ;
- une date ;
- un sexe ;
- un âge ;
- une saison.

Le système doit retourner :

- niveau obtenu ;
- seuil battu ;
- écart au seuil ;
- grille utilisée ;
- règle appliquée.

## 14. Administration des groupes

### 14.1 Objectif

Permettre à l'administrateur et au directeur sportif de structurer les groupes.

### 14.2 Fonctionnalités

- création de groupe ;
- capacité maximale ;
- type de groupe ;
- niveau cible ;
- âge cible ;
- sexe si groupe spécifique ;
- saison ;
- entraîneurs associés ;
- créneaux associés ;
- règles d'accès ;
- historique ;
- duplication.

### 14.3 Paramètres d'un groupe

- nom ;
- code court ;
- couleur ;
- description ;
- capacité ;
- statut ;
- ordre d'affichage ;
- visibilité parents ;
- visibilité nageurs ;
- niveau requis ;
- objectifs du groupe.

### 14.4 Règles métier

- Un groupe actif doit être rattaché à une saison.
- Un groupe ne peut pas dépasser sa capacité sans autorisation.
- Les changements d'affectation doivent être historisés.
- Une suppression est interdite si des séances ou présences existent.

## 15. Administration des inscriptions

### 15.1 Objectif

Configurer les règles et formulaires d'inscription.

### 15.2 Fonctionnalités

- configuration du formulaire ;
- champs obligatoires ;
- sections personnalisées ;
- documents demandés ;
- consentements ;
- règlements ;
- messages de confirmation ;
- statuts de workflow ;
- règles de validation ;
- ouverture / fermeture par saison ;
- quotas par groupe ou activité.

### 15.3 Workflow d'inscription

Statuts recommandés :

```text
Brouillon > Soumis > À compléter > En validation > Validé > Affecté à un groupe > Archivé
```

Statuts alternatifs :

- refusé ;
- annulé ;
- doublon ;
- en attente paiement ;
- en attente document.

### 15.4 Règles métier

- Un dossier incomplet ne doit pas être validé sans dérogation.
- Une dérogation doit être commentée.
- Les documents obligatoires dépendent de l'âge, du type d'activité et de la saison.
- Les consentements doivent être historisés.

## 16. Administration des documents

### 16.1 Objectif

Définir les documents requis, leurs règles et leur cycle de vie.

### 16.2 Documents types

- certificat médical ;
- questionnaire santé ;
- autorisation parentale ;
- droit à l'image ;
- règlement intérieur signé ;
- justificatif de paiement ;
- pièce d'identité ;
- licence fédérale ;
- attestation d'assurance.

### 16.3 Paramètres d'un document requis

- nom ;
- description ;
- obligatoire ou facultatif ;
- population concernée ;
- âge concerné ;
- saison concernée ;
- date d'expiration ;
- validation manuelle ou automatique ;
- format accepté ;
- taille maximale ;
- modèle téléchargeable.

### 16.4 Règles métier

- Les documents sensibles doivent être protégés.
- Les suppressions doivent être tracées.
- L'expiration doit générer une alerte.
- Un document validé ne doit pas être modifiable sans repasser en validation.

## 17. Administration du planning

### 17.1 Objectif

Configurer les règles de planification et les ressources.

### 17.2 Ressources à gérer

- sites ;
- bassins ;
- lignes d'eau ;
- salles de préparation physique ;
- entraîneurs ;
- créneaux types ;
- périodes d'indisponibilité ;
- jours fériés ;
- vacances ;
- événements bloquants.

### 17.3 Règles de conflit

Le système doit détecter :

- entraîneur déjà occupé ;
- groupe déjà planifié ;
- bassin indisponible ;
- ligne d'eau déjà réservée ;
- chevauchement horaire ;
- dépassement capacité ;
- créneau hors période active.

### 17.4 Options d'administration

- bloquer la création en cas de conflit ;
- autoriser avec alerte ;
- exiger une justification ;
- notifier les responsables.

## 18. Administration de l'émargement

### 18.1 Objectif

Configurer le fonctionnement des présences.

### 18.2 Paramètres

- statuts de présence ;
- délai de modification ;
- obligation de validation séance ;
- droits de correction ;
- justification d'absence ;
- émargement par QR code optionnel ;
- émargement hors ligne mobile ;
- synchronisation différée ;
- alertes absences répétées.

### 18.3 Statuts recommandés

- présent ;
- absent excusé ;
- absent non excusé ;
- retard ;
- blessé ;
- dispensé ;
- autre.

### 18.4 Règles métier

- Une séance validée ne doit plus être modifiable sans droit spécial.
- Une correction après validation doit être auditée.
- Les absences répétées doivent générer une alerte.
- Les statistiques doivent être recalculées après modification.

## 19. Administration des performances

### 19.1 Objectif

Garantir la fiabilité des performances compétition et entraînement.

### 19.2 Paramètres compétition

- sources d'import ;
- formats de fichier ;
- règles de mapping ;
- stratégie de dédoublonnage ;
- règles de conversion temps ;
- règles de record personnel ;
- règles de qualification ;
- validation manuelle ou automatique.

### 19.3 Paramètres entraînement

- types de tests ;
- unités ;
- séries types ;
- seuils d'alerte ;
- indicateurs calculés ;
- droits de saisie ;
- modification après validation ;
- visibilité parent / nageur.

### 19.4 Règles métier

- Toute performance doit être rattachée à un nageur identifié.
- Les temps doivent être stockés en centièmes ou millisecondes selon le standard choisi.
- Les performances officielles doivent être distinguées des performances d'entraînement.
- Les modifications doivent être historisées.

## 20. Administration des mesures physiques

### 20.1 Objectif

Configurer les données physiques suivies par le club.

### 20.2 Mesures possibles

- poids ;
- taille ;
- envergure ;
- fréquence cardiaque ;
- mobilité ;
- souplesse ;
- détente ;
- gainage ;
- VMA ;
- test endurance ;
- blessure déclarée ;
- restriction d'entraînement.

### 20.3 Paramètres de confidentialité

Chaque type de mesure doit préciser :

- qui peut lire ;
- qui peut écrire ;
- qui peut modifier ;
- visibilité parent ;
- visibilité nageur ;
- niveau de sensibilité ;
- durée de conservation ;
- export autorisé ou non.

### 20.4 Règles métier

- Les données physiques sont sensibles.
- L'accès doit être limité par défaut.
- Les exports doivent être contrôlés.
- Les suppressions ou anonymisations doivent être possibles selon politique RGPD.

## 21. Administration de la communication

### 21.1 Objectif

Configurer tous les messages envoyés par le club.

### 21.2 Modèles de messages

- inscription reçue ;
- dossier incomplet ;
- inscription validée ;
- groupe affecté ;
- rappel document ;
- rappel paiement ;
- annulation séance ;
- convocation compétition ;
- changement planning ;
- alerte absence ;
- message général.

### 21.3 Canaux

- email ;
- notification mobile ;
- notification web ;
- SMS optionnel ;
- bannière applicative ;
- message interne.

### 21.4 Bannières administrables

Types de bannières :

- bannière d'accueil ;
- bannière inscription ;
- bannière maintenance ;
- bannière urgence ;
- bannière compétition ;
- bannière information club ;
- bannière application mobile.

Paramètres :

- titre ;
- message ;
- niveau ;
- image ;
- couleur ;
- dates de diffusion ;
- public cible ;
- bouton d'action ;
- lien ;
- priorité.

## 22. Administration des paiements

### 22.1 Objectif

Paramétrer le suivi financier des adhésions.

### 22.2 Fonctionnalités

- tarifs par saison ;
- tarifs par groupe ;
- remises famille ;
- exonérations ;
- échéanciers ;
- modes de paiement ;
- statuts ;
- relances ;
- exports comptables ;
- reçus ;
- justificatifs.

### 22.3 Règles métier

- Une remise doit être justifiée.
- Une exonération doit être réservée aux profils autorisés.
- Les paiements ne doivent pas être supprimés physiquement.
- Les modifications doivent être tracées.

## 23. Administration des imports et exports

### 23.1 Objectif

Piloter tous les flux de données entrants et sortants.

### 23.2 Imports possibles

- nageurs ;
- groupes ;
- inscriptions ;
- performances compétition ;
- grilles de qualification ;
- plannings ;
- paiements ;
- documents ;
- référentiels.

### 23.3 Exports possibles

- adhérents ;
- groupes ;
- présences ;
- absences ;
- paiements ;
- documents manquants ;
- performances ;
- qualifications ;
- statistiques ;
- logs d'audit ;
- configuration.

### 23.4 Suivi des imports

Chaque import doit afficher :

- fichier source ;
- utilisateur ;
- date ;
- statut ;
- nombre de lignes ;
- lignes créées ;
- lignes modifiées ;
- lignes ignorées ;
- erreurs ;
- rapport téléchargeable ;
- possibilité d'annulation si supportée.

### 23.5 Règles métier

- Aucun import massif ne doit modifier les données sans prévisualisation.
- Un import doit pouvoir être simulé.
- Les erreurs doivent être explicites.
- Les imports critiques doivent être réversibles ou historisés.

## 24. Administration de la qualité des données

### 24.1 Objectif

Détecter les incohérences qui dégradent la fiabilité de l'application.

### 24.2 Contrôles recommandés

- nageurs sans groupe ;
- nageurs sans responsable légal ;
- doublons potentiels ;
- performances sans sexe ;
- performances sans âge calculable ;
- performances sans épreuve reconnue ;
- documents expirés ;
- paiements incohérents ;
- séances sans entraîneur ;
- groupes sans créneau ;
- créneaux en conflit ;
- grilles de qualification incomplètes ;
- catégories non calculables.

### 24.3 Score qualité

Le dashboard admin peut afficher un score de qualité des données :

```text
Score qualité = données valides / données contrôlées x 100
```

Niveaux :

- 95 % à 100 % : excellent ;
- 85 % à 94 % : correct ;
- 70 % à 84 % : à surveiller ;
- moins de 70 % : critique.

## 25. Administration de l'audit

### 25.1 Objectif

Tracer toutes les actions sensibles.

### 25.2 Actions à auditer

- connexion administrateur ;
- échec de connexion ;
- changement de rôle ;
- modification de permission ;
- validation inscription ;
- modification de groupe ;
- suppression document ;
- modification performance ;
- import massif ;
- export sensible ;
- modification paiement ;
- modification grille ;
- changement configuration ;
- anonymisation ;
- restauration de sauvegarde.

### 25.3 Données d'audit

- utilisateur ;
- action ;
- module ;
- objet impacté ;
- ancienne valeur ;
- nouvelle valeur ;
- date ;
- adresse IP ;
- user agent ;
- résultat ;
- commentaire.

### 25.4 Règles métier

- Les logs d'audit ne doivent pas être modifiables depuis l'interface.
- La consultation des logs doit elle-même être auditée si elle porte sur des données sensibles.
- Les exports d'audit doivent être réservés aux administrateurs habilités.

## 26. Administration sécurité et conformité

### 26.1 Objectif

Protéger les comptes, les mineurs, les données sportives et les données sensibles.

### 26.2 Paramètres sécurité

- politique de mot de passe ;
- durée de session ;
- verrouillage après échecs ;
- double authentification optionnelle ;
- restriction IP optionnelle ;
- expiration invitation ;
- révocation sessions ;
- niveau de sécurité par rôle.

### 26.3 RGPD

Fonctionnalités nécessaires :

- export des données personnelles ;
- anonymisation ;
- suppression logique ;
- consentements ;
- durée de conservation ;
- registre des traitements ;
- politique de confidentialité ;
- gestion des mineurs ;
- journalisation des accès aux données sensibles.

### 26.4 Données sensibles

Catégories :

- données médicales ;
- documents administratifs ;
- mesures physiques ;
- données de mineurs ;
- coordonnées parents ;
- paiements ;
- commentaires internes.

### 26.5 Règles métier

- Les données sensibles sont masquées par défaut.
- L'accès doit être explicitement accordé.
- Les exports sensibles nécessitent une permission dédiée.
- Les durées de conservation doivent être paramétrables.

## 27. Administration des intégrations

### 27.1 Objectif

Configurer les connexions avec des systèmes externes.

### 27.2 Intégrations possibles

- FFN ou exports fédéraux ;
- Google Calendar ;
- Outlook Calendar ;
- service email ;
- service SMS ;
- paiement en ligne ;
- stockage cloud ;
- application mobile SPH ;
- outils BI ;
- webhook externe.

### 27.3 Paramètres par intégration

- statut ;
- clé API ;
- URL ;
- dernière synchronisation ;
- fréquence ;
- logs ;
- erreurs ;
- test de connexion ;
- activation / désactivation.

### 27.4 Règles métier

- Les secrets ne doivent jamais être affichés en clair.
- Les clés API doivent être chiffrées.
- Les tests de connexion doivent être disponibles.
- Les erreurs de synchronisation doivent être visibles dans le dashboard admin.

## 28. Administration technique et supervision

### 28.1 Objectif

Donner une visibilité opérationnelle sur l'état technique de la plateforme.

### 28.2 Éléments à superviser

- état API ;
- état base de données ;
- état stockage ;
- jobs planifiés ;
- files de traitement ;
- imports en cours ;
- exports en cours ;
- emails en attente ;
- notifications en attente ;
- erreurs applicatives ;
- temps de réponse ;
- espace disque ;
- version déployée.

### 28.3 Jobs techniques

Exemples :

- génération des séances ;
- recalcul des statistiques ;
- recalcul des qualifications ;
- envoi des notifications ;
- relances documents ;
- relances paiements ;
- sauvegarde ;
- nettoyage fichiers temporaires ;
- archivage saison ;
- export programmé.

### 28.4 Actions admin

- relancer un job ;
- annuler un job ;
- consulter les erreurs ;
- télécharger un rapport ;
- mettre en pause une file ;
- purger un cache ;
- vérifier l'état système.

## 29. Sauvegarde, restauration et archivage

### 29.1 Objectif

Sécuriser les données du club et permettre une restauration contrôlée.

### 29.2 Fonctionnalités

- sauvegarde automatique ;
- sauvegarde manuelle ;
- sauvegarde base ;
- sauvegarde documents ;
- historique des sauvegardes ;
- test de restauration ;
- restauration partielle ;
- archivage saison ;
- export de configuration.

### 29.3 Règles métier

- Une restauration doit nécessiter une confirmation renforcée.
- Une restauration doit être auditée.
- Les sauvegardes doivent être chiffrées.
- Les sauvegardes doivent être testées périodiquement.

## 30. API du module d'administration

### 30.1 Principes

Les API admin doivent être séparées des API métier standards.

Préfixe recommandé :

```text
/api/admin
```

### 30.2 Endpoints principaux

```text
GET    /api/admin/dashboard
GET    /api/admin/settings
PATCH  /api/admin/settings

GET    /api/admin/users
POST   /api/admin/users
GET    /api/admin/users/{id}
PATCH  /api/admin/users/{id}
DELETE /api/admin/users/{id}
POST   /api/admin/users/{id}/suspend
POST   /api/admin/users/{id}/reset-password

GET    /api/admin/roles
POST   /api/admin/roles
PATCH  /api/admin/roles/{id}
DELETE /api/admin/roles/{id}
GET    /api/admin/permissions
PATCH  /api/admin/roles/{id}/permissions

GET    /api/admin/seasons
POST   /api/admin/seasons
PATCH  /api/admin/seasons/{id}
POST   /api/admin/seasons/{id}/duplicate
POST   /api/admin/seasons/{id}/close
POST   /api/admin/seasons/{id}/archive

GET    /api/admin/modules
PATCH  /api/admin/modules/{moduleKey}

GET    /api/admin/reference-data
POST   /api/admin/reference-data/{type}
PATCH  /api/admin/reference-data/{type}/{id}

GET    /api/admin/qualification-grids
POST   /api/admin/qualification-grids/import
POST   /api/admin/qualification-grids/{id}/simulate
POST   /api/admin/qualification-grids/{id}/activate

GET    /api/admin/imports
POST   /api/admin/imports/simulate
POST   /api/admin/imports/execute
GET    /api/admin/imports/{id}/report

GET    /api/admin/exports
POST   /api/admin/exports
GET    /api/admin/exports/{id}/download

GET    /api/admin/data-quality
POST   /api/admin/data-quality/run-checks

GET    /api/admin/audit-logs
GET    /api/admin/security/events
PATCH  /api/admin/security/policy

GET    /api/admin/jobs
POST   /api/admin/jobs/{id}/retry
POST   /api/admin/jobs/{id}/cancel

GET    /api/admin/backups
POST   /api/admin/backups
POST   /api/admin/backups/{id}/restore
```

### 30.3 Exigences API

- authentification obligatoire ;
- contrôle RBAC sur chaque endpoint ;
- validation forte des entrées ;
- pagination ;
- filtres ;
- tri ;
- audit automatique des actions sensibles ;
- réponses d'erreur explicites ;
- documentation OpenAPI.

## 31. Modèle de données recommandé

### 31.1 Tables principales

```text
admin_settings
club_profile
club_assets
seasons
season_periods
users
roles
permissions
role_permissions
user_roles
user_scopes
modules
module_settings
reference_data
qualification_grids
qualification_grid_rows
import_jobs
export_jobs
data_quality_checks
data_quality_results
audit_logs
security_events
notification_templates
system_banners
integration_settings
background_jobs
backup_records
```

### 31.2 Tables de permissions contextuelles

```text
user_group_access
user_season_access
user_swimmer_access
role_scope_rules
sensitive_data_access_rules
```

### 31.3 Tables d'historique

```text
settings_history
role_permission_history
season_history
group_assignment_history
qualification_grid_history
user_status_history
```

## 32. Écrans détaillés à prévoir

### 32.1 Vue d'ensemble admin

Contenu :

- indicateurs système ;
- alertes ;
- actions rapides ;
- état des modules ;
- activité récente ;
- qualité des données.

### 32.2 Identité club

Contenu :

- informations générales ;
- logo ;
- couleurs ;
- bannières ;
- documents légaux ;
- prévisualisation.

### 32.3 Utilisateurs

Contenu :

- table filtrable ;
- statut ;
- rôle ;
- dernière connexion ;
- actions rapides ;
- fiche détaillée.

### 32.4 Rôles et permissions

Contenu :

- liste des rôles ;
- matrice de permissions ;
- permissions contextuelles ;
- simulation d'accès ;
- historique.

### 32.5 Saisons

Contenu :

- liste des saisons ;
- assistant création ;
- duplication ;
- clôture ;
- archivage ;
- périodes.

### 32.6 Modules

Contenu :

- cartes modules ;
- état ;
- dépendances ;
- configuration ;
- visibilité navigation.

### 32.7 Référentiels sportifs

Contenu :

- tabs par référentiel ;
- CRUD ;
- statut actif / inactif ;
- mapping import ;
- validation.

### 32.8 Grilles de qualification

Contenu :

- versions ;
- import ;
- validation ;
- simulation ;
- activation ;
- recalcul.

### 32.9 Imports / exports

Contenu :

- historique ;
- statut ;
- rapports ;
- erreurs ;
- simulation ;
- relance.

### 32.10 Qualité des données

Contenu :

- score global ;
- contrôles ;
- anomalies ;
- correction guidée ;
- export.

### 32.11 Audit

Contenu :

- logs ;
- filtres ;
- recherche ;
- détails ;
- export restreint.

### 32.12 Sécurité

Contenu :

- politique mot de passe ;
- sessions ;
- événements ;
- accès sensibles ;
- RGPD ;
- conservation.

### 32.13 Technique

Contenu :

- jobs ;
- logs techniques ;
- intégrations ;
- API ;
- sauvegardes ;
- version applicative.

## 33. Règles UX spécifiques

### 33.1 Principes visuels

- Interface sobre, claire et premium.
- Sidebar fixe ou rétractable.
- Recherche globale dans l'administration.
- Breadcrumb systématique.
- Badges de statut visibles.
- Actions critiques en zone séparée.
- Confirmation renforcée pour les actions irréversibles.

### 33.2 Actions sensibles

Pour les actions suivantes, afficher une modale de confirmation :

- suppression ;
- suspension utilisateur ;
- changement de rôle admin ;
- activation grille ;
- recalcul massif ;
- clôture saison ;
- restauration sauvegarde ;
- export sensible ;
- modification politique sécurité.

### 33.3 Design des statuts

Utiliser des badges :

- actif ;
- inactif ;
- brouillon ;
- archivé ;
- erreur ;
- attention ;
- validé ;
- incomplet.

### 33.4 Mode mobile

L'administration complète doit rester disponible sur tablette et partiellement sur mobile.

Sur mobile, prioriser :

- dashboard ;
- alertes ;
- utilisateurs ;
- inscriptions ;
- imports ;
- audit simplifié ;
- actions urgentes.

Les opérations complexes comme la matrice de permissions ou l'import de grilles doivent être optimisées pour desktop/tablette.

## 34. Sécurité par design

### 34.1 Principes

- accès admin séparé ;
- permissions strictes ;
- audit systématique ;
- confirmation des actions critiques ;
- masquage des données sensibles ;
- contrôle des exports ;
- limitation des sessions ;
- protection des secrets.

### 34.2 Exemples de règles

- Un administrateur club ne peut pas modifier le super administrateur.
- Un entraîneur ne peut pas devenir administrateur sans action d'un profil supérieur.
- Un export contenant des données sensibles doit être journalisé.
- Une grille activée ne doit pas être modifiée directement : il faut créer une nouvelle version.
- Une saison archivée est en lecture seule.

## 35. Backlog de développement recommandé

### Phase A - Socle administration

- dashboard admin ;
- gestion identité club ;
- gestion utilisateurs ;
- rôles standards ;
- permissions simples ;
- saisons ;
- paramètres généraux.

### Phase B - Administration métier

- groupes ;
- référentiels sportifs ;
- documents requis ;
- formulaires inscription ;
- planning ressources ;
- statuts émargement.

### Phase C - Administration performance

- grilles de qualification ;
- imports compétition ;
- règles de calcul ;
- mesures physiques ;
- tests entraînement ;
- simulation qualification.

### Phase D - Administration data et supervision

- imports / exports ;
- qualité des données ;
- audit ;
- jobs ;
- logs ;
- sauvegardes.

### Phase E - Sécurité avancée

- MFA ;
- politique session ;
- RGPD ;
- anonymisation ;
- conservation ;
- secrets ;
- intégrations.

## 36. Critères d'acceptation globaux

Le module d'administration est considéré comme prêt si :

- un administrateur peut configurer une saison complète ;
- un administrateur peut créer et gérer les utilisateurs ;
- les rôles et permissions sont appliqués correctement ;
- les modules peuvent être activés ou masqués ;
- les référentiels sportifs sont modifiables proprement ;
- les grilles de qualification sont importables et testables ;
- les documents requis sont configurables ;
- les imports sont simulables avant exécution ;
- les exports sensibles sont contrôlés ;
- les actions critiques sont auditées ;
- les données sensibles sont protégées ;
- les sauvegardes sont visibles ;
- les erreurs techniques sont consultables ;
- l'interface est claire, responsive et sécurisée.

## 37. Prompt Claude Code - Module administration

Tu es un architecte logiciel senior et développeur full-stack expert en applications SaaS métier, RBAC, sécurité, administration système et interfaces professionnelles.

Je veux développer le module d'administration complet de SPH - Swim Performance Hub, une plateforme de gestion professionnelle d'un club de natation.

Le module d'administration doit permettre de gérer toute la configuration de l'application : identité du club, saisons, utilisateurs, rôles, permissions, modules, référentiels sportifs, groupes, inscriptions, documents, planning, émargement, performances, grilles de qualification, imports, exports, qualité des données, audit, sécurité, intégrations, jobs et sauvegardes.

Contraintes fortes :

- architecture modulaire ;
- backend API sécurisé ;
- frontend professionnel responsive ;
- permissions fines par rôle, groupe, saison et type de donnée ;
- audit des actions sensibles ;
- protection des données sensibles ;
- séparation claire entre administration et modules métier ;
- préparation à une évolution multi-clubs ;
- interface moderne, claire et très intuitive.

Produis :

1. la structure des routes backend ;
2. les modèles de données ;
3. les services métier ;
4. les endpoints API ;
5. les écrans frontend ;
6. les composants UI ;
7. les règles RBAC ;
8. le système d'audit ;
9. les tests unitaires et d'intégration ;
10. les critères d'acceptation ;
11. les migrations de base ;
12. un plan de développement incrémental.

Commence par implémenter un MVP administration contenant :

- dashboard admin ;
- identité club ;
- utilisateurs ;
- rôles ;
- permissions simples ;
- saisons ;
- modules ;
- audit minimal ;
- paramètres généraux.

Puis prépare les extensions :

- grilles de qualification ;
- imports / exports ;
- qualité des données ;
- sécurité avancée ;
- intégrations ;
- sauvegardes.

Le code doit être propre, typé, testé, documenté et prêt pour une évolution progressive.

## 38. Prompt Claude Code - Découpage par fichiers

Crée une architecture de fichiers claire pour le module administration.

Exemple attendu :

```text
backend/
  app/
    admin/
      routes/
        admin_dashboard.py
        admin_users.py
        admin_roles.py
        admin_permissions.py
        admin_seasons.py
        admin_modules.py
        admin_reference_data.py
        admin_qualification_grids.py
        admin_imports.py
        admin_exports.py
        admin_audit.py
        admin_security.py
        admin_jobs.py
        admin_backups.py
      services/
        admin_dashboard_service.py
        user_admin_service.py
        rbac_service.py
        permission_service.py
        season_admin_service.py
        module_settings_service.py
        audit_service.py
        data_quality_service.py
      models/
        admin_settings.py
        role.py
        permission.py
        audit_log.py
        module_setting.py
        import_job.py
        export_job.py
      schemas/
        admin_dashboard_schema.py
        user_admin_schema.py
        role_schema.py
        permission_schema.py
        audit_schema.py
      tests/
        test_admin_users.py
        test_admin_roles.py
        test_admin_permissions.py
        test_admin_audit.py

frontend/
  src/
    features/
      admin/
        pages/
          AdminDashboardPage.tsx
          AdminClubIdentityPage.tsx
          AdminUsersPage.tsx
          AdminRolesPage.tsx
          AdminSeasonsPage.tsx
          AdminModulesPage.tsx
          AdminReferenceDataPage.tsx
          AdminQualificationGridsPage.tsx
          AdminImportsExportsPage.tsx
          AdminDataQualityPage.tsx
          AdminAuditPage.tsx
          AdminSecurityPage.tsx
          AdminTechnicalPage.tsx
        components/
          AdminSidebar.tsx
          AdminHeader.tsx
          AdminStatCard.tsx
          PermissionMatrix.tsx
          AuditLogTable.tsx
          ModuleStatusCard.tsx
          SeasonWizard.tsx
          ImportJobStatus.tsx
          DataQualityPanel.tsx
        services/
          adminApi.ts
        types/
          admin.types.ts
        hooks/
          useAdminDashboard.ts
          useAdminUsers.ts
          useAdminRoles.ts
          usePermissions.ts
```

Respecte les principes suivants :

- séparation claire des responsabilités ;
- composants réutilisables ;
- API typée ;
- contrôles de permissions côté backend et côté frontend ;
- pas de logique critique uniquement côté frontend ;
- audit automatique des actions sensibles ;
- tests sur toutes les règles critiques.

## 39. Synthèse stratégique

Le module d'administration doit devenir la colonne vertébrale de SPH - Swim Performance Hub. Il garantit la maîtrise du système, la qualité des données, la sécurité, la cohérence sportive et la capacité du club à évoluer sans dépendance permanente à un développeur.

Sa conception doit être traitée comme un module prioritaire, au même niveau que les inscriptions, les groupes, l'émargement et les performances.

La recommandation est de développer l'administration dès le MVP, mais avec un périmètre progressif : commencer par les utilisateurs, rôles, saisons, identité club et modules, puis enrichir avec les référentiels, grilles, imports, audit avancé et supervision technique.
