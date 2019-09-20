---
index: 7
title: Mailvelope
---
Mailvelope  
====================

Secure Webmail 

**Leçon à lire : [Protection des Fichiers](umbrella://information/protecting-files), [Courriel](umbrella://lesson/courriel)**  
**Niveau :** Avancé  
**Temps requis :** 30 à 60 minutes  
**Mise à jour :** Avril 2018 (certaines images datent de versions antérieures)  
**Sources :**  Security in a Box, [MAILVELOPE - CHIFFREMENT OPENPGP POUR WEBMAIL](https://securityinabox.org/en/guide/mailvelope/web/). 

**L’utilisation de Mailvelope vous donnera :**

- La possibilité d’envoyer et de recevoir des messages chiffrés de bout en bout qui ne peuvent pas être lus par des tiers.
- La possibilité de signer votre courrier électronique et d’authentifier le courrier électronique signé d’autrui.


**Téléchargement :** [https://www.mailvelope.com/en](https://www.mailvelope.com/en)  
**Version utilisée dans ce guide :** 1.5.1  
**Licence :** Logiciel Libre et à Code Source Ouvert  
**Configuration requise :**  **Mozilla Firefox,** **Google Chrome** ou **Chromium** opérant sur LINUX, Windows ou Mac.   

# 1. Introduction 

Mailvelope est une extension de navigateur qui vous permet de chiffrer, déchiffrer, signer et authentifier des messages électroniques et des fichiers à l’aide d’OpenPGP. (Une extension de navigateur est un composant logiciel qui ajoute des fonctionnalités supplémentaires à votre navigateur Web.) Il fonctionne avec la messagerie Web et ne nécessite pas le téléchargement ni l’installation de logiciel supplémentaire. Alors que Mailvelope ne possède pas de nombreuses fonctionnalités fournies par Thunderbird, Enigmail et GnuPG, il s’agit probablement du moyen le plus simple pour les utilisateurs de messagerie Web de commencer à tirer parti du chiffrement de bout en bout.

## 1.0 Ce que vous devriez savoir sur Mailvelope avant de commencer

Mailvelope repose sur une forme de *cryptographie par clé publique* qui oblige chaque utilisateur à générer sa propre paire de *clés*. Cette *paire de clés* peut être utilisée pour chiffrer, déchiffrer et signer du contenu numérique tel que des messages électroniques. Elle comprend une *clé privée* et une *clé publique* :

- Votre **clé privée** est extrêmement sensible. Toute personne ayant réussi à obtenir une copie de cette clé serait en mesure de lire un contenu chiffré destiné uniquement à vous. Ils pourraient également signer des messages de sorte qu’ils sembleraient provenir de vous. Votre *clé privée* est elle-même chiffrée en une phrase secrète que vous choisirez lors de la génération de votre *paire de clés*. Vous devez choisir un mot de passe complexe et veiller à ne laisser personne accéder à votre *clé privée*. Vous utiliserez votre *clé privée* pour déchiffrer les messages qui vous sont envoyés par ceux qui possèdent une copie de votre *clé publique*.

- Votre **clé publique** est destinée à être partagée avec d’autres et ne peut pas être utilisée pour lire un message chiffré ou simuler un message signé. Une fois que vous avez la clé publique du correspondant, vous pouvez commencer à lui envoyer des messages chiffrés. Il sera le seul à pouvoir déchiffrer et lire ces messages car il a accès à la *clé privée* qui correspond à la *clé publique* que vous utilisez pour les chiffrer. De même, pour que quelqu’un puisse vous *envoyer* un courrier électronique chiffré, il doit obtenir une copie de votre *clé publique*. Il est important de vérifier que la *clé publique* que vous utilisez pour chiffrer le courrier électronique appartient bien à la personne avec laquelle vous essayez de communiquer. Si vous ou votre correspondant êtes amenés à chiffrer un courriel avec la mauvaise clé publique, votre conversation ne sera pas sécurisée.

Mailvelope vous permet également de joindre des **signatures numériques** à vos messages. Si vous *signez* un message à l’aide de votre *clé privée*, tout destinataire ayant une copie de votre *clé publique* peut vérifier qu’il a été envoyé par vous et que son contenu n’a pas été falsifié. De même, si vous avez la *clé publique* d’un correspondant, vous pouvez vérifier ses signatures numériques.

Mailvelope vous permet de :

- Générer une paire de clés de chiffrement
- Exporter votre clé publique afin que vous puissiez la partager avec d’autres
- Importer les clés publiques d’autres personnes
- Composer, chiffrer et signer des courriels
- Déchiffrer et authentifier les messages
- Chiffrer, attacher et déchiffrer des fichiers

Vos correspondants ne doivent pas nécessairement utiliser Mailvelope, mais ils doivent utiliser une forme de chiffrement OpenPGP, dont plusieurs sont énumérés ci-dessous.

Comme Mailvelope est une extension de navigateur, il ne fonctionnera qu’avec le navigateur sur lequel il a été installé. Si vous souhaitez utiliser Mailvelope avec un autre navigateur, vous devrez l’installer à nouveau. Cela est vrai même si les deux navigateurs sont sur le même ordinateur. Vous devrez également exporter toutes vos clés et les importer dans la nouvelle copie de Mailvelope.


## 1.1 Autres outils comme Mailvelope

Comme Mailvelope est une extension de navigateur, il fonctionne sur la plupart des systèmes d’exploitation de bureau. Cela inclut GNU/Linux, Microsoft Windows et Mac OS X. Cela ne fonctionne pas sur les appareils mobiles Android ou iOS. Voici quelques alternatives gratuites à code source ouvert :

- [**Thunderbird avec Enigmail**](../../thunderbird/windows) Client de messagerie complet avec chiffrement PGP ajouté pour GNU/Linux, Microsoft Windows et Mac OS X  
- [**GPG4Win**](https://www.gpg4win.org/) Suite d’outils de chiffrement de messagerie et de fichiers PGP pour Microsoft Windows
- [**Suite d’Outils GPG**](https://gpgtools.org/) pour Mac OS X  
- [**gpg4usb**](https://www.gpg4usb.org/) Outil de PGP portable et autonome pour GNU/Linux et Microsoft Windows  
- [**Mailpile**](https://www.mailpile.is/) Un prochain client de messagerie compatible OpenPGP pour GNU/Linux, Microsoft Windows et Mac OS X  

# 2. Génération et partage de clés de chiffrement

Avant de pouvoir commencer à chiffrer et à déchiffrer un courrier électronique, vous devez suivre trois étapes préparatoires :

- Générez votre paire de clés de chiffrement (ou importez-la si vous en avez déjà une)
- Exportez votre clé publique et envoyez-la à vos contacts
- Importez des clés publiques à partir de vos contacts


## 2.1 Générer une paire de clés

Pour générer votre paire de clés, ouvrez le navigateur sur lequel vous avez installé Mailvelope et suivez les étapes ci-dessous.

**Étape 1**. **Cliquez** sur **l’icône de verrouillage** Mailvelope dans la barre d’outils de votre navigateur pour activer l’écran suivant :

![](mailvelope-all-en-v01-002.png)

**Étape 2**. **Cliquez** sur **[Options]** pour activer l’écran des *Options* Mailvelope

![](mailvelope-all-en-v01-003.png)

**Étape 3**. **Cliquez** sur **[Générer une clé]** et **tapez** vos informations dans les champs, comme indiqué ci-dessous :

![](mailvelope-all-en-v01-004.png)

**Important :**

- Choisissez une phrase de passe forte pour protéger votre clé privée. (Apprenez à créer des [mots de passe](umbrella://information/passwords/beginner) forts.)
- Vous n’êtes pas obligé d’utiliser votre vrai nom lors de la génération de votre clé, mais vous devez entrer l’adresse courriel du compte avec laquelle vous avez l’intention d’utiliser Mailvelope. Si vous le souhaitez, vous pouvez créer un nouveau compte de messagerie spécialement à cet effet.
- Nous vous recommandons de générer une paire de clés unique pour chaque compte de messagerie que vous souhaitez utiliser avec Mailvelope.

**Étape 4**. **Décochez** la case *Télécharger la clé publique sur le Serveur de Clés Mailvelope*

**Étape 5**. **Cliquez** sur **[Soumettre]** pour commencer à générer votre paire de clés :

![](mailvelope-all-en-v01-005.png)

Une fois l’opération terminée, Mailvelope affiche : "**Succès ! Nouvelle clé générée et importée dans le trousseau de clés**".

**Étape 6**. **Cliquez** sur les *Afficher les clés* pour jeter un coup d’œil à votre nouvelle paire de clés, comme indiqué dans la section ci-dessous.

## 2.2 Exporter et envoyer votre clé publique avec Mailvelope

Vous devez partager votre clé publique avec d’autres personnes afin qu’elles vous envoient un courrier électronique chiffré. Vous devez également partager l’intégralité de *l’empreinte* de votre clé, via un autre canal, afin que vos correspondants puissent vérifier que la clé publique que vous leur avez envoyée vous appartient réellement. **Vous ne devez jamais partager votre clé privée**, car toute personne en ayant une copie peut déchiffrer les messages qui vous sont envoyés et signer les messages de sorte qu’ils semblent provenir de vous.

Pour exporter votre clé publique avec Mailvelope, suivez les étapes ci-dessous.

**Étape 1**. À partir de l’onglet de navigation **Options Mailvelope**, **sélectionnez** l’onglet **Gestion des clés**, puis **cliquez** sur **[Afficher les clés]** à gauche.

![](mailvelope-all-en-v01-006.png)

**Étape 2**. **Cliquez** sur la clé que vous souhaitez exporter. (Dans notre cas, la clé publique que nous venons de générer est la seule que nous ayons.)

Cela activera l’écran ci-dessous :

![](mailvelope-all-en-v01-007.png)

Cet écran affiche, entre autres choses, l’empreinte de votre paire de clés. Par exemple, l’empreinte numérique de la paire de clés que nous venons de générer pour *ekaterina@riseup.net* est **3B9F 54DD 571A 6F77 251D 92E7 E8B1 F5E6 FBB4 EFFE**.

**Étape 3**. **Cliquez** sur l’onglet **Exporter**.

![](mailvelope-all-en-v01-008.png)

**Important :** Assurez-vous que **[Publique]** soit bien sélectionné en haut de l’écran. Si vous sélectionnez *[Privée]* ou *[Toute]*, vous exporterez votre clé privée. Vous ne devez jamais envoyer votre clé privée à une autre personne ni la télécharger sur un serveur. (Les seules raisons pour lesquelles vous souhaitez exporter votre clé privée sont le fait de procéder à une sauvegarde chiffrée ou de migrer vos clés vers un nouveau navigateur Web.) Le nom de fichier par défaut doit se terminer par "_Pub.asc".

**Étape 5**. **Cliquez** sur **[Enregistrer]** pour enregistrer votre clé publique

**Étape 6** : Envoyez le fichier que vous venez d’exporter (*Elena_Katerina_Pub.asc*, dans ce cas) aux correspondants avec lesquels vous souhaitez échanger un courrier électronique chiffré.

## 2.3 Importer une clé publique avec Mailvelope

Avant de pouvoir chiffrer un message destiné à un correspondant, vous devez importer sa clé publique. Pour importer la clé publique d’un correspondant à l’aide de Mailvelope, suivez les étapes ci-dessous.

**Étape 1**. Après avoir reçu une clé publique en pièce jointe, enregistrez le fichier quelque part sur votre ordinateur.

**Étape 2**. Dans l’onglet de navigation **Options Mailvelope**, **sélectionnez** l’onglet **Gestion des clés**, puis **cliquez** sur **[Importer les clés]** à gauche.

![](mailvelope-all-en-v01-009.png)

Sur cet écran, vous pouvez :

- Rechercher un serveur de clé publique en entrant le nom, l’adresse courriel ou le numéro de clé de votre correspondant.
- Sélectionner un fichier texte contenant une clé
- Copier et coller le bloc de texte dans un fichier de clé

Les étapes ci-dessous supposent que vous avez reçu un fichier clé et que vous l’avez enregistré sur votre ordinateur. Nous allons donc utiliser la deuxième option.

**Étape 3**. **Cliquez** sur ** [Sélectionner un fichier texte clé à importer]**.

**Étape 4**. **Accédez** au fichier clé sur votre ordinateur et **cliquez** sur **[Importer]**

Une fois terminé, Mailvelope affichera quelque chose comme : "**Succès ! Clé publique 6764717C5D64FBB6 de l’utilisateur Mansour <mansour@riseup.net> importée dans le trousseau de clés**"

Si vous cliquez sur **[Afficher les clés]**, à gauche de l’onglet **Gestion des clés**, vous devriez voir votre clé publique nouvellement importée :

![](mailvelope-all-en-v01-010.png)

Avant d’envoyer un message chiffré à ce correspondant, vous devez vérifier sa clé.

## 2.4 Vérifier la clé publique d’un correspondant

Vous devez maintenant vérifier que la clé que vous avez importée provient bien de la personne à laquelle vous pensez qu’elle appartient. Vous et vos correspondants de courrier électronique devez suivre cette procédure pour chaque clé publique que vous recevez.

Pour vérifier la clé publique de votre correspondant, contactez-le à l’aide d’un moyen de communication vous permettant d’être absolument certain de parler à la bonne personne. Les réunions en personne sont préférables, mais les conversations audio et vidéo sont acceptables si vous êtes sûr de pouvoir reconnaître la voix ou l’apparence de celle-ci. Vous allez échanger des empreintes de clé publique, qui n’ont pas besoin d’être gardées secrètes. Cette conversation n’a donc pas à être confidentielle tant que vous vous abstenez de discuter de sujets sensibles.

Vous et votre correspondant devez tous les deux vérifier les empreintes des clés publiques que vous avez échangées. Une empreinte numérique est une série unique de chiffres et de lettres identifiant une clé. Vous pouvez utiliser la section **Afficher les clés** de l’onglet **[Gestion des clés]** dans **Options Mailvelope** afin de déterminer :

- L’empreinte de la paire de clés que vous avez généré
- L’empreinte des clés publiques d’autres personnes que vous avez importé

Pour afficher l’empreinte d’une paire de clés particulière, procédez comme suit :

**Étape 1**. **Cliquez** sur **[Afficher les clés]** à gauche, à partir de l’onglet **Gestion des clés**.

![](mailvelope-all-en-v01-010.png)

**Étape 2**. **Cliquez** sur la clé que vous désirez vérifier

![](mailvelope-all-en-v01-035.png)

Dans la fenêtre Détails de la Clé, vous verrez **l’empreinte** de la clé sélectionnée. Par exemple, l’empreinte numérique de ekaterina@riseup.net est *3B9F 54DD 571A 6F77 251D 92E7 E8B1 F5E6 FBB4 EFFE*.

Votre correspondant doit également suivre ces étapes. Pour vérifier les empreintes :

- Lisez l’empreinte de votre paire de clés à votre correspondant,  
- Demandez-lui de vérifier que l’empreinte qu’il possède pour votre clé publique correspond à ce que vous venez de lui dire.  
- Demandez à votre correspondant de vous lire l’empreinte de sa clé publique,  
- Vérifiez que l’empreinte que vous avez pour sa clé publique correspond à ce qu’il vient de vous dire,  
- Si les empreintes ne correspondent pas, échangez à nouveau les clés publiques et répétez le processus.

Note : les empreintes de clé n’étant pas sensibles, vous pouvez facilement écrire celle que votre correspondant vous a lue. Ensuite, quand vous aurez plus de temps, vous pourrez vérifier que cela correspond à l’empreinte numérique que vous avez pour sa clé publique. C’est également la raison pour laquelle certaines personnes impriment leurs empreintes digitales sur leurs cartes de visite.

## 2.5 Sauvegarde et récupération de toutes vos clés

Les paire(s) de clés que vous avez générées ainsi que les clés publiques que vous avez collectées et vérifiées sont l’élément le plus important de votre installation Mailvelope. Vous pouvez enregistrer toutes ces clés dans un seul fichier afin de les sauvegarder. Voir [Récupération à partir d’une perte d’informations](../../sauvegarde) pour planifier une stratégie de sauvegarde sécurisée. Nous vous recommandons de mettre à jour cette sauvegarde chaque fois que vous générez une nouvelle paire de clés ou importez et vérifiez une clé publique importante.

**Important :** Étant donné que ce fichier contient votre clé privée, vous ne devez pas le télécharger sur un serveur ou sur un type de "stockage cloud".


**Pour enregistrer toutes vos clés dans un seul fichier**, suivez les étapes ci-dessous à partir de l’onglet **Gestion des clés** de Mailvelope

**Étape 1**. **Cliquez** sur **[Afficher les clés]**

![](mailvelope-all-en-v01-011.png)

**Étape 2**. **Cliquez** sur **[Exporter]**

![](mailvelope-all-en-v01-012.png)

**Note :** Vous pouvez choisir n’importe quel nom et emplacement pour le fichier qui contiendra vos clés. Dans cet exemple, nous allons utiliser le nom par défaut : **all_keys.asc**

**Étape 3**. **Cliquez** sur **[Enregistrer]**

**Étape 4**. Faites une sauvegarde sécurisée de ce fichier, puis supprimez-le de votre ordinateur.

**Important :** Ce fichier contient votre/vos clé(s) privée(s). Vous devez donc conserver votre sauvegarde. Par exemple, vous pouvez vouloir la stocker dans un conteneur VeraCrypt chiffré sur un périphérique de stockage USB bien caché.

**Pour importer toutes les clés de ce fichier**, suivez les étapes pour *Importer la clé publique d’un correspondant* dans la section 2.3.


# 3. Configurer Mailvelope pour fonctionner avec votre service de messagerie Web.

Mailvelope est pré-configuré pour fonctionner avec plusieurs services de messagerie Web, y compris Gmail. Vous pouvez vérifier si Mailvelope est déjà configuré pour fonctionner avec votre fournisseur de messagerie Web en vous connectant à votre compte de messagerie et en composant un nouveau message. Vous devriez voir un bouton Mailvelope dans le coin supérieur droit de la zone de message, comme indiqué ci-dessous :

![](mailvelope-all-en-v01-016.png)

Si vous voyez ce bouton, vous pouvez ignorer les étapes restantes de cette section.

Pour que Mailvelope fonctionne avec l’interface de messagerie Web *Roundcube* utilisée par [Riseup](https://mail.riseup.net) et d’autres fournisseurs, suivez les étapes ci-dessous. En suivant un processus similaire, vous devriez également pouvoir configurer Mailvelope pour d’autres fournisseurs de messagerie Web.


**Étape 1**. **Lancez** le navigateur sur lequel vous avez installé Mailvelope

**Étape 2**. **Connectez-vous** à votre compte de messagerie

**Étape 3**. **Accédez** à votre boîte de réception et **ouvrez** n’importe quel message électronique.

**Étape 4**. **Cliquez** l’icône de verrouillage Mailvelope dans la barre d’outils de votre navigateur pour ouvrir le menu Mailvelope comme indiqué ci-dessous.

![](mailvelope-all-en-v01-013.png)

**Étape 5**. **Cliquez** sur **[Ajouter]** pour afficher un écran contenant une **Liste des fournisseurs de messagerie électronique**

![](mailvelope-all-en-v01-014.png)

Au bas de cette liste, vous devriez voir une nouvelle entrée pour **mail.riseup.net**.

**Étape 6**. Revenez à l’onglet de navigation avec votre messagerie Web.

**Étape 7**. **Cliquez sur composer** pour écrire un nouvel courriel.

**Étape 8**. **Cliquez** l’icône de verrouillage Mailvelope dans la barre d’outils de votre navigateur pour ouvrir le menu Mailvelope comme indiqué ci-dessous

![](mailvelope-all-en-v01-015.png)

**Étape 8**. **Cliquez** à nouveau sur **[Ajouter]**.

Votre navigateur affichera à nouveau un écran contenant une **Liste de fournisseurs de messagerie électronique**.

**Étape 9**. **Fermez** cet onglet du navigateur et revenez à votre messagerie Web.

**Étape 10**. **Rechargez** la page dans laquelle vous composez un nouvel courriel.

Vous devriez voir un bouton Mailvelope dans le coin supérieur droit de la zone de message, comme indiqué ci-dessous :

![](mailvelope-all-en-v01-016.png)


# 4. Chiffrement et déchiffrement des messages et des fichiers

Après avoir échangé les clés et vérifié que Mailvelope est configuré pour fonctionner avec votre fournisseur de messagerie Web, vous pouvez commencer à chiffrer et à déchiffrer les messages.

Pour une explication du fonctionnement de Mailvelope, reportez-vous à la section [Ce que vous devez savoir à propos de cet outil avant de commencer](#things-you-should-know-about-mailvelope-before-you-start). Et gardez à l’esprit que Mailvelope protège uniquement le *contenu* des messages et des pièces jointes. **Les informations suivantes ne sont jamais chiffrées :**

- La ligne *Objet :*
- L’adresse courriel de l’expéditeur  
- Les adresses courriel des destinataires  
- Noms de fichiers des pièces jointes  
- Tout nom réel pouvant être associé à des expéditeurs et des destinataires ("**Elena S. Katerina**", par exemple, dans l’adresse de messagerie suivante : "**Elena S. Katerina <ekaterina@riseup.net>**")  

Alors, choisissez vos lignes d’objet avec soin et envisagez de créer une paire de clés pour au moins un compte de messagerie qui n’inclut pas votre vrai nom.

Enfin, lorsque vous envoyez un courrier électronique chiffré, soyez assuré qu’une copie — chiffrée sur votre clé publique — sera placée dans votre dossier Courrier envoyé.

## 4.1 Chiffrement des messages avec Mailvelope

À l’aide du navigateur sur lequel vous avez installé Mailvelope, connectez-vous à un compte de messagerie Web avec lequel Mailvelope a été configuré pour fonctionner, puis commencez à rédiger un nouveau message et suivez les étapes ci-dessous :

**Étape 1**. Remplissez les champs **À :**, **Cc :** et ** Object :**, comme d’habitude :

![](mailvelope-all-en-v01-017.png)

**Note :** Si vous ne voyez pas le bouton Mailvelope dans le coin supérieur droit de la zone de message, veuillez vous reporter à la section ci-dessus *Configuration de Mailvelope pour fonctionner avec votre fournisseur de messagerie Web*.

**Étape 2**. **Cliquez** sur le bouton Mailvelope dans le coin supérieur droit de la zone de message pour ouvrir la fenêtre **Envoyer un message**.

![](mailvelope-all-en-v01-018.png)

**Étape 3**. **Tapez** votre message.

**Important :** *Si vous souhaitez chiffrer un message, vous devez le saisir dans la fenêtre spéciale **Envoyer un courriel** de Mailvelope, plutôt que dans la zone de texte normale affichée par votre interface de messagerie Web.* Sinon, votre fournisseur de messagerie Web peut enregistrer des brouillons inachevés pendant que ovus écrivez, sans que vous le sachiez.

Toutes les adresses courriel des champs **À :**, **Cc :** et **Cci :** seront copiées dans le champ *destinataires* de la fenêtre *Envoyer un courriel* de Mailvelope. Votre message sera chiffré sur toutes les clés publiques associées aux adresses indiquées ici (ainsi que sur votre propre clé publique). Vous pouvez ajouter ou supprimer manuellement une adresse dans la fenêtre *Envoyer un courriel*. Si ’une de ces adresses est **marquée en rouge**, cela signifie que vous n’avez pas de clé publique pour ce destinataire et vous ne pourrez pas envoyer le message à moins que vous ne supprimiez ce destinataire ou obteniez sa clé publique.

**Note :** En raison du fonctionnement d’OpenPGP, vous ne devez pas vous fier au champ **Cci** pour masquer l’existence de certains destinataires à d’autres destinataires.

**Étape 3**. Lorsque vous avez terminé de sélectionner les destinataires et de composer votre message, **cliquez sur [Chiffrer]**. Votre message sera chiffré et transféré dans la zone de message normale de votre messagerie Web.

![](mailvelope-all-en-v01-019.png)

**Étape 4**. **Cliquez sur [Envoyer]**.


## 4.2 Déchiffrement des messages avec Mailvelope

À l’aide du navigateur sur lequel vous avez installé Mailvelope, connectez-vous à un compte de messagerie Web avec lequel Mailvelope a été configuré pour fonctionner, puis ouvrez un message chiffré qui vous a été envoyé et suivez les étapes ci-dessous :

Mailvelope détectera automatiquement si un message entrant est chiffré. Il affichera l’icône Mailvelope sur le message chiffré, comme indiqué ci-dessous

![](mailvelope-all-en-v01-020.png)

**Étape 1**. **Cliquez** l’icône Mailvelope pour activer l’écran de mot de passe.

**Étape 2**. **Tapez** la phrase secrète que vous avez choisie lors de la génération de votre paire de clés

![](mailvelope-all-en-v01-021.png)

**Important :** Si vous cochez la case *Mémoriser temporairement le mot de passe*, Mailvelope gardera votre phrase secrète pendant 30 minutes. (Vous pouvez modifier cette durée dans les options de Mailvelope.) Nous vous recommandons de décocher cette case, sauf si vous êtes sur le point de déchiffrer de nombreux messages.

**Étape 3**. **Cliquez** sur **[OK]** pour déchiffrer le message.

![](mailvelope-all-en-v01-022.png)

**Note :** Si Mailvelope affiche un message disant : *Erreur ! Aucune clé privée trouvée pour ce message*, cela signifie que l’expéditeur n’a pas chiffré ce message sur votre clé publique (et peut-être même qu’il ne *possède* pas votre clé publique). Vous ne pourrez pas déchiffrer le message. Contactez l’expéditeur et demandez-lui de renvoyer le message chiffré sur votre clé. Vous pouvez également lui envoyer votre clé et lui proposer de vérifier votre empreinte numérique.

**Important** : En règle générale, il est pas déconseillé de créer des copies non chiffrées des messages chiffrés ou des pièces jointes et de les stocker sur votre ordinateur.

## 4.3 Signature des messages et vérification des signatures avec Mailvelope

En plus de chiffrer les messages sur la clé publique d’une autre personne, Mailvelope peut les *signer* en utilisant votre propre clé privée. De cette manière, les destinataires disposant de votre clé publique peuvent vérifier qu’un message particulier est bien venu de vous et n’a pas été modifié pendant le transit.

Mailvelope ne vous permet pas actuellement de signer et de chiffrer le même message.


### 4.3.1 Signer un message

Pour signer un message, suivez les étapes ci-dessous.

**Étape 1**. Composez un message dans la fenêtre *Envoyer un courriel* de Mailvelope, comme indiqué ci-dessous :

![](mailvelope-all-en-v01-029.png)

**Étape 2**. **Cliquez** sur **[Signer]**.

![](mailvelope-all-en-v01-030.png)

**Étape 3**. **Sélectionnez** une clé privée à utiliser lors de la signature du message.

**Étape 4**. **Cliquez** sur **[OK]**.

**Étape 5**. **Tapez** la phrase secrète de la clé que vous avez sélectionnée.

![](mailvelope-all-en-v01-031.png)

Notez que nous avons désélectionné l’option *Mémoriser le mot de passe temporairement*.

**Étape 6**. **Cliquez** sur **[OK]**.

Le message signé sera copié dans la zone de message de votre courrier Web, comme indiqué ci-dessous :

![](mailvelope-all-en-v01-032.png)

**Important :** Lorsque vous signez un courrier électronique, celui-ci ne sera pas chiffré. Notez que vous pouvez toujours lire le contenu du message ci-dessus. Le bloc de texte *en dessous* du message est la signature numérique. Ne modifiez pas le message avant de l’envoyer. Si vous le faites, les destinataires seront informés que votre signature est invalide.

**Étape 7**. **Cliquez** sur **[Envoyer]**.



### 4.3.2 Vérification d’un message signé

Pour vérifier un message signé, suivez les étapes ci-dessous lors de l’affichage du message.

![](mailvelope-all-en-v01-033.png)

**Étape 1**. **Cliquez** sur l’enveloppe avec le sceau rouge qui apparaît sur le message.

Si vous avez la clé publique pour cet expéditeur, une boîte verte doit apparaître au-dessus du message pour vous informer qu’elle a été *signée* par la clé privée correspondante et n’a pas été modifiée en transit.

![](mailvelope-all-en-v01-034.png)

**Important :** Si vous voyez une case rouge indiquant *Signature non valide*, le message peut avoir été falsifié ou envoyé par quelqu’un d’autre. Vous devez contacter la personne dans le champ **De :** en utilisant un autre canal de communication et confirmer qu’elle l’a envoyé.

Si vous voyez une case jaune indiquant *Signé avec une clé inconnue*, cela signifie que vous ne disposez pas d’une clé publique qui correspond à la clé privée utilisée pour signer le message. Vous ne pourrez pas vérifier la signature avant d’avoir obtenu et validé la bonne clé publique.

## 4.4 Chiffrement et déchiffrement de fichiers avec Mailvelope

Mailvelope peut également chiffrer et déchiffrer des fichiers. Les fichiers chiffrés peuvent être attachés aux courriels.

### 4.4.1 Chiffrer et joindre des fichiers

Pour chiffrer un fichier, suivez les étapes ci-dessous à l’aide du navigateur sur lequel vous avez installé Mailvelope.

**Étape 1**. **Cliquez** sur l’icône de verrouillage de Mailvelope dans la barre d’outils de votre navigateur et **sélectionnez** **Options** pour ouvrir l’onglet de navigation **Options Mailvelope**.

**Étape 2**. **Sélectionnez** l’onglet **[Chiffrement de Fichier]**.

**Étape 3**. **Cliquez** sur **Chiffrement** sur le côté gauche.

**Étape 4**. **Cliquez** sur **[+ Ajouter]** pour sélectionner les fichiers que vous souhaitez chiffrer, comme indiqué ci-dessous.

![](mailvelope-all-en-v01-023.png)

Dans cet exemple, nous avons sélectionné un fichier image appelé *picture.png*. Vous pouvez ajouter plusieurs fichiers. Chacune photo sera chiffrée séparément sur les clés publiques que vous avez sélectionnées.

**Étape 5**. **Cliquez** sur **[Suivant]**.

![](mailvelope-all-en-v01-024.png)

**Étape 6**. **Sélectionnez** un correspondant pour qui vous désirez chiffrer le(s) fichier(s) sélectionné(s).

**Étape 7**. **Cliquez** sur **[Ajouter]**.

Dans cet exemple, nous sélectionnons des clés pour Elena et Mansour. **Vous pouvez sélectionner plus d’une personne, y compris vous-même.**

**Étape 8**. **Cliquez** sur **[Chiffrer]**.

![](mailvelope-all-en-v01-025.png)

**Étape 9**. **Cliquez** sur **[Enregistrer tout]** pour enregistrer les fichiers chiffrés.

Les fichiers chiffrés seront enregistrés à l’endroit où votre navigateur enregistre les fichiers téléchargés (généralement dans le dossier *Téléchargements*). Les fichiers chiffrés auront une nouvelle extension, *.asc*. Par exemple, *picture.png* deviendra *picture.png.asc*. Vous pouvez maintenant envoyer les fichiers chiffrés en pièces jointes à l’aide de la fonction de pièce jointe normale de votre fournisseur de messagerie Web.

**Important :** N’oubliez pas que vous avez toujours la version non chiffrée sur votre ordinateur. Veillez donc à envoyer la version chiffrée (celle qui se termine par *.asc*). De plus, rappelez-vous que *le nom de fichier d’origine est toujours visible* et ne sera pas chiffré. Alors choisissez un nom qui ne révèle pas d’informations sensibles.



### 4.4.2 Déchiffrer des fichiers

Pour déchiffrer un fichier, suivez les étapes ci-dessous. Si le fichier chiffré vous a été envoyé en tant que pièce jointe, ces étapes supposent que vous l’avez déjà enregistré quelque part sur votre ordinateur.

**Étape 1**. **Cliquez** sur l’icône de verrouillage de Mailvelope dans la barre d’outils de votre navigateur et **sélectionnez** **Options** pour ouvrir l’onglet de navigation **Options Mailvelope**.

**Étape 2**. **Sélectionnez** l’onglet **[Chiffrement de Fichier]**.

**Étape 3**. **Cliquez** sur **Déchiffrement** sur le côté gauche.

**Étape 4**. **Cliquez** sur **[+ Ajouter]** pour sélectionner les fichiers que vous souhaitez déchiffrer.

![](mailvelope-all-en-v01-026.png)

Vous pouvez sélectionner plusieurs fichiers chiffrés, à condition qu’ils aient tous été chiffrés à l’aide de la même clé publique.

**Étape 5**. **Cliquez** sur **[Suivant]**.

**Étape 6**. **Tapez** la phrase secrète de votre clé privée.

![](mailvelope-all-en-v01-027.png)

Notez que nous avons désélectionné l’option *Mémoriser le mot de passe temporairement*.

**Étape 7**. **Cliquez** sur **[OK]**.

![](mailvelope-all-en-v01-028.png)

**Étape 8**. **Cliquez** sur **[Enregistrer tout]** pour enregistrer les fichiers déchiffrés.

Les fichiers chiffrés seront enregistrés à l’endroit où votre navigateur enregistre les fichiers téléchargés (en général dans le dossier *Téléchargements*).

# FAQ

**Q** : Mailvelope peut-il être installé dans différents navigateurs tels que Safari ou Opéra ?

**A** : Non. À l’heure actuelle, Mailvelope fonctionne uniquement comme extension/module complémentaire dans les navigateurs **Mozilla Firefox** et **Google Chrome ou Chromium**.

**Q** : Pour combien de comptes puis-je générer des paires de clés ?

**A** : Autant que nécessaire.

**Q** : Mailvelope stocke-t-il mes clés privées n’importe où en ligne (par exemple, dans le cloud) ?

**A** : Non, les clés privées sont stockées sur votre ordinateur. Pour **Firefox**, elles se trouvent dans un répertoire de profil, pour **Chrome ou Chromium**, il s’agit d’un répertoire de données utilisateur. Cependant, les clés publiques peuvent être téléchargées sur le serveur de clés Mailvelope.

**Q** : Mailvelope permet-il de créer des clés pouvant fonctionner pendant un temps limité ?

**A** : Pas pour le moment.

**Q** : Mailvelope peut-il être installé sur une version portable d’un navigateur ?

**A** : Oui. Une fois cette opération effectuée, vous pouvez copier le dossier du navigateur contenant l’installation de Mailvelope et toutes les clés sur une clé USB, puis l’utiliser sur un autre ordinateur.
