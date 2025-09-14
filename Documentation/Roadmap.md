# 🛤️ **Roadmap de l'Ordinateur de Bord**

Liste en diagramme d'organisation de l'ordinateur de bord.

## 📅 **Calendrier des tâches**

Les tâches et réunions sont gérées via [le calendrier Teams Avionique](https://ulavaldti.sharepoint.com/sites/exch_fsg_0572/SitePages/Avionique.aspx). Cliquez pour accéder aux événements à venir.

## 🎯 **Objectifs**
- [ ] ODB autonomne pouvant déclencher les pyros sans support CUTS
- [ ] Deux ODB autonomne pour la conception d'une fusée à 2 étage
- À déterminer...

## 🛠️ **Conception du PCB**
- [ ] Définir les spécifications du PCB
  - [ ] Établir les dimensions du PCB
  - [ ] Identifier les contraintes de puissance et de chaleur
- [ ] Sélectionner les composants
  - [ ] Choisir le microcontrôleur (ex: STM32F103C8)
  - [ ] Déterminer les capteurs nécessaires (ex: accéléromètre, baromètre)
  - [ ] Sélectionner les connecteurs et autres composants passifs
- [ ] Créer un schéma électrique
  - [ ] Intégrer les composants sélectionnés dans le schéma
  - [ ] Vérifier les connexions et les erreurs de circuit
- [ ] Concevoir le layout du PCB
  - [ ] Placer les composants sur le PCB
  - [ ] Tracer les pistes et optimiser le routage
  - [ ] Vérifier les règles de conception (DRC)
- [ ] Vérifier le design pour les erreurs
  - [ ] Réaliser une simulation de circuit si possible
  - [ ] Effectuer une revue de design avec l'équipe
- [ ] Commander le PCB
  - [ ] Choisir un fournisseur de PCB
  - [ ] Passer commande et suivre le statut
- [ ] Assembler le prototype
  - [ ] Solder les composants sur le PCB
  - [ ] Inspecter les soudures et vérifier les connexions
- [ ] Tester le prototype
  - [ ] Vérifier l'alimentation et les connexions
  - [ ] Tester chaque fonctionnalité (ex: capteurs, communication)

## 💻 **Programmation**
- [ ] Définir l'architecture logicielle
  - [ ] Établir l'organisation des fichiers et des modules
- [ ] Écrire le code pour le microcontrôleur
  - [ ] Initialiser les composants matériels
  - [ ] Implémenter les fonctions de base (ex: lecture de capteurs)
- [ ] Mettre en place la communication entre les modules
  - [ ] Configurer les protocoles de communication (ex: USART, SPI, I2C)
  - [ ] Tester la communication entre les différents modules
- [ ] Développer les drivers pour les composants
  - [ ] Écrire des drivers pour chaque capteur et module
  - [ ] Tester chaque driver individuellement
- [ ] Tester et déboguer le code
  - [ ] Effectuer des tests unitaires sur chaque fonction
  - [ ] Utiliser un débogueur pour identifier les problèmes
- [ ] Documenter le code et les fonctionnalités
  - [ ] Rédiger des commentaires dans le code
  - [ ] Créer un document de spécifications techniques
- [ ] Préparer le firmware pour la première itération
  - [ ] Créer un script de téléchargement du firmware
  - [ ] Tester le chargement du firmware sur le prototype
- [ ] Développer la boucle principale d'exécution pour le comportement de la fusée pendant un lancement
  - [ ] Créer une main loop
  - [ ] Établir une structure d'exécution des différents composants liés
  - [ ] Tester le chargement du firmware sur le prototype

## 🌳 **Diagramme des composantes**

- Accéléromètre / Gyroscope
  - Mesure d'accélération
    - [ ] Écrire le driver pour le capteur
    - [ ] Tester la fonctionnalité de mesure
  - Détection de rotation
    - [ ] Implémenter la fonction de détection de rotation
    - [ ] Vérifier l'exactitude des données
  - Orientation (roll, pitch)
    - [ ] Intégrer les mesures d'orientation dans le code
    - [ ] Tester les valeurs d'orientation
  - Gestion du Mach lock
    - [ ] Développer la logique de gestion du Mach lock
    - [ ] Tester les transitions de Mach lock
    - [ ] Définir les composantes à mettre sous le Mach lock
- Baromètre
  - Mesure d'altitude
    - [ ] Écrire le driver pour le baromètre
    - [ ] Tester la précision des mesures d'altitude
  - Mesure de température
    - [ ] Implémenter la lecture de la température
    - [ ] Vérifier la calibration du capteur
- GPS Module
  - Latitude
    - [ ] Écrire le driver pour le module GPS
    - [ ] Tester la lecture de la latitude
  - Longitude
    - [ ] Tester la lecture de la longitude
    - [ ] Vérifier la précision des coordonnées
- Microcontrôleur (STM32)
  - Traitement des données
    - [ ] Établir l'organisation des fichiers et des modules
    - [ ] Implémenter la boucle principale d'exécution
  - Communication
    - [ ] Configurer les protocoles de communication (ex: USART, SPI, I2C)
    - [ ] Tester la communication entre les différents modules
  - Gestion des capteurs
    - [ ] Initialiser les composants matériels
    - [ ] Implémenter les fonctions de lecture des capteurs
- Carte SD
  - Stockage des données
    - [ ] Écrire les fonctions de sauvegarde des données
    - [ ] Tester l'écriture sur la carte SD
  - Récupération des données
    - [ ] Développer les fonctions de lecture des données
    - [ ] Tester la récupération des données stockées
- Drogue chute
  - Déclenchement à l'apogée
    - [ ] Écrire le code pour le déclenchement
    - [ ] Tester le mécanisme de déclenchement
- Main chute
  - Déclenchement à basse altitude
    - [ ] Implémenter la logique de déclenchement
    - [ ] Vérifier le fonctionnement à différentes altitudes
- Alimentation (Batterie)
  - [ ] Vérifier l'alimentation et les connexions
  - [ ] Tester la durée de vie de la batterie
- Indicateurs LED
  - [ ] Développer le code pour contrôler les LEDs
  - [ ] Tester les indications visuelles
- Buzzer
  - [ ] Développer le code pour contrôler le buzzer
  - [ ] Créer des modèles sonores pour déterminer le comportement de l'ODB
  - [ ] Tester les modèles sonores dans différents états de l'ODB
- Connecteurs
  - [ ] Vérifier la compatibilité des connecteurs
  - [ ] Tester la connectivité entre les composants

## 📈 **Notes d'amélioration**

L'itération de ce projet (ODB2) vis à améliorer la première version de se projet (ODB1).
- Retirer module bluetooth N'est pas utile à longue portée.
- Retirer LED RGB Remplacer par LEDS d'états individuels ou implémenter des états via des modulations sonores du buzzer.
- Augmenter la puissance radio et le débit de données
- Modifier le buzzer pour émettre des sons plus forts
- Modification des paramètres des composants onboard
- Implémentation des modes de consommation énergétique (Fix ODB1 pin CS)
- Améliorer la durée de vie des batteries de tous les systèmes
- Transmettre les étapes d'évolution via les paquets radio
- Améliorer la puissance du processeur (Série F4 monocoeur minimum)
- ...

## 💡 **Idées**

- Développer un système de recharge de batteries qui se déploie sur la platforme de lancement
- Développer un module de caméra au sol et à l'intérieur de la fusée
- Développer un système de *répeteur radio* via une charge utile éjectable (Payload)
- Sous-systèmes de l'ordinateur de bord modulaire via la liaison CanBus

---

🔙 Retour à la [page principale](../README.md)
