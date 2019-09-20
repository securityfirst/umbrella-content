---
index: 9
title: Orbot & Orfox
---
Orbot & Orfox
---

Navigation Web améliorée pour la confidentialité de vos données sur Android

**Leçon à lire : [Internet](umbrella://communications/the-internet), [Téléphones Mobiles](umbrella://communications/mobile-phones)**  
**Niveau** : Débutant  
**Temps requis** : 15 minutes  
**Publié :** Avril 2018  
**Sources :** Security Planner (Citizen Lab), [Orbot et Orfox](https://securityplanner.org/#/tool/orbot-and-orfox) ; Security in a Box, [ORBOT POUR ANDROID](https://securityinabox.org/fr/guide/orbot/android/), Le Projet Guardian, [Orbot v16 : un tout nouveau look, plus facile à utiliser !](https://guardianproject.info/2018/01/05/orbot-v16-a-whole-new-look-and-easier-to-use/)  

**En utilisant Orbot et Orfox ensemble, vous obtiendrez :**
- La possibilité de dissimuler votre identité en ligne aux sites Internet et autres services lors de l’utilisation de certaines applications Android.  
- La possibilité de dissimuler vos activités de navigation lorsque vous utilisez Orfox.  
- La possibilité de contourner la censure sur Internet et le filtrage en ligne lors de l’utilisation d’Orfox.  

**Téléchargement :** [Orbot](https://play.google.com/store/apps/details?id=org.torproject.android) et [Orfox](https://play.google.com/store/apps/details?id=info.guardianproject.orfox) dans la boutique Google Play.  
**Configuration requise :**  Varie selon les appareils (Orbot) ; Android 4.0.3 et ultérieure (Orfox)   
**Version utilisé dans ce guide** : Version 16 (Orbot) Fennec-52.7.3esr/TorBrowser-7.5.3/Orfox-1.5.2-RC-1 (Orfox)   
**Licence** : FOSS (primairement GPLv2)

# 1. Introduction 

Orbot permet à d’autres applications sur des appareils Android d’utiliser Internet de manière plus sécurisée via le Réseau Tor. (En savoir plus sur [**Tor**](umbrella://communications/the-internet/advanced).) Orfox est une version du navigateur Tor pour Android qui utilise Orbot pour se connecter au Réseau Tor.

N’oubliez pas que si vous utilisez Orfox pour revenir à un contenu que vous avez déjà créé sans utiliser Orfox, comme un article de blog, le site hébergeant le contenu connaîtra toujours votre emplacement réel.

Si vous souhaitez renforcer l’anonymat lors de l’utilisation d’Orfox :

*   N’accédez jamais à des comptes créés sous votre vrai nom.
*   Ne donnez jamais vos données personnelles.
*   Évitez de faire des choses que vous faites lorsque vous n’essayez pas d’être anonyme.


# 2. Installation et configuration de Orbot

## 2.1 Installation de Orbot

**Étape 1 :** Sur votre appareil Android, **téléchargez** et **installez** l’application à partir du [Google Play store](https://play.google.com/store/apps/details?id=org.torproject.android) en appuyant sur INSTALLER.

![](orbot-and-002.png)

**Note :** **Orbot** peut également être téléchargé à partir d’une boutique tierce [F-Droid](https://guardianproject.info/fdroid/).

## 2.2 Configuration de Orbot

**Étape 1 :** Cliquez sur **Ouvrir.**

![](orbot-and-005.png)

**Étape 2 :** **Faites glisser** à travers les écrans d’accueil de l’assistant d’installation ou appuyez sur la flèche Suivant.

![](orbot-and-006.png) ![](orbot-and-007.png)

**Étape 3 :** Si votre accès au réseau Tor peut être bloqué, vous devrez peut-être utiliser un intermédiaire.

![](orbot-and-009.png)  

![](orbot-and-010.png)

Si vous n’êtes pas certain d’avoir besoin d’un intermédiaire, essayez sans celle-ci d’abord. Pour en savoir plus sur les passerelles, lisez *Configuration avancée d’Orbot : Utilisez un intermédiaire Tor* ci-dessous.

**Étape 4 :** Si vous souhaitez accéder à une application bloquée, utilisez Orbot en tant que VPN (réseau privé virtuel) en cliquant sur **Choisir applications**.

![](orbot-and-008.png)

Sélectionnez les applications individuelles que vous souhaitez utiliser avec **Orbot** et cliquez sur *OK*.

> "Plutôt que de promouvoir une sorte d’auto-magie appelée "autoriser Tor pour tout mon appareil", nous souhaitons nous concentrer sur les moyens de permettre à des applications spécifiques de passer par Tor, de manière à garantir une plus grande sécurité." — Le Projet Guardian, [27 octobre 2017](https://guardianproject.info/2017/10/27/no-more-root-features-in-orbot-use-orfox-vpn-instead/)

Notez que de nombreuses applications, telles que celles pour lesquelles vous devez vous connecter, porteront atteinte à votre anonymat, même si le trafic Internet est tunnellisé via Orbot. Cette étape vous aidera si un pare-feu ou un filtre bloque une application individuelle, mais ne vous rend pas anonyme.

![](orbot-and-011.png)

![](orbot-and-012.png)

Lorsque vous avez terminé la configuration, l’écran **Orbot** désactivé apparaît.

![](orbot-and-013.png)

# 3. Commencer à utiliser Orbot

**Étape 1 :** Touchez l’icône Orbot grise au centre de l’écran jusqu’à ce qu’elle devienne jaune.

![](orbot-and-014.png) 

**Étape 2 :** Lorsqu’il se connecte, Orbot devient vert.

![](orbot-and-015.png) 

**Étape 3 :** Touchez l’icône verte jusqu’à ce qu’elle devienne grise pour vous déconnecter, ou cliquez sur l’icône de menu en haut à droite de l’écran et sélectionnez Quitter pour quitter l’application.

![](orbot-and-019.png)

**Étape 4 :** Appuyez sur *Global (Auto)* pour sélectionner une liste d’emplacements d’où peut provenir votre trafic Internet.

![](orbot-and-022.png)

**Étape 5.** *Activez* le mode VPN pour accéder aux applications répertoriées en canalisant leur trafic Internet via Orbot. Ajoutez d’autres applications à la liste en cliquant sur *Applications compatibles avec Tor* au bas de l’écran.

# 4. Configuration avancée Orbot : Utiliser l’Intermédiaire Tor

Si l’accès à Tor est restreint ou si vous souhaitez dissimuler le fait que vous utilisez Tor, vous pouvez configurer Orbot pour qu’il utilise des *intermédiaires*. En savoir plus sur les intermédiaires dans le guide [Tor pourLINUX](umbrella://tools/tor/s_tor-for-linux.md).

**Étape 1 :** Appuyez sur l’icône du menu en haut à droite, puis sélectionnez *Paramètres*. Faites défiler jusqu’à *Intermédiaires.* Cochez la case à côté de *Utiliser des Intermédiaires.*

![](orbot-and-025.png)

**Étape 2 :** Si vous connaissez *l’adresse IP* de *l’intermédiaire* que vous souhaitez utiliser, appuyez sur *Adresse IP et le port des intermédiaires*. Entrez l’adresse IP et appuyez sur *OK*.

![](/media/orbot-and-026.png)

**Étape 3 :** Redémarrez **Orbot** pour commencer à utiliser *l’intermédiaire*.

Vous pouvez en apprendre plus sur les intermédiaires sur le [site Web du Projet Tor](https://bridges.torproject.org/).


# 5. Installation de Orfox

**Étape 1 :** Sur votre appareil Android, **téléchargez** et **installez l’application** à partir du [Google Play store](https://play.google.com/store/apps/details?id=info.guardianproject.orfox).

**Note :** **Orfox** peut également être téléchargé à partir de la boutique tierce [F-Droid](https://guardianproject.info/fdroid/).

**Étape 2 :** Pour ouvrir Orfox, **tapez** l’icône de l’application.

**Orfox** vous donnera l’option de vous connecter à _https://check.torproject.org_, afin de vous assurer que sa connexion au réseau **Tor** fonctionne. S’il peut se connecter, vous verrez un message vous indiquant que votre _navigateur est configuré pour utiliser Tor_. Si **Orfox** ne peut pas se connecter au site Web, un message d’erreur apparaît dans le navigateur. Si cela se produit, vérifiez qu’Orbot est en cours d’exécution.

**Étape 3 :** Pour naviguer sur les sites Web, **tapez** la zone en haut de l’écran et tapez l’adresse que vous voulez visiter. Appuyez sur *Aller* sur le clavier à l’écran.

# 6. Effacer votre historique de navigation Orfox

**Étape 1 :** Pour effacer manuellement votre historique de navigation et votre cache, et masquer les sites Web visités dans Orfox, tapez sur l’icône du menu principal avec trois points dans le coin supérieur droit, puis sur *Paramètres*.

**Étape 2 :** Appuyez sur *Effacer les données privées,* puis *EFFACER LES DONNÉES,* pour supprimer les données des catégories répertoriées.

Note : Lorsque vous définissez cette option, vous ne pourrez pas appuyer sur le bouton Précédent pour afficher les pages Web que vous avez déjà visitées.

**Étape 3 :** Retournez au menu *Paramètres* et sélectionnez *Confidentialité.* Sélectionnez _Supprimez les données privées à la sortie_ pour effacer automatiquement les données privées lorsque vous quitterez l’application via le menu principal.

Note : La sélection de *Nouvel onglet privé* dans le menu principal empêchera également Orfox d’enregistrer l’historique de navigation. Les fichiers que vous téléchargez et les pages Web que vous avez ajoutées aux favoris seront toujours enregistrés sur votre appareil.

# 7. Personnaliser la sécurité de votre navigateur

Orfox inclut une fonctionnalité de curseur de sécurité qui vous permet de choisir entre les paramètres de sécurité Standard, Plus Sécurisé et Très Sécurisé. Tapez sur l’icône du menu principal avec trois points dans le coin supérieur droit, puis *Paramètres Orfox*. Les paramètres les plus sûrs et très sécurisés entraîneront la rupture de certaines fonctionnalités du site Web, mais vous serez moins exposé aux vulnérabilités que les pirates peuvent exploiter pour vous attaquer.
