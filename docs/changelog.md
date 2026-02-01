# Changelog  

## 1.0 - 2026-01-17   
version: V1.02

- Ajout capteur PIR   
- Rallumage écran sur détection  
- Correction bug affichage valeurs
- Ajout du changelog sur la page web de l'afficheur

## 2.0 - 2026-01-18  
La version V1 est rendu obsolète  

Version: V2.00  

- Ajout Modèle ESP32-2432S028 résistif
- Mise en place de la callibration pour ESP32-2432S028 car le bus est SPI

## 2.0 - 2026-01-19  
Mise à jour de la doc  

## 2.0 - 2026-01-25 
Version V2.01
- Ajout de l'injection et passage en négatif et en rouge si injection (pas encore valider, pas de soleil ce jour)
- Ajout d'une Horloge sur une 3e pages de l'écran
- Ajout d'un programmateur journalier sur la page web pour permetre de choisir dans quel mode mettre l'afficheur
- Il y a 4 programmes horaire possibilité d'avoir l'écran sur la page normal (accueil) éteindre ou horloge
- Un case qui permet d'activer ou non le programmateur et un champ qui ouvre une popup pour l'info du mode de programme
- Ajout de modèle : ESP32-2432S028R  

## 2.0 - 2026-01-25  
Version V2.02  
- Ajout possibiliter de remonter l'info triac d'un routeur esclave et sera afficher en remplacement du triac par défaut
- Ajout du fuseau horaire pour la réunion (demande d'un utilisateur)
- Modification du code de la page web pour avoir une banière NEW VERSION  + numéro si une mise à jour est dispo
  
## 2.0 - 2026-01-27  
Version V2.03 
- Modification de la prise en compte du label sur la ligne 2 (tension ou production)
- Suppression de la ligne 4 si pas de JSY et PZEM activer (en réflexion sur l'usage future)
- Reprise de la gestion de la veille avec le programmateur actif (gestion sur les modes horloge et off) pas de besoin si page1 active

## 2.0 - 2026-01-27  
Version V2.04  
- Correction bug sur l'affichage de la vigilance
- Ajout de la récupération de TempoRte interne pour permettre à ceux qui sont sur d'ancienne version du routeur de pouvoir afficher
les couleurs Jour et Demain
- Modification de l'affichage de la ligne 4, si pas de JSY ou PZEM la ligne n'est plus afficher
- Modification pour renommer la ligne 2

## 2.0 - 2026-02-01  
Version V2.05  
- Correction bug sur la remonter d'info de TempoRte interne de l'esp quand le F1ATB est dans une version inférieur à V16.05
- Suppression du bouton plus bleu et mise en place d'un swiper sur le tactile (glissement du doigt pour changer de page)  
- Ajout d'une fonction pour les utilisateurs Jeedom, cette fonction permet de pouvoir afficher en ligne 4 de l'afficheur
la puissance totale routée depuis un virtuel qui fait la somme des puissances ( si plusieurs modules remonte l'info
→ exemple PZEM , Shelly et autres
- Mise à jour de la doc
  








 




