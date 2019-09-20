---
index: 14
title: Psiphon
---
# GUIDE D’UTILISATION DE PSIPHON

Contournement de la Censure

**Leçon à lire : [Internet](umbrella://communications/the-internet)**   
**Téléchargement :** [Google Play](https://play.google.com/store/apps/details?id=com.psiphon3.subscription), [Apple App Store](https://itunes.apple.com/fr/app/psiphon/id1276263909?ls=1&mt=8) ou [Psiphon](https://psiphon.ca/fr/download.html).  
**Configuration requise :** Une connexion Internet, et un appareil opérant Windows, Android 2.3 ou version récente, ou iOS 10.2 ou version récente (iOS 8 pour le navigateur Psiphon)    
**Licence :** Logiciel à code source ouvert gratuit ; GNU GPL Version 3  
**Niveau :** Débutant  
**Autres lectures :** [https://psiphon.ca/fr/user-guide.html](https://psiphon.ca/fr/user-guide.html)  
**Temps requis :** 5 minutes  

**L’utilisation de Psiphon vous donnera :**
- La capacité de contourner en toute sécurité la censure d’Internet pour accéder à des sites Web bloqués et à des applications à l’aide d’un VPN (réseau privé virtuel).

### 1. Avant de commencer

- Faites attention aux copies malicieuse de Psiphon et téléchargez-le uniquement à partir de sources officielles.

![image](tool_psiphon10.png)
![image](tool_psiphon11.png)
![image](tool_psiphon12.png)

- Psiphon est principalement conçu comme un outil d’évasion de la censure, plutôt que comme un garant de l’anonymat.
- Psiphon étant basé sur un VPN, il est capable de transmettre par mandataire tout votre trafic Internet, pas seulement les sites Web.
- Si vous n’avez pas activé activement Psiphon, vous n’utilisez pas le VPN. (Il ne suffit pas seulement d’avoir Psiphon sur votre ordinateur.)
- Les pages Web peuvent se charger plus lentement lors de l’utilisation d’un VPN. Ceci est normal car le navigateur ne se connecte pas directement au site Web.
- Certains services VPN payants peuvent être plus rapides que ceux gratuits tels que Psiphon, mais vous devez être prudent avant de faire confiance à une entreprise avec vos informations, car elles pourraient être partagées avec les autorités ou vendues à d’autres entreprises.
- Le trafic entre votre appareil et le serveur VPN est chiffré. Cependant, le trafic entre ce serveur et un site Web autre que HTTPS ne sera *pas* chiffré. (Il en va de même pour les autres services Internet, par exemple lors de la connexion avec Outlook ou Thunderbird à un fournisseur de messagerie non SSL.)

### 2. Psiphon pour Android

Téléchargez Psiphon Pro à partir de la boutique [Google Play](https://play.google.com/store/apps/details?id=com.psiphon3.subscription). 

Si vous n’avez pas accéder à la boutique Google Play, sélectionnez Psiphon Pro pour Android sur la [page de téléchargement](https://psiphon.ca/fr/download.html?10Years) officielle de Psiphon . (Vérifiez que le fichier téléchargé est authentique [ici](https://psiphon.ca/fr/faq.html#authentic-android).) Vous aurez peut-être besoin d’[activer l’installation alternative](https://psiphon.ca/fr/faq.html#android-enable-sideloading).)

Ouvrez l’application et cliquez sur *commencer* pour vous connecter au réseau Psiphon.

![image](tool_psiphon5.png)

Sélectionnez le mode Ensemble de Périphérique pour canaliser toutes les applications via Psiphon. (Cette option peut ne pas être disponible pour les anciennes versions d’Android. Vous pouvez utiliser le navigateur dédié à Psiphon, mais seule l’activité en ligne effectuée dans le navigateur utilise Psiphon. D’autres applications se connectent à l’aide de votre connexion Internet habituelle.)

![image](tool_psiphon6.png)

Le Psiphon *P* dans le coin supérieur gauche de votre appareil indique que Psiphon est en cours d’exécution.

### 3. Psiphon pour Windows

Téléchargez la dernière version de Psiphon pour Windows [ici](https://psiphon.ca/fr/download.html). Vérifiez que le fichier téléchargé est authentique [ici](https://psiphon.ca/fr/faq.html#authentic-windows).)

Lorsque vous exécutez le programme, une invite de sécurité indiquant que ce programme est un produit légitime de Psiphon Inc. devrait apparaître.

Psiphon se connecte automatiquement lorsque vous l’exécutez. Pendant la connexion, une icône en rotation s’affiche. La connexion au serveur Psiphon est établie lorsque l’icône en forme de coche verte est affichée.

Quand vous fermez le programme, Psiphon se déconnecte automatiquement. Vous pouvez aussi cliquer sur l’icône pour activer/désactiver la connexion.

### 4. Psiphon pour iOS

Téléchargez Psiphon à partir de l’[Apple App store](https://itunes.apple.com/fr/app/psiphon/id1276263909?ls=1&mt=8). 

Ouvrez l’application, puis cliquez sur le bouton gris *Déconnecté*

![image](tool_psiphon7.png)

Le bouton devient rouge lors de la connexion et vert lorsqu’il est connecté.

![image](tool_psiphon8.png) ![image](tool_psiphon9.png)

Une icône "VPN" dans le coin supérieur gauche de votre appareil indique que Psiphon est en cours d’exécution, ce qui signifie que d’autres applications accéderont à Internet via Psiphon.

Pour utiliser le navigateur dédié Psiphon pour iOS, un [téléchargement](https://itunes.apple.com/fr/app/psiphon-browser/id1193362444?mt=8) distinct  est nécessaire, mais il fonctionne sous iOS 8 ou une version ultérieure. L’application principale Psiphon nécessite iOS 10.2 ou une version ultérieure. Si vous utilisez le navigateur, seule l’activité en ligne effectuée dans le navigateur utilisera Psiphon. D’autres applications se connecteront en utilisant votre connexion Internet habituelle.
