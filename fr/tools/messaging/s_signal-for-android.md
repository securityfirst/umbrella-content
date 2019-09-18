---
index: 16
title: Signal pour Android
---
Signal pour Android
==============================
Messages Sécurisés

**Leçon à lire : [Envoi d’un message](umbrella://communications/sending-a-message)**  
**Niveau**: Débutant-Intermédiaire  
**Temps requis**: 15-20 minutes  
**Publication :** Avril 2018  (certaines images datent d’une version antérieure)  
**Sources :** FFÉ, Autodéfense contre la surveillance [Comment : Utiliser Signal pour Android](https://ssd.eff.org/fr/module/how-use-signal-android); Security in a Box [SIGNAL POUR ANDROID](https://securityinabox.org/fr/guide/signal/android/).

**En utilisant Signal, cela vous donnera :**

- La possibilité d’envoyer des messages de groupe, texte, image et vidéo chiffrés de bout en bout et d’avoir des conversations téléphoniques chiffrées avec d’autres utilisateurs de Signal.

**Téléchargement** : [Google Play Store](https://play.google.com/store/apps/details?id=org.thoughtcrime.securesms).

**Configuration requise**: Android 2.3 et plus récentes, avec les services Google Play (vous devez avoir un compte Google qui sera lié à l’installation de l’application).

**Version utilisée dans ce guide**: Signal 3.31.3

**Licence :** GPLv3

**Lectures complémentaires** :

*   [http://support.whispersystems.org/](http://support.whispersystems.org/)
*   [https://signal.org/blog/standalone-signal-desktop/](https://signal.org/blog/standalone-signal-desktop/)
*   [https://whispersystems.org/blog/signal-video-calls/](https://whispersystems.org/blog/signal-video-calls/)


introduction
-----------------
Signal est un logiciel gratuit et à code source ouvert pour Android, iOS et Ordinateur qui utilise un chiffrement de bout en bout, permettant aux utilisateurs d’envoyer des messages de groupe, texte, image et vidéo chiffrés de bout en bout, ainsi que des conversations téléphoniques chiffrées entre les utilisateurs de Signal.

Bien que Signal utilise les numéros de téléphone comme contacts, les appels et les messages chiffrés quant à eux utilisent en réalité votre connexion de données ; par conséquent, les deux parties à la conversation doivent avoir un accès Internet sur leurs appareils mobiles. De ce fait, les utilisateurs de Signal n’engagent pas de frais SMS et MMS pour ce type de conversation.

Sous Android, Signal peut remplacer votre application de messagerie texte par défaut. Il est donc toujours possible d’envoyer des messages SMS non chiffrés.

Note :
* Signal empêche les autres d’accéder au contenu de vos messages et appels vocaux, mais ne cache pas le fait que vous envoyez des messages ou que vous passez des appels vocaux chiffrés. Dans certains pays, des outils de chiffrement tels que Signal peuvent attirer l’attention ou enfreindre les contraintes légales.
* Open Whisper Systems, les fabricants de Signal, utilise l’infrastructure d’autres sociétés (Google sur Android) pour envoyer des alertes à ses utilisateurs lorsqu’ils reçoivent un nouveau message. Cela signifie que certaines métadonnées, ou des informations sur les destinataires et la date de réception des messages, peuvent être transmises à ces sociétés.

Installation de Signal sur votre téléphone Android 
----------------------------------------
### Étape 1 : Téléchargez et Installez Signal

Sur votre appareil Android, accédez à Google Play Store et recherchez "Signal". Sélectionnez [Signal par Open Whisper Systems](https://play.google.com/store/apps/details?id=org.thoughtcrime.securesms).

Une fois que vous avez appuyé sur "Installer", vous verrez une liste des fonctions Android auxquelles Signal doit pouvoir accéder pour pouvoir fonctionner. Cliquez sur "Accepter".

Une fois le téléchargement de Signal terminé, appuyez sur "Ouvrir" pour lancer l’application.

### Étape 2 : Inscrivez-vous et Vérifiez votre Numéro de Téléphone

Vous verrez maintenant l’écran suivant. Entrez votre numéro de téléphone mobile et appuyez sur "Enregistrer".

![](tool_signalandroid_resized000_0.png)

Il vous sera ensuite demandé de vérifier votre numéro de téléphone. Cliquez sur "Continuer".

![](tool_signalandroid_resized001_0.png)

Afin de vérifier votre numéro de téléphone, vous recevrez un SMS avec un code à six chiffres. Étant donné que Signal peut accéder à vos messages texte SMS, il reconnaît automatiquement la réception du code et termine votre inscription.

![](tool_signalandroid_resized002_0.png)

Une fois ce processus terminé, il vous sera demandé si vous souhaitez que Signal soit votre application SMS par défaut. Cela peut être utile pour garder tous vos messages au même endroit. Sachez que si vous acceptez ceci, les messages envoyés aux contacts sur lesquels Signal n’est pas installé (même si vous les envoyez depuis l’application Signal) ne seront pas cryptés.

 

Utilisation de Signal
------------------------------

Pour pouvoir utiliser Signal, votre correspondant doit être équipé de Signal. Si vous essayez d’envoyer un message à une personne utilisant l’application Signal sans que Signal soit installé sur l’appareil de ce dernier, un message texte standard non chiffré sera envoyé. Si vous essayez d’appeler la personne, il passera un appel téléphonique standard.

Signal vous fournit une liste des autres utilisateurs de Signal dans vos contacts. Pour ce faire, les données représentant les numéros de téléphone de votre liste de contacts sont téléchargées sur les serveurs de Signal, bien que ces données soient supprimées presque immédiatement.

### Comment Envoyer un Message Chiffré

Pour commencer, appuyez sur l’icône de composition dans le coin supérieur droit de l’écran.

![](tool_signalandroid_resized003_0.png)

Vous verrez une liste de tous les utilisateurs de Signal enregistrés dans vos contacts. Vous pouvez également entrer le numéro de téléphone d’un utilisateur de Signal qui ne figure pas dans vos contacts. Lorsque vous sélectionnez un contact, vous êtes amené à l’écran de messagerie texte de votre contact. Notez que pour les utilisateurs de Signal, le texte "Envoyer Message Signal" apparaîtra - cela signifie que le message sera crypté. Sur cet écran, l’icône "téléphone" située dans le coin supérieur droit de l’écran indique que vous pouvez également émettre un appel vocal crypté à l’aide de Signal. À partir de cet écran, vous pouvez envoyer des messages texte, photo ou vidéo chiffrés de bout en bout.

![](tool_signalandroid_resized006.png)

Pour les utilisateurs sur lesquels Signal n’est pas installé, le texte "Envoyer SMS non sécurisé" apparaît, ce qui n’enverra pas le message avec chiffrement. Sur cet écran, l’icône "téléphone" dans le coin supérieur droit de l’écran fera un appel téléphonique normal et non chiffré.

![](tool_signalandroid_resized004_0.png)

### Comment Initier un Appel Chiffré

Pour initier un appel chiffré à un contact, sélectionnez ce contact puis appuyez sur l’icône téléphone. Vous saurez que le contact peut accepter les appels de Signal si vous voyez une petite icône représentant un cadenas à côté de l’icône du téléphone.

![](tool_signalandroid_resized006-1.png)

Une fois qu’un appel est établi, votre appel est chiffré.

### Comment Initier un Appel Vidéo Chiffré

Pour passer un appel vidéo chiffré, appelez simplement une personne de la manière citée ci-dessous :

![](tool_signalandroid_initial_video_screen.png)

et appuyez sur l’icône de la caméra vidéo. Vous devrez peut-être autoriser Signal à accéder à la vidéo à partir de votre caméra. Cela partage votre vidéo avec votre ami (votre ami devra peut-être faire la même chose).

### Comment Démarrer une Discussion de Groupe Chiffrée

Vous pouvez envoyer un message de groupe chiffré en appuyant sur l’icône de débordement (les trois points dans le coin supérieur droit de l’écran) et en sélectionnant "Nouveau groupe".

![](tool_signalandroid_resized020_0.png)

Sur l’écran suivant, vous pourrez nommer le groupe et y ajouter des participants.

![](tool_signalandroid_resized021_0.png)

![](tool_signalandroid_resized016_0.png)

Après avoir ajouté des participants, vous pouvez appuyer sur la coche dans le coin supérieur droit de l’écran. Cela initiera la discussion de groupe.

![](tool_signalandroid_resized019_0.png)

Si vous souhaitez modifier le nom du groupe, ou ajouter ou supprimer des participants, vous pouvez le faire à partir de l’écran de discussion en appuyant sur l’icône de débordement (les trois points dans le coin supérieur droit de l’écran) et en sélectionnant "Modifier le groupe".

### Conversations Muettes

Parfois, les conversations peuvent être gênantes. Une fonctionnalité particulièrement utile pour les discussions de groupe est la désactivation des notifications, de sorte que vous ne voyez pas une nouvelle notification à chaque fois qu’un nouveau message est créé. Cela peut être fait à partir de l’écran de discussion de groupe en appuyant sur l’icône de débordement (les trois points dans le coin supérieur droit de l’écran) et en sélectionnant "Mettre Notifications en Silence". Vous pouvez ensuite sélectionner la durée pendant laquelle vous souhaitez que la mise en sourdine soit active. Cela peut également s’appliquer aux conversations individuelles, si vous le souhaitez.

### Comment Vérifier vos Contacts

À ce stade, vous pouvez vérifier l’authenticité de la personne avec laquelle vous parlez, afin de vous assurer que sa clé de chiffrement n’a pas été falsifiée ou remplacée par la clé d’une autre personne lorsque votre application l’a téléchargée (un processus appelé vérification de clé). La vérification est un processus qui a lieu lorsque vous êtes physiquement en présence de la personne à qui vous parlez.

Commencez par ouvrir l’écran où vous pouvez envoyer un message à votre contact, comme décrit ci-dessus. Sur cet écran, appuyez sur l’icône de débordement (les trois points dans le coin supérieur droit de l’écran) et sélectionnez "Paramètres de conversation".

![](tool_signalandroid_resized010_0.png)

À partir de l’écran suivant, appuyez sur "Vérifier les Numéros de Sécurité".

![](tool_signalandroid_resized011_0.png)

Vous allez désormais être amené à un écran qui affiche un code QR et une liste de "numéros de sécurité". Ce code sera unique pour chaque contact différent avec lequel vous conversez. Faites en sorte que vos contacts accèdent à l’écran correspondant pour discuter avec eux, afin qu’ils aient également un code QR affiché sur leur écran.

![](tool_signalandroid_resized012_0.png)

De retour sur votre appareil, vous pouvez taper sur votre code QR, ce qui utilisera votre caméra pour scanner le code QR affiché sur l’écran de votre contact. Alignez alors votre caméra sur le code QR :

![](tool_signalandroid_resized014.png)

Espérons que votre appareil photo scannera le code à barres et affichera le dialogue "Numéros de Sécurité Vérifiés !" suivant :

![](tool_signalandroid_resized015.png)

Cela indique que vous avez vérifié votre contact avec succès. Si à la place, votre écran ressemble à ceci, quelque chose ne va pas :

![](tool_signalandroid_resized013.png)

Vous voudrez peut-être éviter de discuter de sujets sensibles avant d’avoir vérifié les clés avec cette personne.

_Note pour les utilisateurs expérimentés : L’écran affichant votre code QR comporte également une icône permettant de partager votre numéro de sécurité dans le coin supérieur droit. La vérification en personne est la méthode recommandée, mais vous avez peut-être déjà authentifié votre contact à l’aide d’une autre application sécurisée, telle que PGP. Puisque vous avez déjà vérifié votre contact, vous pouvez utiliser en toute sécurité la confiance établie dans cette application pour vérifier les numéros au sein de Signal, sans avoir à vous trouver physiquement en présence de votre contact. Dans ce cas, vous pouvez partager votre numéro de sécurité avec cette application en appuyant sur l’icône "partager" et envoyer à votre contact votre numéro de sécurité._

### Disparition des Messages

Signal a une fonctionnalité appelée "disparition de messages" qui garantit que les messages seront supprimés de votre appareil et de l’appareil de votre contact un certain temps après leur affichage. Pour permettre la disparition des messages lors d’une conversation, ouvrez l’écran dans lequel vous pouvez envoyer un message à votre contact. Sur cet écran, appuyez sur l’icône de débordement (les trois points en haut à droite de l’écran), puis appuyez sur le menu déroulant situé à côté de "Disparition des Messages".

![](tool_signalandroid_resized022_0.png)

Un menu déroulant apparaîtra vous permettant de choisir la rapidité avec laquelle les messages disparaîtront :

![](tool_signalandroid_resized009.png)

Après avoir sélectionné cette option, vous devriez voir l’information dans la conversation indiquant que la "disparition des messages" a été activé.

![](tool_signalandroid_resized008_0.png)

Vous pouvez désormais envoyer des messages avec l’assurance qu’ils seront supprimés après le délai choisi.