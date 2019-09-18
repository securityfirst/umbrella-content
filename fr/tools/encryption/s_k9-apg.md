---
index: 5
title: K9 & Open Keychain
---
# GUIDE K-9 & OPEN KEYCHAIN


**Leçon à lire : [Courriel Avancé](umbrella://lesson/courriel/1).**
**Niveau** : Avancé
**Publié :** Mai 2018
**Sources :** Security in a Box, [K9 AVEC APG POUR ANDROID](https://securityinabox.org/en/guide/k9/android/), Open Keychain [FAQ](https://www.openkeychain.org/faq/).

**K-9 Mail** est un fournisseur de messagerie à code source ouvert et gratuit pour les appareils Android.

**Open Keychain** est une application à code source ouvert et gratuite vous permettant de chiffrer, déchiffrer ainsi que de signer les messages ou courriels utilisant le chiffrement par clé publique tel que OpenPGP. Celle-ci est basée sur un code provenant d’un outil similaire nommé APG, désormais inaccessible.

**En utilisant K-9 Mail avec Open Keychain, vous obtiendrez :**
- La capacité d’utiliser des courriels chiffrés sur votre appareil Android.

**Téléchargement :** [K-9 Mail](https://play.google.com/store/apps/details?id=com.fsck.k9) et [Open Keychain](https://play.google.com/store/apps/details?) dans Google Play Store.
**Configuration requise** : version Android 4.0.3. et ultérieure.
**Version utilisée dans ce guide** : 5.403 (K-9 Mail) ; 5.0.2 (Open Keychain)
**Licence** : FOSS.

# 1. Introduction

**K-9 Mail** est un fournisseur de messagerie complet vous permettant d’envoyer et de recevoir des courriels provenant d’un ou plusieurs comptes de messagerie sur votre appareil Android, et de le faire de manière plus sécurisée à l’aide de [Open Keychain](https://play.google.com/store/apps/details?id=org.sufficientlysecure.keychain&hl=fr).

**Note :**
- Les services de messagerie sécurisés comme Signal sont un meilleur choix que l’courriel pour les communications sensibles.
- Transférer une clé de chiffrement privée vers votre téléphone peut rendre vos courriels plus sécurisés dans votre appareil, mais peut également rendre la clé plus vulnérable à la perte ou interception. (Open Keychain décrit le risque sur leur [site Web](https://www.openkeychain.org/faq/#are-my-secret-keys-safe-on-my-mobile-device).)
- Les *destinataires* et l’*objet* ne peuvent être caché des personnes surveillant votre courriel, même si l’courriel est chiffré.

Avant de commencer à utiliser **K-9 Mail**, vous aurez besoin :
- Une connexion Internet sur votre téléphone.
- Un compte de messagerie supportant les connexions sécurisées POP3 ou IMAP. (Voir les paramètres que vous utiliserez avec les fournisseurs de messagerie les plus connus [ici](https://k9mail.github.io/documentation/accounts/providerSettings.html).)
- Une paire de clés OpenPGP et des clés publiques des personnes avec lesquelles vous allez communiquer.

(Apprenez-en plus sur le chiffrement par clé publique/privée dans la leçon sur l’[courriel](umbrella://lesson/courriel). Apprenez comment générer votre propre clé à l’aide des guides pour [Mailvelope](umbrella://tools/messaging/s_mailvelope.md), ou PGP pour [LINUX](umbrella://tools/pgp/s_pgp-for-linux.md), [Mac OSX](umbrella://tools/pgp/s_pgp-for-mac-os-x.md), ou [Windows](umbrella://tools/pgp/s_pgp-for-windows.md).)

# 2. Installation et configuration de K9 Mail

## 2.1 Installation

**Étape 1.** Téléchargez et installez K-9 Mail à partir de la boutique [Google Play](https://play.google.com/store/apps/details?id=com.fsck.k9). Vérifiez attentivement les autorisations que vous donnez à l’application avant d’accepter les conditions de celle-ci.

![](tool_k9_1.png)

**Étape 2.** **Appuyez** sur *Ouvrir* afin de démarrer l’application pour la première fois.

## 2.2 Configuration

Cliquez sur *Suivant* pour commencer l’installation du compte.

Lorsque c’est possible, **K-9 Mail** essaiera de configurer automatiquement votre compte. Dans le cas contraire, ou si vous souhaitez avoir plus de contrôles sur le processus d’installation du compte, vous pouvez également le configurer manuellement.

**Étape 1 :** Entrez votre adresse courriel et mot de passe dans les champs fournis, puis appuyez sur *Suivant*.

![](tool_k9_2.png)

K-9 Mail se connectera à Internet et essaiera d’obtenir les paramètres de votre compte.

**Note :** Les utilisateurs utilisant l’identification à deux facteurs sur leur compte courriel peuvent avoir besoin d’une étape supplémentaire afin d’utiliser K-9 Mail.

Exemple :
* Les utilisateurs Gmail doivent autorisé les applications moins sécurisées à accéder à leurs comptes au sein de leurs paramètres, et doivent générer un mot de passe à usage unique. En savoir plus [ici](https://support.google.com/accounts/answer/6010255?hl=fr).
* Les utilisateurs Yahoo peuvent autorisé les applications utilisant une connexion moins sécurisée dans les Paramètres du Compte. En savoir plus [ici](https://help.yahoo.com/kb/SLN27791.html?guccounter=1).

(Les fournisseurs de messagerie classifie K-9 Mail en tant que "moins sécurisé" car il n’utilise pas le même protocole d’authentification. Cependant, les outils de confiance à code source ouvert comme K-9 Mail sont toujours considérés comme étant sécurisés pour le chiffrement d’courriel.)


**Étape 2** : Entrez votre nom comme vous le désirez affiché sur tout les courriels que vous envoyés. Donnez également un nom au compte afin de le distinguer parmi plusieurs comptes. Appuyez ensuite sur *Terminé*.

**Étape 3 :** Envoyez un courriel à vous-mêmes à partir de votre ordinateur afin de vous assurer que vous puissiez le lire dans K-9 Mail.

**Note :** Si vous choisissez *configuration manuelle*, on vous demandera de sélectionner les paramètres correspondant à votre type d’courriel (IMAP/POP/Exchange), ainsi que les paramètres des serveurs entrants et sortants. Référez-vous aux paramètres de configuration de votre fournisseur de messagerie sur votre ordinateur pour obtenir ces informations.

- Pour la configuration du serveur, assurez-vous toujours que le *type de sécurité* est toujours défini sur *STARTTLS* ou *SSL/TLS*. N’utilisez **jamais** l’option *aucun*.

- Si K-9 Mail affiche un avertissement concernant le certificat de votre connexion sécurisée, *ne l’ignorez pas*, vérifiez cependant que le certificat correspond bien au mail de votre serveur. Si cela n’est pas le cas, vos communications peuvent être interceptées. Vous devriez voir l’empreinte SHA-1 à la fin de cet avertissement. Vérifiez sur votre ordinateur si le certificat installé à partir du mail de votre serveur possède la même empreinte, ou cherchez un moyen de vérifier celui-ci en vous adressant directement à votre fournisseur de messagerie.


Nous vous recommandons d’utiliser **K-9 Mail** en plus du client de messagerie de votre ordinateur. Lorsque vous téléchargez un courrier électronique, ce dernier ne sera pas supprimé du serveur par défaut puisque vous souhaitez également recevoir le courrier électronique sur votre ordinateur. Mais ceci, ainsi que d’autres paramètres, peuvent être modifiés. Appuyez longuement sur le compte que vous venez de configurer et sélectionnez *paramètres du compte* dans le menu, ou appuyez sur les trois points dans le coin inférieur droit de l’application et sélectionnez Paramètres pour consulter vos options.


# 3. Envoyer et recevoir des courriels chiffrés

**Étape 1 :** Sous Paramètres, appuyez sur *Cryptographie*. Si vous ne l’avez pas déjà fait, K-9 Mail vous invitera à télécharger Open Keychain. Une fois Open Keychain téléchargé, sélectionnez-le dans K-9 Mail.

![](tool_k9_5.png)

Avant de pouvoir commencer à envoyer et à recevoir des courriels chiffrés, vous devez vous assurer que toutes vos clés OpenPGP ont été importées dans Open Keychain.

# 4. Configuration d’Open Keychain

Appuyez sur Open Keychain pour ouvrir l’application. Dans Paramètres, appuyez sur *Gérer mes clés*.

![](tool_k9_6.png)  

**Option 1 :** Si vous utilisez PGP pour la première fois ou si vous souhaitez créer une nouvelle clé, appuyez ensuite sur *Créer ma clé* et suivez les instructions.

**Option 2 :** Si vous avez déjà une clé PGP et souhaitez l’utiliser sur votre appareil Android, ouvrez le programme que vous utilisez sur votre ordinateur pour gérer les clés (tel que GPG Keychain ou Mailvelope) et exportez votre propre clé, incluant votre clé privée ou secrète. Sauvegardez ensuite le fichier dans un lieu sécurisé.

**Note :** Votre clé privée peut être utilisée pour usurper votre identité et déchiffrer vos communications chiffrées. Le transférer sur un appareil mobile est risqué car le fichier pourrait être perdu ou intercepté.

Si vous choisissez de transférer votre fichier de clé privée, prenez les précautions suivantes :

- Connectez votre appareil Android de confiance à votre ordinateur de confiance à l’aide d’un câble USB pour le transférer directement ou activez Bluetooth sur votre ordinateur de confiance et votre appareil Android de confiance (vérifiez que les codes de couplage correspondent) et utilisez la fonction "envoyer le fichier au périphérique" ; ou,
- Voir les conseils d’[Open Keychain](https://www.openkeychain.org/faq/#what-is-the-best-way-to-transfer-my-own-key-to-openkeychain) sur le mot de passe protégeant votre clé en utilisant la ligne de commande avant de la transférer sur Internet.

Dans la fenêtre *Gérer mes clés* d’Open Keychain, appuyez sur *Importer une clé à partir d’un fichier*, puis sur l’icône du fichier. Naviguez jusqu’au dossier où vous avez déplacé le fichier, sélectionnez-le et tapez sur *OUVRIR*. Vous pouvez également utiliser la *Clé d’importation du fichier* pour transférer les clés publiques que d’autres personnes ont partagées avec vous. Les clés importées avec succès vont maintenant apparaître dans votre liste de clés. Une fois que vous les voyez dans Open Keychain, supprimez les fichiers de votre appareil. Ne les laissez pas dans un dossier.

(Pour en savoir plus sur la gestion des clés, lisez les entrées de groupe de clés et d’échange de signatures de clés dans le glossaire Umbrella.)


# 5. Échange des courriels chiffrés avec K9

**Étape 1 :** À partir de n’importe quel écran de **K-9 Mail**, appuyez sur l’icône enveloppe + pour lancer un nouvel courriel à une personne avec laquelle vous avez déjà échangé des clés publiques.

**Étape 2 :** Ajoutez l’adresse courriel du destinataire dans le champ *À*.

**Étape 3 :**

![](tool_k9_7.png)

Appuyez sur l’icône de verrou gris ; cette icône deviendra verte lorsque le chiffrement est actif.

![](tool_k9_8.png) 

**Étape 4 :** Envoi d’un message.

**Étape 5 :** Lorsque vous recevez une réponse chiffrée, K-9 Mail vous invitera automatiquement à entrer votre phrase secrète GPG et à déchiffrer le courrier.