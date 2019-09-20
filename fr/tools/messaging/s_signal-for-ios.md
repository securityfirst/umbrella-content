---
index: 17
title: Signal pour iOS
---
Signal pour iOS
=========================

Messages Sécurisés

**Leçon à lire : [Envoi d’un message](umbrella://communications/sending-a-message)**  
**Niveau : Débutant-Intermédiaire**  
**Temps requis : 15-20 minutes**  
**Publié : Avril 2018 (certaines images datent de versions antérieures)**  
**Sources : FFÉ, Autodéfense contre la surveillance [Guide pratique : utiliser Signal pour iOS](https://ssd.eff.org/fr/module/guide-pratique-utiliser-signal-pour-ios) ; Security in a Box [SIGNAL POUR ANDROID](https://securityinabox.org/fr/guide/signal/android/).**  

**En utilisant Signal, cela vous donnera :**

- La possibilité d’envoyer des messages de groupe, texte, image et vidéo chiffrés de bout en bout et d’avoir des conversations téléphoniques chiffrées avec d’autres utilisateurs de Signal.

**Emplacement de téléchargement** : [Application Apple Store](https://itunes.apple.com/us/app/signal-private-messenger/id874139669?mt=8)

**Configuration requise** : iOS 8.0 ou version ultérieure. Compatible avec iPhone, iPad et iPod touch.
(vous devez avoir un compte Apple qui sera lié à l’installation de l’application).

**Version utilisée dans ce guide** : Signal iOS 2.8.1

**Licence :** GPLv3

**Lectures complémentaires** :

*   [http://support.whispersystems.org/](http://support.whispersystems.org/)
*   [https://signal.org/blog/standalone-signal-desktop/](https://signal.org/blog/standalone-signal-desktop/)
*   [https://whispersystems.org/blog/signal-video-calls/](https://whispersystems.org/blog/signal-video-calls/)

introduction
-----------------
Signal est un logiciel gratuit et à code source ouvert pour Android, iOS et Ordinateur qui utilise un chiffrement de bout en bout, permettant aux utilisateurs d’envoyer des messages de groupe, texte, image et vidéo chiffrés de bout en bout, ainsi que des conversations téléphoniques chiffrées entre les utilisateurs de Signal.

Bien que Signal utilise des numéros de téléphone comme contacts, les appels et les messages chiffrés quant à eux utilisent en réalité votre connexion de données ; par conséquent, les deux parties à la conversation doivent avoir un accès Internet sur leurs appareils mobiles. De ce fait, les utilisateurs de Signal n’engagent pas de frais SMS et MMS pour ce type de conversation.

Sous Android, Signal peut remplacer votre application de messagerie texte par défaut. Il est donc toujours possible d’envoyer des messages SMS non chiffrés.

Note :
* Signal empêche les autres d’accéder au contenu de vos messages et appels vocaux, mais ne cache pas le fait que vous envoyez des messages ou que vous passez des appels vocaux chiffrés. Dans certains pays, des outils de chiffrement tels que Signal peuvent attirer l’attention ou enfreindre les contraintes légales.
* Open Whisper Systems, les fabricants de Signal, utilise l’infrastructure d’autres sociétés (Apple sur iOS) pour envoyer des alertes à ses utilisateurs lorsqu’ils reçoivent un nouveau message. Cela signifie que certaines métadonnées, ou des informations sur les destinataires et la date de réception des messages, peuvent être transmises à ces sociétés.

Installation de Signal – Private Messenger sur votre iPhone
----------------------------------------------------------------------

### Étape 1 : Téléchargez et Installez Signal – Private Messenger

Sur votre appareil iOS, accédez à l’App Store et recherchez « Signal ». Sélectionnez [Signal – Private Messenger](https://itunes.apple.com/us/app/signal-private-messenger/id874139669?mt=8). par Open Whisper Systems.

Appuyez sur « OBTENIR » pour télécharger l’application, puis « INSTALLER ». Vous serez peut-être invité à entrer votre ID Apple. Une fois téléchargé, cliquez sur « OUVRIR » pour lancer l’application.

### Étape 2 : Inscrivez-vous et Vérifiez votre Numéro de Téléphone

Vous verrez désormais l’écran suivant. Entrez votre numéro de téléphone mobile et appuyez sur «Vérifier Ce Périphérique».

![](tool_signalios_resized000.png)

![](tool_signalios_resized001.png)

Afin de vérifier votre numéro de téléphone, vous recevrez un SMS avec un code à six chiffres. Vous serez désormais invité à entrer ce code, puis à taper « Soumettre le Code de Vérification ».

![](tool_signalios_resized002.png)

Une fois ce processus terminé, Signal demandera l’accès à vos contacts. Appuyez sur «Continuer».

![](tool_signalios_resized003.png)

Signal demandera alors l’autorisation de vous envoyer des notifications. Appuyez sur «OK».

![](/tool_signalios_resized004.png)

Utilisation de Signal
------------------------------

Pour pouvoir utiliser Signal, la personne que vous appelez doit avoir Signal d’installer. Si vous essayez d’appeler ou d’envoyer un message à une personne utilisant l’application Signal sans que l’une des applications susmentionnées soit installée, l’application vous demandera si vous souhaitez l’inviter par SMS, mais ne vous permettra pas de passer votre appel ou d’envoyer un message depuis l’application.

Signal vous fournit une liste des autres utilisateurs de Signal dans vos contacts. Pour ce faire, les données représentant les numéros de téléphone de votre liste de contacts sont téléchargées sur les serveurs de Signal, bien que ces données soient supprimées presque immédiatement.

Comment Envoyer un Message Chiffré
--------------------------------------------------

Notez qu’Open Whisper Systems, le fabricant de Signal, utilise l’infrastructure d’autres sociétés pour envoyer des alertes à ses utilisateurs lorsqu’ils reçoivent un nouveau message. Il utilise Google sur Android et Apple sur iPhone. Cela signifie que les informations concernant les destinataires des messages et leur date de réception risquent de fuir vers ces sociétés.

Pour commencer, appuyez sur l’icône de composition dans le coin supérieur droit de l’écran.

![](tool_signalios_resized005-compose.png)

Vous verrez une liste de tous les utilisateurs Signal enregistrés dans vos contacts.

![](tool_signalios_resized008.png)

Lorsque vous appuyez sur un contact, vous êtes amené à l’écran de messagerie texte de celui-ci. À partir de cet écran, vous pouvez envoyer des messages texte, photo ou vidéo chiffrés de bout en bout.

![](tool_signalios_resized010.png)

### Comment Initier un Appel Chiffré

Pour initier un appel chiffré, sélectionnez le contact que vous désirez appeler puis appuyez sur l’icône du téléphone.

![](tool_signalios_resized010-phone.png)

À ce stade, Signal peut demander l’autorisation d’accéder au microphone. Appuyez sur « OK ».

![](tool_signalios_resized011.png)

Une fois qu’un appel est établi, votre appel est chiffré.

### Comment Initier un Appel Vidéo Chiffré

Pour passer un appel vidéo chiffré, appelez simplement une personne de la manière suivante :

![](tool_signalandroid_initial_video_screen.png)

et appuyez sur l’icône de la caméra vidéo. Vous devrez peut-être autoriser Signal à accéder à la vidéo à partir de votre caméra. Cela partage votre vidéo avec votre ami (votre ami devra peut-être faire la même chose).


### Comment Démarrer une Discussion de Groupe Chiffrée

Vous pouvez envoyer un message de groupe chiffré en appuyant sur l’icône de composition située dans le coin supérieur droit de l’écran (le carré avec un crayon pointant vers le centre), puis en appuyant sur l’icône avec trois chiffres situé au même endroit.

![](tool_signalios_resized005-compose.png)

![](tool_signalios_resized008-group.png)

Sur l’écran suivant, vous pourrez nommer le groupe et y ajouter des participants. Après avoir ajouté des participants, vous pouvez appuyer sur l’icône « + » dans le coin supérieur droit de l’écran.

![](tool_signalios_resized023-plus.png)

Cela initiera la discussion de groupe.

![](tool_signalios_resized024.png)

Si vous souhaitez modifier le nom du groupe, ou ajouter ou supprimer des participants, vous pouvez le faire à partir de l’écran de discussion en appuyant sur l’icône de débordement (les trois points dans le coin supérieur droit de l’écran) et en sélectionnant « Modifier le groupe ».

### Comment Vérifier vos Contacts

À ce stade, vous pouvez vérifier l’authenticité de la personne avec laquelle vous parlez, afin de vous assurer que sa clé de chiffrement n’a pas été falsifiée ou remplacée par la clé d’une autre personne lorsque votre application l’a téléchargée (un processus appelé vérification de clé). La vérification est un processus qui a lieu lorsque vous êtes physiquement en présence de la personne à qui vous parlez.

Tout d’abord, ouvrez l’écran où vous pouvez envoyer un message à votre contact, comme décrit ci-dessus. À partir de cet écran, appuyez sur le nom de votre contact en haut de l’écran.

![](tool_signalios_resized010-name.png)

À partir de l’écran suivant, appuyez sur "Vérifier les Numéros de Sécurité".

![](tool_signalios_resized015-verify.png)

Vous allez désormais être amené à un écran qui affiche un code QR et une liste de « numéros de sécurité ». Ce code sera unique pour chaque contact différent avec lequel vous conversez. Faites en sorte que vos contacts accèdent à l’écran correspondant pour discuter avec eux, afin qu’ils aient également un code QR affiché sur leur écran.

![](tool_signalios_resized016.png)

De retour sur votre appareil, appuyez sur « Scanner le Code ». À ce stade, Signal peut demander la permission d’accéder à la caméra. Appuyez sur « OK ».

![](tool_signalios_resized017.png)

Vous pourrez désormais utiliser la caméra pour scanner le code QR affiché sur l’écran de votre contact. Alignez alors votre caméra sur le code QR :

![](tool_signalios_resized018.png)

Espérons que votre appareil photo scannera le code à barres et affichera le dialogue « Numéros de Sécurité Vérifiés ! » suivant :

![](tool_signalios_resized019.png)

Cela indique que vous avez vérifié votre contact avec succès. Si à la place, votre écran ressemble à ceci, quelque chose ne va pas :

![](tool_signalios_resized020.png)

Vous voudrez peut-être éviter de discuter de sujets sensibles avant d’avoir vérifié les clés avec cette personne.

_Note pour les utilisateurs expérimentés : L’écran affichant votre code QR comporte également une icône permettant de partager votre numéro de sécurité_ _dans le coin supérieur droit. La vérification en personne est la méthode recommandée, mais vous avez peut-être déjà authentifié votre contact à l’aide d’une autre application sécurisée, telle que PGP. Puisque vous avez déjà vérifié votre contact, vous pouvez utiliser en toute sécurité la confiance établie dans cette application pour vérifier__les numéros au sein de Signal, sans avoir à vous trouver physiquement en présence de votre contact. Dans ce cas, vous pouvez partager votre numéro de sécurité avec cette application en appuyant sur l’icône « partager » et envoyer à votre contact votre numéro de sécurité._

### Disparition des Messages

Signal a une fonctionnalité appelée « disparition de messages » qui garantit que les messages seront supprimés de votre appareil et de l’appareil de votre contact un certain temps après leur affichage. Pour permettre la disparition des messages lors d’une conversation, ouvrez l’écran dans lequel vous pouvez envoyer un message à votre contact. Sur cet écran, appuyez sur le nom du contact en haut de l’écran, puis appuyez sur le menu déroulant situé à côté de « Disparition des Messages ».

![](tool_signalios_resized015-slider.png)

Un menu déroulant apparaîtra vous permettant de choisir la rapidité avec laquelle les messages disparaîtront :

![](tool_signalios_resized021.png)

Après avoir sélectionné une option, vous pouvez appuyer sur l’icône « < » dans le coin supérieur gauche de l’écran et vous devriez voir l’information dans la conversation indiquant que la « disparition des messages » a été activé.

![](tool_signalios_resized022.png)

Vous pouvez désormais envoyer des messages avec l’assurance qu’ils seront supprimés après le délai choisi.
