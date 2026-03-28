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

Page de téléchargement  

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

Pour ESP32-2432S028  à la première mise en service, le calibrage de l’écran est demander, tant que la calibration ne sera pas faite l’écran restera noir.\

  
  
<img width="479" height="395" alt="image" src="https://github.com/user-attachments/assets/b284ba2d-1554-4361-bd6d-6dd5abba5df4" />

Il est possible par la suite de lancer une calibration si besoin en touchant le tactile plus de 5 secondes.\

**Pas de calibration sur le JC2432W328**\

Un lien pour la documentation depuis la page web\ 

<img width="666" height="63" alt="image" src="https://github.com/user-attachments/assets/e4e31045-cad1-4ffb-8021-88575c1719be" />  

**#Météo**\

Il est possible d’utiliser 2 modes différent pour avoir la météo\

1er Mode par défaut :\

Utilisation : Openweathermap\

Il faut commencer par récupérer la position GPS de vôtre lieu d’habitation, ensuite il faut obtenir une clé API depuis :\
[openweathermap](https://openweathermap.org/api)  

<img width="414" height="321" alt="image" src="https://github.com/user-attachments/assets/63655a0b-0619-41ca-b9fd-009a0676c7e5" />  

et souscrire a l’API One Call API 3,0 (c’est gratuit) ensuite copier la clé pour la rentrer sur la page web de l’Afficheur routeur ainsi que les coordonner GPS et enregistrer , l’ Afficheur va redémarrer pour sauvegarder en dur.\

<img width="649" height="455" alt="image" src="https://github.com/user-attachments/assets/c48d2b7e-cdf2-4aca-b94c-4d55ce20e34d" />  

**2e Mode utilisation de Open-météo → météofrance-api**\

Cette API n’a pas besoin de clé API et ne remonte pas la ville en relation avec les coordonnées\ 
Il faut remplir le champ Ville en rapport avec la vôtre et par défaut affiche Paris  

<img width="641" height="37" alt="image" src="https://github.com/user-attachments/assets/646cdca3-850f-471d-9018-6b10957f1d7c" />  



##  MQTT \ 

Pour le MQTT, l’Afficheur routeur a son propre broker MQTT pour permettre à ceux qui n’ont pas\
de serveur domotique type HA, Jeedom de pouvoir récupérer les infos du routeur F1ATB \

Formulaire de l’Afficheur routeur :\

<img width="650" height="506" alt="image" src="https://github.com/user-attachments/assets/fa1e0708-07df-46ed-93a0-6db232dd3017" />  


                                              















