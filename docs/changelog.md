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
- Ajout de pouvoir allumer/éteindre/changer de page depuis l'envoi d'une commande MQTT depuis la domotique, ne fonctionne uniquement si le programmateur est désactiver

- Ajout d'un bouton dans la page LOG pour télécharger le log en fichier.txt
  
## 2.0 - 2026-02-03  
Version V2.06  
- Ajout de la possibilité de remonter l'info d'un SSR en pourcentage pour le routeur maître ou esclave (demande de lucianow1)  
  
## 2.0 - 2026-02-07  
Version V2.07  
- Ajout d'un bargraphe représentant un chauffe eau avec segment qui augmente et clignote lors de la chauffe
- Correction bug sur remonter de température
- Ajout d'une fonction supplémentaire pour remonter la production si besoin depuis la domotique en MQTT (testé sur JEEDOM)
- Ajout d'un bargraphe dedier (batterie) pour avoir l'info si en charge et remplissage

## 2.0 - 2026-02-08
Version V2.08
- Ajout d'une aleternative pour la météo, mise en place de l'info météo open-meteo (https://open-meteo.com/en/docs)
Cette API n'utilise pas de clé API et est entierement gratuite
Sur l'afficheur openweathermap est activer par défaut, il suffit d'activer open-météo depuis la page web
- Modification de la page web
- Correction d'un bug sur le bargraphe chauffe eau
- Ajout d'un bargraphe pour une batterie de stokage et alimenter par MQTT pour savoir elle est en charge et info de son % de charge

## 2.0 - 2026-02-09  
Version V2.08  
- Correction bug sur la fonction d'alternative de la météo
- Version V2.08 à réinstaller pour prendre en compte la correction

## 2.0 - 2026-02-10  
Version V2.09
- Ajout de remonter d'un 2e routeur esclave utiliser pour le moment uniquement pour l'info température canal 0 et 1
- Modification de la page web pour le 2e esclave

## 3.0 - 2026-02-14  
Version V3.00  
- Correction bug météo
- Ajout d'un Popup 'Aide MQTT' dans le formulaire MQTT F1ATB
- Remplacement du .bin de base sur le lien de téléchargement de départ (première mise ne service donc V3 par défaut)

## 3.0 - 2026-02-15
Version V3.01  
- Ajout de l'info TEMPO sur la page de l'horloge pour ceux ayant tempo
- Modification dans le Setup le démarage du server web et correction connexion au wifi
- Ajout d'un bargraphe radiateur avec choix du routeur esclave (1 ou 2)

## 3.0 - 2026-02-20  
Version V3.02  
- Ajout rotation de l'écran (demandé) non testé sur ESP32-2432S028R
- Ajout d'une page web pour Live Data
  
![Live-data](https://github.com/user-attachments/assets/11eedb49-1e95-4cc4-af5e-e5d5957590ae)  


## 3.0 - 2026-03-01
Version V3.03  
- Ajout d'une page Energie type HA
  
  ![Page-energie avec batterie](https://github.com/user-attachments/assets/02ad3e8f-d3a1-4532-9d80-e4675cfd28a8)

- Ajout d'un bargraphe batterie de stockage, fonction possible :
  remonter du % de charge et puissance de charge
  Si les 2 infos sont remonter le bargraphe indiquera le % de charge sur les segments,
  si seul l'info de puissance de charge , les segments seront animés
- Ajout fonction pour lancer un forçage de chauffe de 30 min sur le routeur par un mouvement de glisser de doigt 
 sur l'afficheur de bas en haut et arrêter le forçage par un glisser de haut en bas
- Ajout d'une fonction de contrôle et info avec l'application Telegram (voir doc)
- Modification des fonctions perso

## 3.0 - 2026-03-08
Version V3.04   

- Correction de l'animation des points sur la page Energie Live  
- Modification du code pour l'utilisation de Telegram , passage de la fonction sur le core 0
- Ajout de l'utilisation d'un PZEM PZEM-004T brancher sur l'afficheur (permet d'avoir une info de puissance si l'afficheur est installer
  sur un tableau
  
- Utilisation de la librairie MycilaPZEM de Mathieu Carbour
  
- Pin utiliser pour le PZEM : pin 22 relier sur RX et pin 21 relier sur TX permet d'être plus simple pour l'utilisation d'un JC2432W328
- Modification en pin 35 pour le capteur PIR

## 3.0 - 2026-03-14  
Version V3.04  
Cette version est à télécharger depuis la page de téléchargement de première mise en service car le firmware passe pas dans la mise à jour classique   
- version V3.041 (mise à jour classique avec modification du code sur la réception topic pour la batterie

## 3.0 -2026-03-22  
Version V3.05  
Il n'est pas possible de télécharger cette version si la V3.04 n'est pas encore en place sur l'afficheur.

- Refonte totale des pages web
- Ajout d'un écran qui reproduit la page web VISUALISATION LIVE, elle peut-être appeler depuis le programmateur dans Mode → Dashboard Web
- Ajout d'un mode déporté de l'afficheur pour être utiliser sur la tableau électrique ou autre

![Afficheur-déporté-tableau](https://github.com/user-attachments/assets/5ac68c37-da7c-49ce-8ac0-420c9dbb0b41)

## 3.0 - 2026-03-27  
Version V3.06 / 07  
- Correction bug pour utilisation PZEM sur ESP32-2432S028 (passage en V3.07 si utilisation d'un ESP32-2432S028)
- Correction topic et payload pour info photovoltaique depuis MQTT extern
- Modification de la méthode de téléchargement des firmware depuis github
- Correction bug pour le programmateur sur écran déporté 

## 3.0 - 2026-03-29  
Version V3.08  
- Alternative de choix entre un PZEM connecté sur l'afficheur ou reception de l'info depuis MQTT extern
- Modification pour l'info puissance routé sur le mode afficheur déporté
- Modification de l'intitulé pour les fonctions PZEM écran déporté
- Correction pour le téléchargement du bin depuis le PC (problème de watchdog)
- Suppression de l'activation de la vigilance par défaut (car en mode déporté elle s'affiche sur la jauge)
- Modification pour la réception du topic production photovoltaïque (problème avec domoticz)  
 

 
 



 




