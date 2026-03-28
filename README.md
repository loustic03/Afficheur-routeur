## Afficheur pour routeur F1ATB   

Développer à la base pour un usage pour ceux n'ayant pas de domotique    

<img width="581" height="334" alt="image" src="https://github.com/user-attachments/assets/c74c5e4c-1378-43e0-a46b-b766842ff591" />  

C’est un écran type JC2432W328 type capacitif sur I2C donné pour un touch CST816S mais plutôt CST820
donc utilisation panel : ST7789 et touch CST819S sur LovyangGFX  

<img width="378" height="383" alt="image" src="https://github.com/user-attachments/assets/b18c3798-eca2-48e7-952c-e9b3c7acc8b9" />  

Modèle ESP32-2432S028 résistif (plusieurs modèles existe et ce ressemble, il y en a qui sont en version R mais non spécifier)  

Utilisation panel : ST7789 et touch XPT2046 sur LovyangGFX pour le vrai 243S028 et utilisation panel :  ILI9341 et touch XPT2046 sur LovyangGFX pour le 243S028R  

<img width="405" height="251" alt="image" src="https://github.com/user-attachments/assets/1c9cb51f-2fc6-4583-ac8c-a385772bfaee" />    

# Mise en place du firmware pour la première fois , utiliser le lien suivant   

Attention le web installateur ne fonctionne pas avec Firefox / Safari  

Connecter l’écran sur le PC avec un câble de bonne qualité   

[Téléchargement du code](https://loustic03.github.io/Afficheur-routeur)  

Une page web s’ouvre de ce type  
<img width="586" height="251" alt="image" src="https://github.com/user-attachments/assets/1f42d5de-367c-45b1-a324-696bb76a312d" />  

Ensuite cliquer sur le bouton Connect , une fenêtre s’ouvre et cliquer sur le port indiquer dans la fenêtre   

<img width="284" height="62" alt="image" src="https://github.com/user-attachments/assets/23f95a82-e137-4799-a008-e20bcd4ac6a1" />    

Ensuite un clic sur connecté et une fenêtre s’ouvre pour pouvoir télécharger le firmware  

<img width="411" height="277" alt="image" src="https://github.com/user-attachments/assets/cc3b74d7-8eef-4ed3-ab11-0f90ecdb28f3" />    

Attention il faut tenir appuyer le bouton Boot qui ce trouve derrière l’écran avant de cliquer sur  
**Install Afficheur routeur** quand le téléchargement commence le bouton boot peut-être relâcher  

une fois le téléchargement fini, une fenêtre s’ouvre pour avertir de la fin de l’Upload  

<img width="345" height="266" alt="image" src="https://github.com/user-attachments/assets/31d04a0f-ec71-427f-b205-03890cc7013c" />  

Pour écran JC2432W328  
Si tous c’est bien passer l’écran s’allume avec un message connexion wifi, si l’écran n’affiche pas le premier message, faire un reboot avec le bouton RST  

L’ESP va créer un réseau Wifi (AP) , voir dans les réseaux wifi qui apparaissent sur le PC ce connecter à celui de l’esp : **Afficheur routeur-AP**  

Depuis le navigateur utiliser 192.168.4.1 pour accéder à la page de connexion, rentrer le SSID et la clé Wifi et valider  

Une fois l’ESP connecter au wifi, sur l’écran de démarrage l’adresse IP de l’écran s’affiche quelques secondes pour le modèle **JC2432W328**  

Pour l’ESP32-2432S028 l’IP sera inscrite dans le log de la page de téléchargement dans
Log & Console   

<img width="357" height="201" alt="image" src="https://github.com/user-attachments/assets/9b44e934-22ca-469f-a8e6-633ccc9e00a2" />  


Ce connecter depuis le navigateur avec l’adresse IP afficher sur l’écran.   

Par défaut le code démarre pour le JC2432W328 , si utilisation d’un  ESP32-2432S028 ou ESP32-2432S028R type résistif au démarrage **l’écran sera noir** , il suffit de le renseigner dans le formulaire Choix du modèle d’écran   

<img width="656" height="336" alt="image" src="https://github.com/user-attachments/assets/df317215-55c8-4383-9f4d-0b9010a4ccc0" />  

Et l’écran sera rebooter pour modifier les para de l’écran    

Rotation de l’écran\  

<img width="638" height="123" alt="image" src="https://github.com/user-attachments/assets/286ebac3-5075-4415-af8f-a8b1cd4ba4d4" />    

Pour ESP32-2432S028  à la première mise en service, le calibrage de l’écran est demander, tant que la calibration ne sera pas faite l’écran restera noir.

  
  
<img width="479" height="395" alt="image" src="https://github.com/user-attachments/assets/b284ba2d-1554-4361-bd6d-6dd5abba5df4" />

Il est possible par la suite de lancer une calibration si besoin en touchant le tactile plus de 5 secondes.

**Pas de calibration sur le JC2432W328**

Un lien pour la documentation depuis la page web

<img width="666" height="63" alt="image" src="https://github.com/user-attachments/assets/e4e31045-cad1-4ffb-8021-88575c1719be" />  

**#Météo**

Il est possible d’utiliser 2 modes différent pour avoir la météo

1er Mode par défaut :

Utilisation : Openweathermap

Il faut commencer par récupérer la position GPS de vôtre lieu d’habitation, ensuite il faut obtenir une clé API depuis 
[openweathermap](https://openweathermap.org/api)  

<img width="414" height="321" alt="image" src="https://github.com/user-attachments/assets/63655a0b-0619-41ca-b9fd-009a0676c7e5" />  

et souscrire a l’API One Call API 3,0 (c’est gratuit) ensuite copier la clé pour la rentrer sur la page web de l’Afficheur routeur ainsi que les coordonner GPS et enregistrer , l’ Afficheur va redémarrer pour sauvegarder en dur.

<img width="649" height="455" alt="image" src="https://github.com/user-attachments/assets/c48d2b7e-cdf2-4aca-b94c-4d55ce20e34d" />  

**2e Mode utilisation de Open-météo → météofrance-api**

Cette API n’a pas besoin de clé API et ne remonte pas la ville en relation avec les coordonnées 
Il faut remplir le champ Ville en rapport avec la vôtre et par défaut affiche Paris  

<img width="641" height="37" alt="image" src="https://github.com/user-attachments/assets/646cdca3-850f-471d-9018-6b10957f1d7c" />  



##  MQTT  

Pour le MQTT, l’Afficheur routeur a son propre broker MQTT pour permettre à ceux qui n’ont pas
de serveur domotique type HA, Jeedom de pouvoir récupérer les infos du routeur F1ATB 

Formulaire de l’Afficheur routeur :

<img width="650" height="506" alt="image" src="https://github.com/user-attachments/assets/fa1e0708-07df-46ed-93a0-6db232dd3017" />  

La case en face de Activer MQTT externe est uniquement pour l’utilisation sur un Broker   

distant (domotique) donc ne doit pas être cocher pour une utilisation du Broker embarquer sur l’Afficheur.  

* Serveur :  il faut rentrer l’IP du broker pour ceux qui utilise un Broker distant (domotique)
* Port : est rentrer par défaut
* Utilisateur :  pour broker distant si utiliser (fonction non tester)
* Mot de passe :  pour broker distant si utiliser (fonction non tester)

# $\color{red}{\textsf{Usage du BROKER EMBARQUÉ SUR L'AFFICHEUR-ROUTEUR}}$

* Topic PicoMQTT : il faut rentrer le topic choisi sur le routeur F1ATB et le topic sur l’Afficheur
doit être rempli comme ceci :  Tampon_state attention a ne pas oublier le _state (très important)

<img width="984" height="343" alt="image" src="https://github.com/user-attachments/assets/44327772-4793-4c86-8309-6dd794247f08" />   

Dans Adresse IP Host rentrer l’adresse IP de l’afficheur   
Comment doit être inscrit le topic sur l’afficheur   
<img width="634" height="49" alt="image" src="https://github.com/user-attachments/assets/64030f87-1a30-4af4-be9a-ca63ffe4eb6d" />    

$\color{red}{\textsf{Usage du Broker distant (domotique)}}$  

* Topic extenre subscribe : doit être rempli comme ceci : Tampon/#
* Topic externe exact : doit être rempli comme ceci : Tampon/Tampon_state
<img width="995" height="346" alt="image" src="https://github.com/user-attachments/assets/3f7706b9-9721-4604-b5f5-1ad7faf88a4e" />

**Sur l‘afficheur rentrer dans serveur IP du broker distant**  
<img width="641" height="83" alt="image" src="https://github.com/user-attachments/assets/a656f808-dfc0-4dd7-b0c1-240803987f6e" />  

**Possibilité de recevoir les infos d’un routeur F1ATB esclave.**  
Il suffit de cocher la case Activer Routeur n°2 et remplir le formulaire des topics en fonction si broker de l’afficheur ou broker distant mais différent du routeur maître.  

$\color{red}{\textsf{************    Pour faire simple  ************}}$
**Mqtt de l’afficheur :**  
<img width="634" height="49" alt="image" src="https://github.com/user-attachments/assets/2bebba4a-8c6d-45d9-8288-d18a1ad947f0" />  

<img width="854" height="37" alt="image" src="https://github.com/user-attachments/assets/5a7c1d21-11e4-4fca-84ec-fc61c53476ef" />  

** Mqtt externe (broker distant ou HA)**  

<img width="631" height="71" alt="image" src="https://github.com/user-attachments/assets/3c355887-0769-4c3c-8950-39567a73184d" />  

<img width="859" height="67" alt="image" src="https://github.com/user-attachments/assets/83826c60-b695-44a1-9700-ca832102ca87" />  

Forçage du triac :  

Depuis l’écran, il suffit de glisser le doigt du bas vers le haut pour activer le forçage de 30 mm  
et du haut vers le bas pour arrêter le forçage   

Depuis la domotique pour lancer une marche forcée de 30 min  

<img width="646" height="321" alt="image" src="https://github.com/user-attachments/assets/3c3a0dee-ea41-4027-8aeb-3277a7487ae7" />  


Si utilisation d’un SSR sur routeur maître cocher la case SSR routeur maître  
La case Triac – SSR externe permet si elle est cocher d’avoir sur l’afficheur le pourcentage d’ouverture routeur esclave à la place du routeur maître  

JSY /Shelly EM remonte le tore 2 du JSY ou le canal 1 du shelly EM  en ligne 4  

<img width="661" height="273" alt="image" src="https://github.com/user-attachments/assets/3f77a978-30bd-4b0a-b020-36e0b7c8fa06" />  



## Page PARAMETRES  

<img width="646" height="74" alt="image" src="https://github.com/user-attachments/assets/e29fc8ed-ecc4-4528-b990-380ad0ecca30" />  

Il est possible de remonter sur l’afficheur 3 sondes de température max du routeur F1ATB et de la renommer avec un maximum de 11 caractères.  

<img width="647" height="518" alt="image" src="https://github.com/user-attachments/assets/52d0a713-0778-4a6e-9dd2-fa3d954df3c4" />  

Température 1 canal 0 routeur maître  
Température 2 canal 1 routeur maître  

Température 3 canal 0 routeur esclave 1  
Température 4 canal 1 routeur esclave 1  

Température 5 canal 0 routeur esclave 2  
Température 6 canal 1 routeur esclave 2  


# Paramètre Gestion afficheur  

. Extinction auto, si la case est cocher l’écran s’éteint après 5 minutes si l’écran n’est pas toucher  
. Activer capteur IR, permet à l’écran de s’allumer sur présence et extinction après 5 minute  
    Le capteur IR n’est pas activer par défaut.  

. Affiche tempo, cocher la case pour remonter les couleurs tempo depuis le F1ATB  

. TempoRte, cocher permet d’avoir l’info TempoRte intégrer sur l’afficheur  

. Enphase, cocher la case si le routeur maître est connecter à l’Enphase Envoy  

. Ventilateur, cocher la case si utilisation d’un ventilateur de refroidissement sur le relais 1 du F1ATB  

# OpenDtu  

Pour ceux qui ont OpenDtu   

Activer OpenDtu et rentrer L’IP de vôtre OpenDtu et enregistrer,  l’esp va rebooter.  
La puissance afficher sera < la production > sur la 2e ligne de l’afficheur   

Tempo (ms) permet d’augmenter le temps de demande d’info sur OpenDtu  

* paramètres d’affichage écran  

Permet de renommer les 4 lignes de l’écran.  
nombre de caractère par ligne :  

<img width="652" height="331" alt="image" src="https://github.com/user-attachments/assets/505f465a-d12a-4c44-9316-6b65e9dfa2b2" />  


1er ligne : 14 caractères  
Consommation   

2e ligne : 11 caractères  
Tension ou production  

3e ligne : 9 caractères  
Ouverture Triac ou SSR    

4e ligne : 17 caractères  
Puissance routée  


# Vigilance Météo  

Il suffit de renseigner le département et enregistrer.  
La vigilance sera afficher dans la zone de la météo et informe juste de l’état vigilance du département.  

Cette info provient de :[Vigiscript]( https://www.vigiscript.fr)  

# Programme journalier écran  

Il est activable ou non si pas de besoin  
Permet de pouvoir exemple sur Prog1 allumer l’écran à partir de 5h30 jusqu’à 9h00   
en prog2 de 9h00 a 11h30 afficher l’horloge et idem pour les autres prog3 et 4  
Si dans ex : prog3  rien n’est rentrer l’afficheur tiendra compte du prog2  

<img width="647" height="859" alt="image" src="https://github.com/user-attachments/assets/96643415-f7a9-46c4-83b5-906cb30d7eb4" /> 

Sur le bouton info cela ouvre une popup d’info  
<img width="402" height="354" alt="image" src="https://github.com/user-attachments/assets/8308a0da-002b-438d-97e3-72d72021e68a" />    

**Téléchargement de la configuration de l’afficheur en fichier JSON et possibilité de restaurer la configuration de l’afficheur**  

<img width="636" height="219" alt="image" src="https://github.com/user-attachments/assets/9246c77c-93c9-4d66-bc6d-879fe7cc991d" />  

Possibilité de téléchargé le bin depuis github  

<img width="641" height="196" alt="image" src="https://github.com/user-attachments/assets/dd7bec5f-916d-4011-b94c-8cc6e4c8118b" />  


Le moyen de voir les infos JSON qui arrive des F1ATB sur une page  LOG :  

<img width="1876" height="568" alt="image" src="https://github.com/user-attachments/assets/5e721587-5c0c-478f-a623-ef2296fa0730" />  

Un bouton de Mise à jour du Firmware pour les futures évolutions, la page s’ouvre directement depuis la page web et propose la liste des firmwares disponible.  

Si une nouvelle version est dispo un badge de nouvelle mise à jour s’affiche sur la page web d’accueil   

<img width="280" height="189" alt="image" src="https://github.com/user-attachments/assets/11b40e0a-ae3f-4f2b-9054-46645b3ff2e9" />  

Lors de la mise à jour il faut bien attendre que l’Afficheur redémarre car l’afficheur télécharge le firmware.bin directement de lui même (la mise a jour est indiquer sur l’écran pendant le téléchargement)  

Le bouton CHANGELOG permet de voir les corrections de bug ou ajout de fonction  

# Reset usine , efface toutes les paramétrés et l’esp redémarre

Il sera en mode AP attente de connexion au wifi   

<img width="307" height="139" alt="image" src="https://github.com/user-attachments/assets/deaae7b1-4e4e-499d-969d-edd47872e718" />  


### Résumé du comportement du programmateur horaire (selon options)

| Option PIR    | Prog activé | Écran éteint | Comment ça s’allume ? | Comment ça s’éteint ?           |
| :------------ | :---------: | :---------: | :-------------------- | :------------------------------ |
| **Désactivé** | Oui         | Oui         | Touch uniquement      | Après 5 min (inactivité touch)  |
| **Activé** | Oui         | Oui         | Touch ou PIR          | Après 5 min (touch ou PIR)      |
| **Désactivé** | Non         | Oui         | Touch uniquement      | Après 5 min                     |
| **Activé** | Non         | Oui         | Touch ou PIR          | Après 5 min (touch ou PIR)      |


### OPTIONS DIVERS  

* Possibilité de changer de fuseau horaire
<img width="652" height="188" alt="image" src="https://github.com/user-attachments/assets/2a16f81c-e1f2-4eaa-8e6b-8947a7f5de9a" />

# MQTT DOMOTIQUE  

* Routage global permet de remonter depuis un serveur domotique en MQTT la puissance routé global
  Il faut activer la fonction
  Et rentrer le topic extern routage et le topic externe exact

  <img width="648" height="261" alt="image" src="https://github.com/user-attachments/assets/6e3ddf70-b632-40d5-820f-95a9ed15d015" />

Exemple d'envoi depuis JEEDOM pour ma part   
<img width="1585" height="144" alt="image" src="https://github.com/user-attachments/assets/bb8b435a-97ce-47bf-8469-98156e922a6b" />  

* La production photovoltaïque, idem pour les infos à rentrer en MQTT depuis la domotique
  <img width="643" height="214" alt="image" src="https://github.com/user-attachments/assets/52a80b38-1d55-4660-abdf-0b0c2b750e3e" />
  
* Possibilité de remonter les info d'une batterie toujours en MQTT depuis la domotique et une fois activer affiche un petit bargrahe sur l'écran
 
  <img width="656" height="325" alt="image" src="https://github.com/user-attachments/assets/18f343f5-618b-470c-8e83-cc169f7975a0" />

  <img width="272" height="220" alt="image" src="https://github.com/user-attachments/assets/67f12c76-ca03-425e-8f60-b7b94c441ef5" />

  
## Bargraphe & Radiateur   

Permet d'afficher un icon ballon d'eau chaude et à côté un radiateur (si utiliser sur un routeur esclave)

Permet le choix de la sonde de température pour le ballon  
Pour le radiateur le choix du routeur esclave (possibilité de max 2 esclave en choix)    


<img width="649" height="412" alt="image" src="https://github.com/user-attachments/assets/411b5db8-7d61-49a3-8f88-cb10eb2043e4" />  

<img width="170" height="112" alt="image" src="https://github.com/user-attachments/assets/703b914b-9f35-43b4-ada4-041b739eb021" />    




## Autre option   

* Depuis le prograammateur si mis en : Energie Live
  
  <img width="324" height="255" alt="image" src="https://github.com/user-attachments/assets/8174774c-0d78-43a3-8b90-68dbbd8d502f" />
  


### Telegram  

Il est possible d’utiliser la messagerie Telegram sur l’afficheur et les commandes seront transmisse au routeur par le biais de MQTT.  

Mise en place de Telegram sur le téléphone :  

[TELEGRAM](https://telegram.org/android?setln=fr)  

Pour que votre appareil puisse vous envoyer des notifications, vous devez récupérer deux informations essentielles : le Jeton (Token) et votre ID Utilisateur.  

1. Création du Bot (Obtenir le Token)  
Le "BotFather" est l'outil officiel de Telegram pour créer des bots.  
    1. Ouvrez Telegram et recherchez le contact @BotFather.  
    2. Cliquez sur Démarrer.  
    3. Envoyez la commande : /newbot.  
    4. Suivez les instructions :  
        ◦ Donnez un Nom à votre bot (ex: Mon Alerte ESP32).  
        ◦ Choisissez un Username (doit se terminer par bot, ex: alerte_maison_123_bot).  
    5. Copiez le Token API qui s'affiche (ex: 7123456789:AAF...). C'est ce code que vous devrez coller dans la page de configuration de votre appareil.  

2. Récupérer votre ID Utilisateur (Chat ID)  
L'ID est un numéro unique qui permet au bot de savoir à qui envoyer les messages. Pour des raisons de sécurité, un bot ne peut pas vous parler si vous ne l'avez pas "autorisé" d'abord.  
    1. Recherchez votre propre bot sur Telegram (via l'Username que vous venez de créer).  
    2. Cliquez sur Démarrer ou envoyez-lui n'importe quel message.  
    3. Recherchez maintenant le contact @userinfobot.  
    4. Cliquez sur Démarrer.  
    5. Le bot vous répond avec votre Id (une suite de 9 ou 10 chiffres). Notez ce numéro.  

 3. Configuration de l'appareil  
Une fois ces deux éléments en main :  
    1. Connectez-vous à l'interface web de l’afficheur dans la page Option  
    2. Remplissez les champs :  
        ◦ Bot Token : Collez le jeton du BotFather.  
        ◦ Chat ID : Collez votre ID numérique.  
    3. Enregistrez.  
    4. Depuis telegram sur le bot créer envoyer /status et le bot recevra les commandes disponible, ce sont les même pour l’envoi de commande MQTT  
       
   <img width="150" height="178" alt="image" src="https://github.com/user-attachments/assets/5067d5e2-c283-4db3-a267-694d0de92c10" />  
   
la commande /info renvoi sur le bot    

<img width="195" height="239" alt="image" src="https://github.com/user-attachments/assets/d8133b55-20d2-45ad-9f3e-40fda693154c" />  





















 







