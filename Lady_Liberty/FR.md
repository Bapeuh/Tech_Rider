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

Le dossier de livraison de **Lady Liberty** contient trois sous-dossiers correspondant aux trois composants à installer :

```text
Lady_Liberty/
├── Tablette_Android/
├── Game_Windows/
└── Game_Android/
```

| Dossier | Destination | Fonction |
|---|---|---|
| `Tablette_Android` | Tablette Android | Interface de contrôle des sessions |
| `Game_Windows` | Ordinateur serveur | Serveur et interface opérateur |
| `Game_Android` | Casques VR | Application Lady Liberty destinée aux visiteurs |

> [!IMPORTANT]
> L’ordinateur serveur, la tablette et tous les casques doivent être connectés au même réseau local et placés sur le même sous-réseau.

### 8.1 Installation du serveur Windows

Le dossier `Game_Windows` contient l’installateur de l’application serveur, notamment :

```text
Lady Liberty_1.0.0.5_Installer.exe
Lady Liberty_1.0.0.5_Installer-1.bin
```

Les deux fichiers doivent rester dans le même dossier pendant l’installation.

#### Procédure d’installation

1. Ouvrir le dossier `Game_Windows`.
2. Double-cliquer sur `Lady Liberty_1.0.0.5_Installer.exe`.
3. Suivre les différentes étapes de l’assistant d’installation.
4. Lorsque l’installateur le demande, renseigner le nom de la session correspondant à la salle.

Exemple :

```text
Session01
```

> [!IMPORTANT]
> Le nom de la session doit être exactement identique sur le serveur et dans le fichier `setup.ini` utilisé pour l’installation des casques. Il est recommandé d’utiliser un nom simple, sans espace ni caractère spécial.

#### Première connexion

Une fois l’installation terminée :

1. lancer l’application Lady Liberty ;
2. saisir l’adresse e-mail et le mot de passe fournis ;
3. vérifier que les identifiants sont correctement enregistrés ;
4. vérifier que le serveur démarre avec le nom de session configuré.

Le raccourci du serveur nommé utilise les arguments suivants :

```text
-server -team=gm -sessionname=Session01
```

`Session01` doit être remplacé par le nom choisi lors de l’installation.

### 8.2 Installation de la tablette Android

Le dossier `Tablette_Android` contient l’APK de l’interface de contrôle ainsi que les fichiers nécessaires à son installation.

#### Procédure d’installation

1. installer l’APK fourni sur la tablette Android ;
2. connecter la tablette au même réseau local que le serveur et les casques ;
3. lancer l’application de contrôle.

La première fenêtre de l’application affiche les différentes sessions détectées sur le réseau ainsi que leur état.

Pour accéder à une salle :

1. sélectionner la session souhaitée dans la liste ;
2. appuyer sur **Connecter** ;
3. attendre l’ouverture de l’interface de gestion de la partie.

L’interface de la tablette présente les mêmes informations principales que l’interface opérateur disponible sur l’ordinateur serveur.

> [!WARNING]
> Si aucune session n’apparaît, vérifier que la tablette est connectée au bon réseau, que le serveur est lancé et que les équipements se trouvent sur le même sous-réseau.

### 8.3 Installation de l’application sur les casques

Le dossier `Game_Android` contient notamment :

```text
setup.ini
LadyLiberty-Android-Shipping-arm64.apk
Install_LadyLiberty_WithID.bat
Install_LadyLiberty.bat
```

Il peut également contenir des fichiers ou dossiers complémentaires nécessaires à l’installation. Ils doivent être conservés dans leur emplacement d’origine.

#### Configuration du nom de session

Avant d’installer l’application sur les casques :

1. ouvrir le fichier `setup.ini` ;
2. renseigner le nom de la session ;
3. utiliser exactement le même nom que celui configuré sur le serveur ;
4. enregistrer le fichier avant de lancer le script d’installation.

Exemple :

```text
Session01
```

> [!IMPORTANT]
> Une différence de nom, de casse ou d’orthographe empêchera le casque de rejoindre automatiquement la bonne session.

### 8.4 Installation avec attribution directe d’un identifiant

Pour installer l’application et attribuer directement un numéro au casque, utiliser :

```text
Install_LadyLiberty_WithID.bat
```

Ce script permet d’assigner un identifiant au casque pendant l’installation. Cet identifiant apparaîtra ensuite dans l’interface opérateur sur l’ordinateur et sur la tablette.

Procédure recommandée :

1. connecter un seul casque à l’ordinateur ;
2. vérifier que le casque est correctement détecté ;
3. lancer `Install_LadyLiberty_WithID.bat` ;
4. saisir l’identifiant demandé ;
5. attendre la confirmation de la fin de l’installation ;
6. débrancher le casque ;
7. répéter l’opération avec le casque suivant en utilisant un identifiant différent.

> [!IMPORTANT]
> Chaque casque d’une même installation doit disposer d’un identifiant unique.

### 8.5 Installation sans attribution directe d’un identifiant

Pour installer l’application sans attribuer immédiatement de numéro au casque, utiliser :

```text
Install_LadyLiberty.bat
```

Le numéro du casque pourra ensuite être modifié depuis l’interface opérateur.

Cette méthode peut être utilisée lorsque l’attribution des identifiants est effectuée ultérieurement ou lorsque la configuration finale est réalisée depuis le serveur.

### 8.6 Installation des casques avec un MDM

L’APK peut également être déployé directement sur les casques à l’aide d’un outil MDM.

Dans cette configuration :

- tous les casques reçoivent initialement l’identifiant `72` ;
- tous les casques sont initialement affectés à la session `NoName` ;
- les identifiants et les sessions doivent ensuite être configurés manuellement depuis l’interface opérateur.

> [!WARNING]
> Tant que les casques n’ont pas été reconfigurés, ils peuvent apparaître avec le même identifiant `72`. Il est nécessaire de les traiter individuellement afin de leur attribuer un identifiant unique.

### 8.7 Création d’un serveur temporaire NoName

Pour récupérer et configurer les casques installés par MDM, il faut lancer simultanément :

- le serveur correspondant à la salle, par exemple `Session01` ;
- un serveur temporaire sans nom de session, appelé `NoName`.

#### Création du raccourci NoName

1. repérer le raccourci de Lady Liberty sur le bureau de l’ordinateur serveur ;
2. copier ce raccourci ;
3. renommer la copie, par exemple :

```text
Lady Liberty — NoName
```

4. effectuer un clic droit sur ce nouveau raccourci ;
5. ouvrir **Propriétés** ;
6. dans le champ **Cible**, retirer complètement l’argument :

```text
-sessionname=Session01
```

Le raccourci du serveur NoName doit conserver uniquement les arguments suivants :

```text
-server -team=gm
```

Le raccourci du serveur de la salle doit conserver :

```text
-server -team=gm -sessionname=Session01
```

### 8.8 Affectation des casques à la bonne session

1. lancer le serveur `NoName` ;
2. lancer le serveur nommé, par exemple `Session01` ;
3. lancer l’application Lady Liberty sur le casque ;
4. attendre que le casque apparaisse dans l’interface du serveur NoName ;
5. cliquer sur l’identifiant du casque ;
6. dans la fenêtre de configuration, modifier :
   - l’identifiant du casque ;
   - la couleur du joueur, si nécessaire ;
   - la session de destination ;
7. sélectionner la session correspondant à la salle, par exemple `Session01` ;
8. fermer la fenêtre de configuration pour enregistrer les modifications.

Lorsque les paramètres sont modifiés, l’application Lady Liberty se ferme automatiquement dans le casque.

Il faut ensuite relancer l’application pour charger les nouveaux paramètres. Le casque doit alors se connecter automatiquement à la session sélectionnée.

Répéter cette opération pour chaque casque.

Lorsque tous les casques :

- possèdent un identifiant unique ;
- sont affectés à la bonne session ;
- apparaissent correctement sur le serveur nommé ;

le serveur `NoName` peut être fermé.

> [!IMPORTANT]
> Ne pas fermer le serveur NoName avant d’avoir configuré et vérifié tous les casques.

### 8.9 Configuration du mode kiosque

L’utilisation du mode kiosque est fortement recommandée sur tous les casques.

Lady Liberty doit être définie comme application autorisée et comme application à lancer automatiquement.

Le mode kiosque permet à l’application de redémarrer automatiquement lorsqu’elle se ferme, notamment après :

- un changement d’identifiant ;
- un changement de session ;
- un changement de langue ;
- un arrêt involontaire de l’application.

Lorsqu’un paramètre est modifié, l’application se ferme puis se relance automatiquement avec la nouvelle configuration.

> [!NOTE]
> Sans mode kiosque, l’opérateur devra relancer manuellement Lady Liberty dans le casque après chaque modification nécessitant le redémarrage de l’application.

### 8.10 Vérification finale de l’installation

Avant de valider l’installation, vérifier les points suivants :

- [ ] Le serveur Windows est installé.
- [ ] L’adresse e-mail et le mot de passe ont été enregistrés.
- [ ] Le serveur démarre avec le bon nom de session.
- [ ] La tablette est connectée au même réseau que le serveur et les casques.
- [ ] L’application de contrôle est installée sur la tablette.
- [ ] La tablette détecte la session configurée.
- [ ] L’application Lady Liberty est installée sur chaque casque.
- [ ] Le fichier `setup.ini` contient le bon nom de session.
- [ ] Chaque casque possède un identifiant unique.
- [ ] Chaque casque est affecté à la bonne session.
- [ ] Tous les casques apparaissent dans l’interface opérateur.
- [ ] Tous les casques apparaissent dans l’application tablette.
- [ ] Le mode kiosque relance correctement Lady Liberty.
- [ ] Le serveur NoName est fermé après la configuration.
- [ ] Une session complète a été testée avec tous les casques.

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
-server -team=gm -sessionname=Session01
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
**Version :** 0.3  
**Dernière mise à jour :** septembre 2026
