# La Magie Opéra — Tech Rider

## 1. Présentation de l'expérience

**La Magie Opéra** est une expérience VR multi-utilisateur en free-roam conçue pour une exploitation culturelle et événementielle.

## 2. Caractéristiques principales

| Élément | Spécification |
|---|---|
| Type | PCVR Free-Roam |
| Nombre de joueurs | Jusqu'à 12 joueurs simultanés |
| Durée en casque | Environ 23 min 30 |
| Durée opérationnelle recommandée | 40 minutes par session, onboarding/offboarding inclus |
| Âge recommandé | 10 ans et plus |
| Interaction | Hand tracking, sans contrôleurs |
| Déplacements | Déambulation libre dans l'espace |
| Accessibilité PMR | Possible selon l'aménagement du lieu |

> [!IMPORTANT]
> Le nombre de joueurs et l'architecture de la session doivent être validés en fonction du déploiement concerné.

## 3. Configuration de l'espace

### Zone de jeu

- Surface recommandée : **8 × 8 m**
- Zone libre de tout obstacle
- Hauteur recommandée : **supérieure à 2,8 m**
- Sol plat et stable
- Éclairage diffus et suffisamment homogène
- Présence de repères visuels contrastés et variés pour améliorer le tracking

### Zone opérateur / technique

- Espace technique recommandé : **15 à 20 m²**
- Accès aux ordinateurs, au réseau, à l'alimentation et au matériel de maintenance
- Zone protégée du public

### Zone d'attente

- Zone recommandée : **15 à 20 m²**

## 4. Matériel requis

### Casques VR

Casques recommandés :

- HTC VIVE Focus 3
- HTC VIVE Focus Vision

Pico 4 Ultra Enterprise peut être utilisé dans certaines configurations après validation technique.

> [!IMPORTANT]
> Les casques utilisent le hand tracking. Aucun contrôleur n'est nécessaire.

### Ordinateurs

Architecture PCVR avec :

- 1 poste serveur
- 1 poste client par joueur, selon l'architecture de déploiement retenue
- GPU et CPU adaptés à la version fournie

> [!TODO]
> Configuration minimale et recommandée des postes à confirmer selon la build et le parc matériel utilisé.

### Réseau

- Réseau local dédié
- Wi-Fi 6E dédié
- Ordinateurs connectés en Ethernet
- Tous les équipements doivent être sur le même sous-réseau
- Connexion Internet filaire requise pour la validation de licence

## 5. Infrastructure réseau

- Switch Ethernet Gigabit ou supérieur
- Points d'accès Wi-Fi dédiés
- Adressage IP fixe ou réservation DHCP recommandé pour les postes critiques
- Serveur et clients sur le même subnet

## 6. Alimentation électrique

Puissance électrique recommandée pour l'installation complète : **environ 10 kW**

> [!IMPORTANT]
> Le dimensionnement électrique définitif doit être validé avec l'équipe technique du lieu.

## 7. Installation

Temps indicatif :

- installation matériel : **environ 5 h**
- calibration et tests : **environ 3 h**
- démontage : **environ 5 h**

Chaque casque doit être calibré dans l'espace réel. Le tracking doit être testé sur l'ensemble de la surface de jeu.

## 8. Exploitation

Configuration recommandée :

- **2 opérateurs**

Configuration minimale :

- **1 opérateur**, uniquement avec une organisation stricte par sessions de 40 minutes.

## 9. Sécurité

Le site doit rester dégagé et conforme aux règles de sécurité du lieu. Les opérateurs doivent superviser les visiteurs pendant toute la session.

## 10. Maintenance

Prévoir quotidiennement :

- nettoyage des interfaces faciales ;
- contrôle des lentilles ;
- vérification du tracking ;
- contrôle réseau ;
- vérification de la charge des casques ;
- test du serveur et des clients avant ouverture.

## 11. Logistique

Configuration communiquée pour certains déploiements :

- **2 flight cases**
- dimensions indicatives : **60 × 160 × 80 cm**

> [!NOTE]
> La logistique exacte dépend du parc matériel inclus dans le déploiement.

## 12. Paramètres logiciels

Exemples d'arguments de lancement :

```bash
-server
-client
-team=GM
-team=Player
-team=Spectator
-team=TeleportPlayer
```

Exemple joueur :

```bash
-client -team=player -id=5 -color=orange
```

> [!WARNING]
> Les arguments disponibles peuvent varier selon la version de la build.

## 13. Checklist installation

- [ ] Zone de jeu 8 × 8 m libre
- [ ] Éclairage validé
- [ ] Ordinateurs installés
- [ ] Réseau Ethernet fonctionnel
- [ ] Wi-Fi dédié configuré
- [ ] Connexion Internet disponible
- [ ] Casques chargés
- [ ] Mapping / calibration effectués
- [ ] Serveur lancé
- [ ] Clients lancés
- [ ] Session complète testée
- [ ] Procédure opérateur validée

## 14. Version du document

**Version :** 0.1  
**Dernière mise à jour :** septembre 2026
