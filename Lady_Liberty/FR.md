# Lady Liberty — Tech Rider

> [!NOTE]
> Ce document décrit une configuration avec **une seule salle et une seule instance de l'expérience**.

## 1. Présentation de l'expérience

**Lady Liberty** est une expérience VR immersive en déambulation libre conçue pour une exploitation culturelle et événementielle. Les visiteurs évoluent physiquement dans une zone réelle dont les limites correspondent à l'espace virtuel.

## 2. Caractéristiques principales

| Élément | Spécification |
|---|---|
| Type | VR standalone multi-utilisateur en free-roam |
| Configuration couverte | 1 salle / 1 instance |
| Nombre de visiteurs | Jusqu'à 10 visiteurs simultanés |
| Zone de jeu | 8 × 6,5 m |
| Hauteur recommandée | Environ 3 m |
| Interaction | Hand tracking, sans contrôleurs |
| Déplacements | Déambulation libre |
| Casque de référence | HTC VIVE Focus Vision |
| Architecture | 1 ordinateur serveur et 1 point d'accès Wi-Fi pour la salle |

> [!TODO]
> À confirmer selon la version livrée : durée exacte de l'expérience, âge minimum et configuration matérielle définitive.

## 3. Configuration de l'espace

### Salle et zone de jeu

- Zone utile : **8 × 6,5 m**
- Hauteur recommandée : **environ 3 m**
- Sol plat, stable et non réfléchissant
- Zone libre de tout obstacle
- Aucun élément saillant à hauteur de tête ou de bras
- Accès contrôlé pendant l'expérience
- Éclairage diffus, stable et suffisamment homogène
- Repères visuels contrastés et variés pour assurer le tracking des casques

> [!IMPORTANT]
> Les limites virtuelles doivent correspondre précisément aux limites réelles de la salle. La zone doit rester entièrement dégagée pendant l'exploitation.

> [!WARNING]
> Les surfaces très réfléchissantes, transparentes, uniformes ou soumises à des variations importantes de lumière peuvent dégrader le tracking.

### Zone opérateur / technique

Prévoir à proximité immédiate :

- l'ordinateur serveur ;
- le switch et le point d'accès Wi-Fi ;
- l'alimentation et les chargeurs ;
- le matériel de nettoyage et de maintenance ;
- un écran de supervision opérateur, selon la configuration livrée.

Le matériel technique doit être protégé et inaccessible au public.

### Accueil et équipement

Prévoir un espace distinct permettant :

- le briefing de sécurité ;
- la distribution et l'ajustement des casques ;
- le stockage et la recharge des casques ;
- le nettoyage entre deux groupes ;
- la sortie des visiteurs sans croisement avec le groupe suivant, si le lieu le permet.

## 4. Matériel requis

### Casques VR

Configuration de référence :

- **10 casques HTC VIVE Focus Vision** pour les visiteurs ;
- casques supplémentaires de secours recommandés ;
- interfaces faciales lavables ou remplaçables ;
- alimentation et chargeurs adaptés.

> [!NOTE]
> Une adaptation sur Pico 4 Ultra Enterprise peut être étudiée après validation technique de la build et du dispositif.

> [!IMPORTANT]
> L'expérience utilise le hand tracking. Aucun contrôleur n'est nécessaire.

### Ordinateur serveur

- **1 ordinateur serveur** pour la salle ;
- connexion Ethernet filaire au réseau de l'expérience ;
- écran, clavier et souris pour l'exploitation et la maintenance ;
- accès Internet pour les services nécessitant une validation en ligne.

Configuration minimale validée :

| Composant | Spécification minimale |
|---|---|
| Processeur | Intel Core i7-3770 à 3,40 GHz |
| Mémoire vive | 32 Go de RAM |
| Stockage système | SSD 250 Go (233 Go utiles sur le poste de référence) |
| Stockage complémentaire | HDD 1 To (932 Go utiles sur le poste de référence) |
| Carte graphique | NVIDIA GeForce GTX 970, 4 Go |
| Architecture système | Système d'exploitation 64 bits, processeur x64 |

> [!NOTE]
> Le poste de référence utilisé pour valider cette configuration porte le nom `BKL01`. Les identifiants Windows propres à cette machine ne sont pas nécessaires pour reproduire l'installation.

### Réseau

- **1 point d'accès Wi-Fi dédié à la salle**
- réseau local dédié à l'expérience
- switch Ethernet Gigabit ou supérieur
- ordinateur serveur connecté en Ethernet
- casques et serveur sur le même sous-réseau
- connexion Internet filaire disponible pour la validation de licence et le support
- adressage IP fixe ou réservations DHCP recommandés pour les équipements critiques

> [!IMPORTANT]
> Le Wi-Fi de l'expérience doit être dédié. Le point d'accès ne doit pas servir au Wi-Fi public ou bureautique du lieu.

> [!WARNING]
> Le nombre de casques réellement supporté par un point d'accès dépend du modèle, de sa configuration radio et de l'environnement du site. Un test en charge avec les 10 casques est obligatoire avant ouverture.

## 5. Infrastructure réseau

Architecture pour une salle :

```text
Connexion Internet
        |
Routeur / pare-feu
        |
Switch Gigabit
   |            |
Serveur      Point d'accès Wi-Fi
                  |
            10 casques VR
```

Recommandations :

- réserver un SSID à l'expérience ;
- désactiver l'isolation des clients ;
- éviter les réseaux mesh et les répéteurs Wi-Fi ;
- maintenir tous les équipements sur le même VLAN / sous-réseau ;
- documenter les adresses IP et les accès d'administration ;
- vérifier l'absence d'interférences radio avant l'installation.

## 6. Alimentation électrique

Prévoir des circuits et prises permettant d'alimenter :

- l'ordinateur serveur et son écran ;
- le switch et le point d'accès ;
- les chargeurs des casques ;
- les équipements de supervision et de maintenance.

> [!TODO]
> Puissance électrique totale et répartition des circuits à confirmer après validation de la configuration matérielle définitive.

> [!NOTE]
> Un onduleur est recommandé pour le serveur et les équipements réseau afin d'éviter un arrêt brutal en cas de microcoupure.

## 7. Installation

L'installation comprend au minimum :

1. contrôle et dégagement de la zone de jeu ;
2. installation de l'ordinateur serveur et du réseau ;
3. configuration du point d'accès dédié ;
4. installation et mise à jour des casques ;
5. mapping / calibration de la salle sur chaque casque ;
6. vérification de la correspondance entre limites réelles et virtuelles ;
7. test du hand tracking ;
8. test réseau avec tous les casques connectés ;
9. test complet d'une session en conditions réelles ;
10. validation de la procédure opérateur et sécurité.

> [!TODO]
> Temps d'installation, de calibration et de démontage à confirmer selon le site et le matériel livré.

## 8. Installation logicielle et première configuration

Trois installations logicielles sont nécessaires :

1. l'expérience et son serveur sur l'ordinateur Windows ;
2. l'APK de l'expérience sur chaque casque ;
3. l'APK de contrôle sur la tablette Android.

### 8.1 Installation sur l'ordinateur serveur

1. Installer la version PC fournie de **Lady Liberty**.
2. Créer deux raccourcis vers l'exécutable de l'expérience.
3. Ajouter les arguments suivants dans le champ **Cible** de chaque raccourci, après le chemin de l'exécutable.

Raccourci du serveur temporaire **NoName** :

```text
-server -team=gm
```

Raccourci du serveur de la salle **ROOM01** :

```text
-server -team=gm -sessionname=ROOM01
```

> [!IMPORTANT]
> Le raccourci sans `-sessionname` ouvre le serveur **NoName**. Il sert à détecter et à configurer les casques avant de les affecter à la salle `ROOM01`.

### 8.2 Première connexion au serveur

Lors du premier lancement de l'expérience sur l'ordinateur :

1. saisir les identifiants fournis, avec l'adresse e-mail et le mot de passe ;
2. vérifier que les identifiants sont correctement enregistrés ;
3. fermer l'application si nécessaire ;
4. lancer le serveur **NoName** ;
5. lancer ensuite le serveur **ROOM01**.

> [!WARNING]
> Ne pas fermer le serveur NoName avant d'avoir affecté tous les casques à la session ROOM01.

### 8.3 Installation et configuration des casques

1. Installer l'APK fourni sur chaque casque.
2. Lancer l'application dans le casque.
3. Au premier lancement, le casque se connecte automatiquement au serveur **NoName**.
4. Dans l'interface du serveur, cliquer sur le numéro du casque détecté.
5. Modifier les paramètres nécessaires :
   - numéro du casque ;
   - couleur du joueur ;
   - serveur / session de destination, ici `ROOM01`.
6. Fermer la fenêtre de réglage pour appliquer les modifications.

Si la session a été modifiée, l'application s'arrête dans le casque. À son prochain lancement, elle doit se connecter automatiquement à la session sélectionnée.

Une fois tous les casques affectés à `ROOM01` et leur connexion vérifiée, le serveur **NoName** peut être fermé.

### 8.4 Mode kiosque des casques

Configurer chaque casque en **mode kiosque** et définir Lady Liberty comme application à lancer automatiquement.

> [!IMPORTANT]
> Le mode kiosque permet à l'application de redémarrer automatiquement lorsqu'elle se ferme. C'est notamment le cas après un changement de session ou de langue : l'application se ferme, puis se relance avec le nouveau réglage.

### 8.5 Installation et connexion de la tablette Android

1. Installer l'APK de contrôle fourni sur la tablette Android.
2. Vérifier que la tablette est connectée au même réseau local que le serveur.
3. Lancer l'application.
4. Sélectionner, en haut de l'écran, la salle à administrer dans la liste des salles disponibles.
5. Choisir `ROOM01`.
6. Appuyer sur **Connecter**.

La tablette peut ensuite accéder aux fonctions de contrôle disponibles pour cette salle.

### 8.6 Contrôle final

- [ ] Les identifiants sont enregistrés sur le serveur
- [ ] Les raccourcis NoName et ROOM01 fonctionnent
- [ ] Le serveur ROOM01 apparaît sur le réseau
- [ ] L'APK est installé sur tous les casques
- [ ] Chaque casque possède le bon numéro et la bonne couleur
- [ ] Tous les casques se connectent à ROOM01
- [ ] Le mode kiosque relance correctement l'application
- [ ] L'APK de contrôle est installé sur la tablette
- [ ] La tablette voit ROOM01 et s'y connecte
- [ ] Le serveur NoName est fermé après la configuration

## 9. Exploitation

Avant chaque ouverture :

- démarrer et contrôler le serveur ;
- vérifier le réseau et le point d'accès ;
- tester un lancement complet ;
- contrôler la charge, les lentilles, le son et le tracking de chaque casque ;
- vérifier que la salle est vide et dégagée.

Entre deux groupes :

- arrêter ou réinitialiser la session ;
- récupérer et inspecter les casques ;
- nettoyer les interfaces faciales ;
- vérifier rapidement la charge et le tracking ;
- préparer les casques pour le groupe suivant.

> [!TODO]
> Nombre minimal d'opérateurs et cadence exacte des sessions à confirmer selon le parcours visiteurs et l'organisation du lieu.

## 10. Consignes de sécurité

Les visiteurs doivent être informés que :

- les murs et limites de jeu correspondent généralement à de vrais murs ;
- ils ne doivent jamais traverser une limite ;
- le reste du décor est virtuel ;
- ils ne doivent pas s'asseoir ni s'appuyer sur un élément virtuel ;
- ils doivent marcher sans courir ;
- ils doivent suivre immédiatement les instructions des opérateurs.

Les opérateurs doivent surveiller la salle pendant toute la session et pouvoir interrompre l'expérience si nécessaire.

## 11. Maintenance

Contrôles quotidiens :

- nettoyage et désinfection des interfaces faciales ;
- inspection des lentilles et des sangles ;
- contrôle de la charge des casques ;
- vérification du tracking et du hand tracking ;
- contrôle du réseau et de la connexion Internet ;
- test du serveur et de la build ;
- vérification visuelle de la salle et des repères de tracking.

Prévoir au minimum :

- interfaces faciales de rechange ;
- câbles et alimentations de secours ;
- batteries ou casques de remplacement selon la cadence ;
- matériel de nettoyage compatible avec les casques.

## 12. Logistique

> [!TODO]
> À confirmer : nombre de flight cases, dimensions, poids, contenu exact du parc, conditions de stockage et besoins de manutention pour une salle.

## 13. Paramètres logiciels

Arguments de lancement actuellement documentés :

```text
-server -team=gm
-server -team=gm -sessionname=ROOM01
```

> [!TODO]
> À compléter avec le nom exact de l'exécutable, la procédure d'arrêt complète et les outils de supervision propres à la build livrée.

## 14. Checklist installation

- [ ] Salle de 8 × 6,5 m disponible et dégagée
- [ ] Hauteur et accès validés
- [ ] Éclairage validé
- [ ] Repères de tracking installés si nécessaire
- [ ] Serveur installé et testé
- [ ] Switch Ethernet opérationnel
- [ ] Point d'accès dédié configuré
- [ ] SSID et sous-réseau validés
- [ ] Connexion Internet disponible
- [ ] 10 casques préparés et chargés
- [ ] Casques de secours disponibles
- [ ] Mapping effectué sur chaque casque
- [ ] Limites réelles et virtuelles vérifiées
- [ ] Hand tracking testé
- [ ] Test réseau en charge effectué
- [ ] Session complète testée
- [ ] Procédure opérateur validée
- [ ] Procédure d'arrêt d'urgence validée
- [ ] Matériel de nettoyage disponible

## 15. Version du document

**Configuration :** 1 salle / 1 instance  
**Version :** 0.2  
**Dernière mise à jour :** septembre 2026
