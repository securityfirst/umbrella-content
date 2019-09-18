---
index: 11
title: PGP pour Mac OS
---
# GUIDE PGP POUR MAC OS

Courriel chiffré pour Mac

**Leçon à lire :**
- [Courriel](umbrella://lesson/courriel)**  
**Téléchargement :**
 - [GPG Suite](https://gpgtools.org/)   
- [Mozilla Thunderbird](https://www.mozilla.org/thunderbird/)   
- [Enigmail](https://www.enigmail.net/home/index.php)  
**Configuration requise pour l’ordinateur :** Une connexion Internet, un ordinateur exécutant Mac OS, un compte de messagerie
**Version utilisée dans ce guide :**
- GPG Suite Beta 4  
- Mozilla Thunderbird 31.2.0  
- Enigmail 1.7.2  
**Licence :** Logiciel libre; mélange de licences de logiciels libres
**Niveau :** Avancé
**Autres lectures :** [http://support.gpgtools.org/](http://support.gpgtools.org/)  
**Temps requis :** 30-60 minutes

**L’utilisation de PGP vous donnera :**
- La possibilité de protéger vos courriels de toute lecture de la part d’inconnu, sauf de leurs destinataires.
- La possibilité de prouver qu’un courriel provient d’une personne en particulier, au lieu d’être un faux message envoyé par un autre expéditeur (il est très facile de créer un courriel). Les deux sont des défenses importantes si vous êtes ciblé pour la surveillance ou la désinformation.

**Note :** Si vous craignez que les courriels chiffrés par PGP ne soient plus sûrs après la détection de vulnérabilités en Mai 2018, consultez la section Efail de notre leçon avancée sur les [courriel](umbrella://lesson/courriel).

### 1.0 Avant de commencer

Pour utiliser Pretty Good Privacy (PGP), vous devez installer un logiciel supplémentaire qui fonctionnera avec votre programme de messagerie actuel. Vous aurez également besoin de créer une clé privée, que vous garderez privée. La clé privée est ce que vous utiliserez pour déchiffrer les courriers électroniques qui vous sont envoyés et pour signer numériquement les courriers électroniques que vous envoyez pour montrer qu’ils proviennent réellement de vous. Enfin, vous apprendrez à distribuer votre clé publique - un petit bloc d’informations que les autres devront connaître avant de pouvoir vous envoyer du courriel chiffré et qu’ils pourront utiliser pour vérifier les courriels que vous leur envoyez.

Ce guide vous montrera comment utiliser PGP avec un Mac Apple (mais pas un iPad ou un iPhone), soit avec le programme de messagerie intégré du Mac, soit avec Mozilla Thunderbird, un programme de messagerie alternatif populaire.

Actuellement, vous ne pouvez pas utiliser directement PGP avec un service de messagerie Web tel que Gmail, Hotmail, Yahoo! Mail ou Outlook Live. Vous pouvez toujours utiliser votre adresse de messagerie Web. vous devrez simplement le configurer avec le programme Thunderbird sur votre ordinateur.

**Notez que les deux bouts de la conversation par courriel doivent utiliser un logiciel compatible PGP pour que cela fonctionne. **

Les gens l’utiliseront normalement uniquement sur leurs propres appareils personnels, pas sur des appareils partagés. Heureusement, PGP est disponible pour la plupart des ordinateurs de bureau et des périphériques mobiles. Vous pouvez leur indiquer ces guides pour les aider à configurer leur propre version. Ce guide est destiné aux utilisateurs de Mac.

### 2.0 Installation de GPGTools sur votre Mac

PGP est une licence libre, ce qui signifie que plusieurs logiciels peuvent l’utiliser. Le logiciel que nous allons utiliser pour PGP est appelé GPG Suite, une application de GPG Tools, car il fonctionne sur les Mac, il est gratuit et accessible à tous. Il est à code source ouvert : le code source sous-jacent est disponible pour permettre à quiconque de rechercher des bogues.

Une fois GPG Suite installé, vous pouvez configurer vos clés pour la première fois, puis activer PGP sur Apple Mail et, éventuellement, Thunderbird.

**Étape 1 : Installation du programme.**

Tout d’abord, allez à [https://www.gpgtools.org/](https://www.gpgtools.org/) dans votre navigateur et choisissez "Télécharger GPG Suite.
![image](tool_pgposx1.png)

Vous obtiendrez une image disque sur laquelle vous pourrez cliquer pour installer le logiciel. Si vous n’êtes pas habitué à installer un logiciel tiers sur votre ordinateur, adressez-vous à un expert Mac à proximité. C’est une étape avec laquelle la plupart des techniciens peuvent vous aider, même s’ils ne connaissent pas PGP ou le chiffrement.
![image](tool_pgposx2.png)

En cliquant sur installer, vous obtiendrez une liste des outils qui seront ajoutés à votre ordinateur.
![image](tool_pgposx3.png)

**_Qu’est-ce que je suis en train d’installer ?_**

Ces outils fonctionnent généralement en coulisse, de sorte que plusieurs programmes de votre Mac peuvent utiliser PGP. Considérez-les comme des programmes pouvant être utilisés par d’autres programmes, plutôt que comme des applications que vous utiliserez directement. GPGMail permet à Apple Mail d&#39;envoyer et de lire des courriels PGP. GPG Keychain Access vous permet de conserver vos clés privées et publiques de la même manière que vous pouvez enregistrer d’autres mots de passe sur votre Mac.

GPGServices ajoute éventuellement une fonctionnalité à OS X pour vous permettre d’utiliser PGP directement dans des programmes autres que la messagerie électronique (par exemple, dans un traitement de texte). GPG Preferences permet de modifier les paramètres PGP dans les préférences d’Apple. Enfin, Mac GPG2 est l’outil de base que tout programme doit utiliser pour chiffrer ou signer.

En octobre 2014, l’équipe GPG Tools a annoncé qu’elle facturerait bientôt GPGMail, la partie de son package qui vous permet d’utiliser GPG avec l’application Mail d’Apple. Ce tutoriel concerne l’utilisation de GPG avec Thunderbird, il n’utilise donc pas ce composant. Vous pouvez simplement utiliser la partie gratuite de la GPG Suite, comme indiqué ici, si vous le souhaitez. Cette option présente l’avantage supplémentaire que tous ces outils sont des "logiciels libres", ce qui signifie que vous êtes toujours autorisé à examiner, éditer et redistribuer librement le code source sous-jacent de GPG Mail, de manière à ce qu’ils soient encore plus sûrs. Pour plus d’informations sur leur décision, voir la [FAQ] de GPG Tools (https://gpgtools.org/news.html).


Cliquez sur "Continuer" pour installer GPG Suite.
![image](tool_pgposx4.png)

Une fois l’installation terminée, ouvrez GPG Keychain (situé dans le dossier de vos applications) s’il ne s’ouvre pas automatiquement et demandez-lui de générer vos clés PGP après l’installation. Cliquez sur "Nouveau" pour générer vos clés PGP.
![image](tool_pgposx5.png)

**Étape 2 : Création de votre clé PGP**

Parfois, lorsque vous installez un nouveau logiciel, votre ordinateur vous harcèle de questions qui n’ont pas de réponse évidente, sans vous donner réellement de conseils sur la façon de répondre. C’est l’un de ces moments.

Il est important de réfléchir un peu aux réponses que vous donnerez ici, car il peut s’avérer difficile de modifier les détails de votre clé PGP ultérieurement, et si vous avez choisi de publier votre clé quelque part, vous ne pourrez pas l’annuler. (Il existe encore des milliers de vieilles clés publiques des années 1990, avec les noms et les anciennes adresses électroniques des personnes qui les ont fabriquées à l’époque.)

Les clés PGP contiennent un nom et une adresse électronique qui lient la clé à vous. L’adresse courriel sera l’un des moyens par lesquels les autres pourront découvrir la clé à utiliser lorsqu’ils vous chiffrent un message.

**_À quel moment ne devrais-je pas mettre mon vrai nom ou mon adresse courriel sur ma clé PGP ? À quel moment ne devrais-je pas télécharger ma clé ?_**

Pour la plupart des gens, il est logique d’ajouter une adresse courriel réelle à votre clé et de la télécharger sur les serveurs de clés publiques - c’est la façon dont les gens vont vous attribuer la bonne clé. Ils peuvent vous envoyer directement un courrier électronique et savoir qu’il sera chiffré avec la clé appropriée. Lorsqu’ils recevront un courrier électronique signé, la signature numérique sera marquée de votre nom.

Pour certaines personnes, toutefois, il n’est pas logique d’ajouter votre vrai nom à votre clé, par exemple si votre modèle de menace signifie qu’avoir votre identité publiquement attachée à votre clé (et à l’adresse électronique associée) n’est pas une bonne idée. Edward Snowden a communiqué avec des journalistes utilisant PGP et une adresse électronique anonyme avant de révéler son identité ; sa clé PGP n’était certainement pas marquée avec son nom.

**Le téléchargement de votre clé est une pratique normale, mais cela peut révéler que vous utilisez le chiffrement, même si vous n’utilisez pas votre propre nom. En outre, comme nous le verrons, d’autres pourraient télécharger votre clé et y associer sa propre clé, ce qui implique que vous et eux avez une connexion. Cela peut être préjudiciable si vous communiquez et ne voulez pas que les gens le sachent. Cela peut également être gênant si vous ne communiquez pas, mais votre attaquant veut que les gens pensent que vous êtes associé.**

Voici un guide approximatif : si vous envisagez d’utiliser un pseudonyme en général, utilisez ce pseudonyme (et son adresse électronique alternative) lors de l’étiquetage de votre clé. Si vous vous trouvez dans un environnement plus dangereux, si vous ne voulez pas que les gens sachent que vous utilisez PGP, ou savez avec qui vous communiquez, ne transférez pas votre clé sur les serveurs de clés publics - et assurez-vous que le groupe de personnes avec lequel vous communiquez ne doit pas télécharger votre clé non plus. Il existe d’autres moyens de vérifier les clés qui ne reposent pas sur leur disponibilité sur le serveur de clés publiques - voir le guide de la FFÉ sur la [Vérification des clés](https://ssd.eff.org/fr/module/v%C3%A9rification-des-cl%C3%A9s) pour plus d’informations.

Cliquez sur la case "Télécharger la clé publique après la génération" si vous souhaitez laisser les autres trouver votre clé rapidement afin qu’ils puissent vous envoyer des messages chiffrés. C’est comme ajouter votre numéro de téléphone à un répertoire téléphonique public : vous n’en avez pas besoin, mais c’est pratique pour les autres.

Avant de générer la clé, déroulez "Options avancées". Vous pouvez laisser le commentaire vide et laisser le type de clé "RSA et RSA (par défaut)". Mais assurez-vous de changer le champ concernant la longueur en 4096.
![image](tool_pgposx6.png)

**Votre clé expirera à un moment donné ; lorsque cela se produit, d’autres personnes cesseront de l’utiliser entièrement pour vous envoyer de nouveaux courriels, bien que vous ne receviez peut-être aucun avertissement ni aucune explication quant à pourquoi. Donc, pensez à le marquer sur votre calendrier et faites attention à ce problème environ un mois avant la date d’expiration.**

Il est possible de prolonger la durée de vie d’une clé existante en lui attribuant une nouvelle date d’expiration, ou de la remplacer par une nouvelle clé en en créant une nouvelle à partir de zéro. Les deux processus peuvent nécessiter de contacter des personnes qui vous envoient un courrier électronique et de s’assurer qu’ils obtiennent la clé mise à jour. Les logiciels actuels ne sont pas très efficaces pour automatiser cela. Alors faites un rappel pour vous-même ; si vous pensez ne pas être en mesure de le gérer, vous pouvez envisager de définir la clé de sorte qu’elle n’expire jamais, bien que dans ce cas, d’autres personnes pourraient essayer de l’utiliser lorsque vous contactez une personne dans le futur, même si vous n’utilisez plus la clé privée ou n’utilisez plus PGP.

Lorsque vous êtes prêt, cliquez sur le bouton "Générer une clé".

Votre ordinateur commencera à générer à la fois votre clé publique et votre clé privée. Cela ne devrait pas prendre plus de quelques minutes à la fin (cela prend un certain temps car pour créer vos clés, votre ordinateur doit rassembler des nombres aléatoires. Pensez-y comme si votre ordinateur lançait une paire de dés à plusieurs reprises.)
![image](tool_pgposx7.png)

Lorsque vous avez terminé de générer votre clé, celle-ci est répertoriée dans GPG Keychain Access. Vous pouvez double-cliquer sur votre clé pour afficher des informations à ce sujet, y compris son "empreinte", un moyen unique d’identifier votre clé PGP.

Le moment est venu de générer un certificat de révocation. (Un certificat de révocation est un fichier que vous pouvez générer et qui annonce que vous ne faites plus confiance à cette clé. Vous le générez lorsque vous avez encore la clé secrète et vous le conservez pour toute catastrophe future.) À l’avenir, si vous craignez que votre clé privée a été copiée par quelqu’un, vous supprimez ou perdez accidentellement votre clé privée ou vous oubliez votre phrase secrète. Vous pouvez indiquer à tout le monde qu’elle a été révoquée ou annulée à l’aide d’un certificat de révocation.

Il vaut mieux en créer un maintenant, car vous avez besoin de la clé privée et de la phrase secrète pour créer un certificat de révocation. Si vous le laissez à plus tard, vous risquez de perdre l’un ou l’autre, et il sera alors trop tard. Créez donc un certificat en cliquant sur votre clé, en choisissant dans le menu "Clé", puis "Créer un certificat de révocation". On vous demandera quelque part de sauvegarder le fichier. Vous voudrez peut-être le conserver avec une copie de sauvegarde de la clé (voir l’étape suivante).

**Étape 3 : Sauvegarde de votre clé PGP**

Si vous perdez l’accès à votre clé privée, vous ne pourrez déchiffrer aucun courriel PGP entrant ni votre ancien courriel. D’autre part, vous souhaitez conserver votre clé privée de manière aussi sécurisée que possible.

Vous voudrez peut-être enregistrer une copie de sauvegarde sur une clé USB, que vous garderez cachée en toute sécurité. Vous n’en aurez besoin que si vous perdez votre clé d’origine, mais par sécurité, vous voudrez la garder hors de portée de vos attaquants potentiels.

**_Est-ce que tout est perdu si mes attaquants obtiennent ma clé privée PGP ?_**

Que faire si votre Mac est volé ou si votre clé de sauvegarde vous est retirée ? Cela signifie-t-il que vos messages PGP sont vulnérables ? Non : si vous avez choisi une bonne phrase secrète et que personne n’a été en mesure d’apprendre ce que c’est, vous devriez quand même être protégé. Pour plus de sécurité, vous souhaiterez peut-être révoquer votre ancienne clé et créer une nouvelle clé PGP. Cela n’empêchera pas votre ancienne clé de déchiffrer votre ancien courrier électronique, mais dissuadera d’autres personnes d’utiliser l’ancienne clé pour vous envoyer de nouveaux courriels.


Pour sauvegarder votre clé, ouvrez GPG Keychain Access. Sélectionnez votre clé et cliquez sur "Exporter" dans la barre d’outils. Placez votre clé USB dans l’appareil et choisissez-la dans la partie "Où" à partir de la boîte de dialogue, puis "Enregistrer sous ...". Cochez la case "Autoriser l’exportation de clé secrète".

**OPTION A) Configuration d’Apple Mail**

Lorsque vous ouvrez Apple Mail pour la première fois, un assistant de première exécution vous aide à configurer votre adresse électronique. Remplissez votre nom, adresse courriel et votre mot de passe, puis cliquez sur "Créer".
![image](tool_pgposx8.png)

**Assistant de configuration du compte de messagerie**

Si vous utilisez des services de messagerie gratuits tels que Gmail, Mail devrait pouvoir détecter automatiquement vos paramètres de messagerie lorsque vous cliquez sur Continuer. Si ce n’est pas le cas, vous devrez peut-être configurer manuellement vos paramètres IMAP et SMTP. Adressez-vous à la société de messagerie que vous utilisez ou demandez à un technicien connaissant votre fournisseur de messagerie (un informaticien au travail ou un ami technicien utilisant le même fournisseur d’accès que vous. Ils n’ont pas besoin de connaître PGP, mais vous pouvez leur demander "Pouvez-vous configurer Apple Mail pour moi ?").
![image](tool_pgposx9.png)

**Détection automatique de la configuration du compte de messagerie**



Lorsque vous rédigez un nouveau message, deux icônes se trouvent juste sous le champ Objet. Il y a un cadenas (courriel chiffré) et une étoile (courriel signé numériquement). Si le cadenas est fermé, cela signifie que cet courriel sera chiffré, et si l’étoile est cochée, cela signifie que cet courriel sera signé numériquement.


**Envoi d’courriels chiffrés ou signés par PGP**
![image](tool_pgposx10.png)

Vous pouvez toujours signer votre courrier électronique, même si le destinataire n’utilise pas PGP. Étant donné que la signature numérique d’courriels nécessite votre clé secrète, Mail affiche une fenêtre vous demandant votre phrase secrète lorsque vous signez un courriel pour la première fois.

Vous ne pouvez chiffrer les courriels que si la personne à qui vous envoyez un courrier électronique utilise PGP et que vous avez la clé publique de cette personne. Si l’icône du cadenas de cryptage est déverrouillée et grisée, vous ne pouvez donc pas cliquer dessus, cela signifie que vous devez d’abord importer la clé publique du destinataire. Demandez-leur de vous l’envoyer ou utilisez l’application GPG Keychain Access pour rechercher la clé depuis un serveur de clés public.

Pour être absolument en sécurité, vous devez vérifier les clés que vous obtenez du serveur de clés ou de votre collègue. Voir le guide de la FFÉ sur la [Vérification des clés](https://ssd.eff.org/fr/module/v%C3%A9rification-des-cl%C3%A9s) pour plus d’informations.

**OPTION B) Utilisation de PGP avec Mozilla Thunderbird**

Cette procédure montre comment utiliser GPG avec le fournisseur de messagerie gratuite et à code source ouvert; Thunderbird de Mozilla, avec le plugin Enigmail pour le chiffrement d’courriels.

Commencez par télécharger Thunderbird à partir de [https://www.mozilla.org/thunderbird](https://www.mozilla.org/thunderbird), montez l’image disque comme vous l’avez fait avec GPG Tools et faites glisser Thunderbird dans Applications. Lorsque vous ’ouvrez pour la première fois, il vous sera demandé si vous souhaitez le définir comme client de messagerie par défaut. Allez-y et cliquez sur "Définir par défaut".
![image](tool_pgposx11.png)

Ensuite, vous verrez l’assistant de première exécution. Pour configurer votre adresse électronique existante, cliquez sur "Ignorer cette option et utiliser mon adresse électronique existante". Ensuite, entrez votre nom, votre adresse électronique et le mot de passe associé à celui-ci.
![image](tool_pgposx12.png)

Si vous utilisez des services de messagerie gratuits tels que Gmail, Thunderbird devrait pouvoir détecter automatiquement vos paramètres de messagerie lorsque vous cliquez sur Continuer. Si ce n’est pas le cas, vous devrez peut-être configurer manuellement vos paramètres IMAP et SMTP - demandez à votre fournisseur d’accès à Internet ou à un ami technique connaissant la configuration de la messagerie électronique. Parfois, Thunderbird peut simplement deviner les bons paramètres.

** Si vous utilisez une authentification à deux facteurs avec Google (et en fonction de votre modèle de menace, vous devriez probablement le faire !), Vous ne pouvez pas utiliser votre mot de passe Gmail standard avec Thunderbird. Au lieu de cela, vous devrez créer un nouveau mot de passe spécifique à l’application pour que Thunderbird puisse accéder à votre compte Gmail. Consultez le [guide de Google](https://support.google.com/mail/answer/1173270?hl=fr) pour ce faire. **
![image](tool_pgposx13.png)

Après avoir configuré Thunderbird pour vérifier votre courrier électronique, cliquez sur "Terminé". Cliquez ensuite sur "Boîte de réception" en haut à gauche pour charger vos courriels.

Maintenant que vous avez installé et configuré Thunderbird pour fonctionner avec votre courrier électronique, vous devez installer [Enigmail](https://www.enigmail.net/home/index.php), l’extension GPG de Thunderbird. Dans Thunderbird, cliquez sur l’icône du menu en haut à droite, puis choisissez Modules complémentaires.
![image](tool_pgposx14.png)

Recherchez "enigmail" dans la case de recherche en haut à droite.
![image](tool_pgposx15.png)

Cliquez sur le bouton Installer à côté de l’extension Enigmail pour télécharger et installer Enigmail. Quand c’est fait, cliquez sur "Redémarrer maintenant" pour redémarrer Thunderbird.

La première fois que vous exécutez Thunderbird avec Enigmail activé, il ouvre l’Assistant de configuration OpenPGP. Cliquez sur "Annuler". Nous allons configurer manuellement Enigmail à la place.

Cliquez sur le bouton Menu, passez la souris sur Préférences, puis choisissez Paramètres du Compte.
![image](tool_pgposx16.png)

Accédez à l’onglet OpenPGP Security. Assurez-vous que "Activer le support OpenPGP (Enigmail) pour cette identité" soit coché. "Utiliser un identifiant de clé OpenPGP spécifique" doit être sélectionné. Si votre clé n’est pas déjà sélectionnée, vous pouvez cliquer sur "Sélectionner une clé" pour la sélectionner.

Vous devez également cocher "Signer les messages non chiffrés par défaut", "Signer les messages chiffrés par défaut" et "Utiliser PGP/MIME par défaut", et non pas (pour la plupart des gens) "Chiffrer les messages par défaut".

Si la plupart des personnes à qui vous envoyez des courriers électroniques utilisent PGP (ou si vous souhaitez les encourager à le faire), vous souhaiterez peut-être chiffrer par défaut. L’idéal serait de chiffrer tous les courriels que vous envoyez, mais ce n’est pas toujours possible. N’oubliez pas que vous ne pouvez envoyer des courriels chiffrés qu’à d&’autres personnes utilisant PGP et que vous devez avoir leurs clés publiques dans votre trousseau. Pour la plupart des gens, choisir manuellement de chiffrer chaque courriel que vous envoyez fonctionnera probablement mieux.
![image](tool_pgposx17.png)

Cliquez ensuite sur "OK" pour enregistrer tous les paramètres.

Félicitations, vous avez maintenant Thunderbird et Enigmail mis en place ! Voici quelques conseils rapides :

- Vous pouvez cliquer sur le bouton de menu, survoler OpenPGP et ouvrir Key Management pour voir le gestionnaire de clés PGP intégré à Enigmail. C’est très similaire à GPG Keychain Access, et vous utilisez celui que vous préférez.
- Lorsque vous composez un nouveau message, il y a deux icônes dans le coin inférieur droit de la fenêtre : un stylo (courrier électronique signé numériquement) et une clé (chiffrement du courrier électronique). Si les icônes sont en or, cela signifie qu’elles sont sélectionnées et si elles sont en argent, cela signifie qu’elles ne sont pas sélectionnées. Cliquez dessus pour activer la signature et le chiffrement de l’courriel que vous écrivez.
![image](tool_pgposx18.png)