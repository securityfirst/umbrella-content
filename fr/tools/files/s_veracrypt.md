---
index: 21
title: VeraCrypt
---
Guide pour VeraCrypt
=================

Stockage de Fichiers Sécurisé

**Leçon à lire : [Protection des Fichiers](umbrella://information/protecting-files)**
**Niveau :** Avancé
**Temps requis :** 30-60 minutes

**L’utilisation VeraCrypt vous donnera :**

*   La possibilité de protéger vos fichiers si votre ordinateur ou périphérique de stockage USB est perdu, volé ou confisqué
*   La possibilité d’accéder et de modifier le même ensemble de fichiers sensibles sur les ordinateurs Windows, Mac OS et Linux
*   Un moyen sécurisé pour sauvegarder les fichiers importants

**Téléchargement :** [https://www.veracrypt.fr/en/Downloads.html]((https://www.veracrypt.fr/en/Downloads.html))

**Version utilisée dans ce guide :** 1.16

**Licence :** Logiciel Libre et à Code Source Ouvert

**Configuration requise :**

GNU/Linux (versions 32-bit et 64-bit, kernel 2.6 ou compatible)
Apple Mac OS X 10.7 ou versions plus récentes, opérant la dernière version de [FUSE pour Mac OS](https://osxfuse.github.io/).
Microsoft Windows Server 2003, 2008, 2012 ; XP, Vista, 7, 8, 10

Note : Un compte administrateur requis pour l’installation et créer des volumes


1\. Introduction
================

[**VeraCrypt**](https://www.veracrypt.fr/en/Home.html) est un _logiciel gratuit_ qui vous permet de chiffrer vos fichiers. C’est une version mise à jour du projet TrueCrypt non maintenu et est disponible pour Microsoft Windows, Mac OS et GNU/Linux. Il corrige diverses failles de sécurité qui ont été identifiées dans TrueCrypt.

1.0. Ce que vous devez savoir sur VeraCrypt avant de commencer
------------------------------------------------------------

VeraCrypt protégera vos fichiers en les chiffrant avec une phrase secrète. Il crée une zone protégée, appelée un _volume_, sur votre ordinateur ou périphérique de stockage externe. Ce volume entier vit dans un seul fichier appelé _conteneur_, que vous pouvez ouvrir (ou _monter_) et fermer (ou _démonter_) en utilisant VeraCrypt. Vous pouvez stocker vos fichiers en toute sécurité dans ce conteneur.

VeraCrypt peut également créer et gérer des volumes chiffrés qui occupent _tout_  l’espace sur un périphérique de stockage particulier. Cependant, ce guide se concentre sur l’utilisation des _conteneurs_.

VeraCrypt utilise le _chiffrement à la volée_ pour protéger vos données. Le chiffrement à la volée chiffre de manière transparente les fichiers lors de leur écriture sur un volume et les déchiffre de manière transparente lors de leur lecture. Vous pouvez copier des fichiers vers et depuis un volume VeraCrypt de la même manière que vous les copiez vers et depuis un dossier normal ou un périphérique de stockage USB.

VeraCrypt prend en charge les _volumes chiffrés standard_ et les _volumes cachés_. L’un ou l’autre gardera vos fichiers confidentiels, mais des _volumes cachés_ vous permettent de cacher vos informations importantes derrière des données moins sensibles afin de les protéger même si vous êtes obligé de révéler votre phrase secrète VeraCrypt. Ce guide couvre la création et l’utilisation des _volumes standard_ et des _volumes cachés_.

N’oubliez pas que si vous oubliez votre phrase secrète, vous perdrez l’accès à vos données ! Il n’y a aucun moyen de récupérer une phrase secrète perdue. De plus, gardez à l’esprit que l’utilisation du chiffrement est illégale dans certaines juridictions.

Pour plus d’informations sur VeraCrypt, voir :

*   La [documentation officielle](https://www.veracrypt.fr/en/Documentation.html)
*   La [FAQ officielle](https://www.veracrypt.fr/en/FAQ.html)

1.1 D’autres outils comme VeraCrypt
------------------------------

Éditions complètes de **Windows** puisque **Windows 7** contient l’utilitaire de chiffrement du disque entier **BitLocker**. (Cela inclut Windows 7 Ultimate, Windows 7 Entreprise, Windows 8 Pro, Windows 8 Entreprise et Windows 10 Pro).

Pour **Mac OS**, vous pouvez utiliser l’utilitaire **FileVault** intégré pour le chiffrement du disque entier (ou pour chiffrer uniquement votre répertoire personnel). **Mac OS** possède également un **Utilitaire de disque** qui peut créer des volumes chiffrés sur des périphériques de stockage USB, mais vous ne pourrez accéder à ces volumes que sur un Mac.

**FileVault** (pour **Mac OS**) et **BitLocker** (pour **Windows**) sont des logiciels propriétaires. Par conséquent, la sécurité qu’ils fournissent ne peut pas être vérifiée de manière indépendante. Néanmoins, c’est une bonne idée de les activer si possible. Vous pouvez utiliser **VeraCrypt**, en plus de ces outils intégrés, pour protéger vos fichiers les plus sensibles et les déplacer entre les ordinateurs Linux, Mac OS et Windows.

De nombreuses distributions **GNU Linux**, y compris [**Ubuntu**](http://www.ubuntu.com/), prennent en charge le chiffrement du disque entier en tant que fonctionnalité standard. Nous vous recommandons d’activer le chiffrement du disque entier lorsque vous installez Linux, car il est beaucoup plus facile de le faire maintenant qu’ultérieurement. En outre, vous pouvez utiliser **l’Utilitaire de disque** intégré sur la plupart des distributions Linux pour créer un volume chiffré sur un périphérique de stockage USB. Contrairement à VeraCrypt, cela vous permettra cependant d’accéder uniquement à vos fichiers sur d’autres ordinateurs Linux. Vous pouvez utiliser VeraCrypt pour déplacer des fichiers entre Linux, Mac OS et Windows.

2\. Installation de VeraCrypt
====================

Pour installer VeraCrypt sur votre ordinateur, suivez les étapes ci-dessous :

**Étape 1**. **Double-cliquez** sur le fichier d’installation nommé "VeraCrypt Setup 1.16.exe".

![image](tool_veracrypt1.png)

_Figure 1 : Le programme d’installation VeraCrypt_

Note : Les utilisateurs Mac OS devront télécharger [FUSE pour Mac OS](https://osxfuse.github.io/), un logiciel nécessaire pour opérer VeraCrypt.  

**VeraCrypt** vous demandera si vous souhaitez autoriser le programme d’installation à modifier votre ordinateur, comme indiqué ci-dessous.

![image](tool_veracrypt2.png)

_Figure 2: Écran de Contrôle d’Accès Utilisateur VeraCrypt_

**Étape 2**. **Cliquez** **\[Oui\]** pour exécuter le programme **VeraCrypt Setup**, qui activera l’écran _licence_.

![image](tool_veracrypt3.png)

_Figure 3 : La licence VeraCrypt_

**Étape 3**. **Cochez** la case intitulée _J’accepte les termes de la licence_ pour activer le bouton **\[Suivant\]**, puis **cliquez sur** **\[Suivant\]**. Vous pouvez ensuite choisir si vous voulez _installer_ VeraCrypt ou _extraire_ celui-ci pour l’utiliser en _mode portable_

![image](tool_veracrypt4.png)

_Figure 4 : L’assistant d’installation montrant le mode d’installation par défaut_

*   Mode d’_installation_: Cette option est destinée aux utilisateurs qui n’ont pas besoin de cacher le fait que **VeraCrypt** soit installé sur leur ordinateur et qui souhaitent l’installer **VeraCrypt** sur tout autre ordinateur sur lequel ils ont besoin d’accéder.
*   Mode _Extraction_: Cette option est destinée aux utilisateurs qui souhaitent utiliser une version portable de **VeraCrypt** sur un périphérique de stockage USB plutôt que de l’installer sur un ordinateur. La version portable peut être exécutée sur tout ordinateur Windows sur lequel l’utilisateur possède un compte _Administrateur_.

**IMPORTANT** : Même en mode portable, **VeraCrypt** laisse des traces sur les ordinateurs où il est utilisé. Ces traces ne révéleront pas le contenu des fichiers chiffrés, mais elles peuvent révéler le fait que **VeraCrypt** a été utilisé sur cet ordinateur.

**Note** : Cette section couvre l’_installation_ **VeraCrypt** sur votre ordinateur. Pour en savoir plus sur l’utilisation de **VeraCrypt** en mode portable, voir **VeraCrypt Portable,** ci-dessous.

**Étape 4**. **Cliquez** **\[Suivant\]** et choisissez où installer **VeraCrypt**.

![image](tool_veracrypt5.png)

_Figure 5 : La fenêtre Options d’Installation_

**Étape 5**. **Cliquez** sur **\[Installer\]** pour commencer l’installation de **VeraCrypt** à l’emplacement par défaut sur votre ordinateur, comme indiqué ci-dessous.

![image](tool_veracrypt6.png)

_Figure 6 : Progrès de l’installation VeraCrypt_

Lorsque l’installation est terminée, l’installateur vous en notifiera.

![image](tool_veracrypt7.png)

_Figure 7 : L’installation de VeraCrypt est un succès_

**Étape 6**. **Cliquez** **\[OK\]** pour confirmer la fin de l’installation et envisager de faire un don à ceux qui développent et entretiennent **VeraCrypt**.

![image](tool_veracrypt8.png)

_Figure 8 : Invitation de don VeraCrypt_

**Étape 7** **Cliquez** sur **\[Terminer\]** et envisagez de lire le tutoriel **VeraCrypt**.

![image](tool_veracrypt9.png)

_Figure 9 : Invitation du tutoriel VeraCrypt_

** Étape 8**. **Cliquez** sur l’un des boutons pour terminer l’installation de **VeraCrypt**. Selon vos préférences d’installation, vous pouvez maintenant disposer d’un raccourci **VeraCrypt** sur votre bureau.

![image](tool_veracrypt10.png)

_Figure 10 : Raccourci de l’application VeraCrypt_

**IMPORTANT** : Si vous ne souhaitez pas annoncer le fait que vous avez des fichiers chiffrés sur votre ordinateur, vous pouvez supprimer ce raccourci. Et, si vous disposez d’un logiciel de chiffrement sur votre ordinateur qui pourrait vous poser un _sérieux_ problème, vous devez supprimer **VeraCrypt** entièrement, puis l’extraire sur un périphérique de stockage USB en _mode portable_ (voir ci-dessous).

**Note** : Les utilisateurs sont encouragés à consulter le [Tutoriel du Débutant de **VeraCrypt**](https://www.veracrypt.fr/en/Beginner%27s%20Tutorial.html) après avoir parcouru ce guide.

3\. Création d’un volume standard
==============================

**VeraCrypt** vous permet de créer deux types de volumes chiffrés : les volumes _Cachés_ et les volumes _Standards_.

*   Les _volumes standards_ protègent vos fichiers avec une phrase de passe à saisir pour pouvoir y accéder.
*   Les _volumes cachés_ ont _deux_ phrases de passe. Vous pouvez entrer l’un d’eux pour ouvrir un volume standard leurre dans lequel vous devrez stocker des fichiers moins sensibles que vous êtes prêt à **abandonner** si nécessaire. La saisie de l’autre phrase secrète ouvrira le volume caché contenant vos fichiers réellement sensibles.

Dans cette section, vous apprendrez à créer un volume **standard**. Si vous souhaitez créer un _Volume caché_, vous devez remplir cette section, puis passer à la section **Création d’un volume caché** ci-dessous.

Pour créer un _Volume standard_ avec **VeraCrypt**, procédez comme suit.

**Étape 1**. Lancez **VeraCrypt** (**\[Démarrer\]** \> **\[Programmes\]** \> **\[VeraCrypt\]** \> **\[VeraCrypt\]**) pour ouvrir la fenêtre principale de l’application.

![image](tool_veracrypt11.png)

_Figure 1 : La fenêtre principale de VeraCrypt_

**Étape 2**. **Cliquez** sur **\[Créer un Volume\]** pour activer l’_Assistant de Création de Volume VeraCrypt_

![image](tool_veracrypt12.png)

_Figure 2 : Fenêtre de l’Assistant de Création de Volume_

Un fichier conteneur VeraCrypt est un volume chiffré qui est stocké dans un seul fichier. Ce conteneur peut être renommé, déplacé, copié ou supprimé comme n’importe quel autre fichier. Dans cette section, nous allons créer un fichier conteneur. Veuillez vous référer à la **[Documentation VeraCrypt](https://www.veracrypt.fr/en/Documentation.html)** pour en savoir plus sur les autres options.

**Étape 3.** **Cliquez** sur **\[Suivant\]** pour sélectionner le type de volume que vous souhaitez créer.

![image](tool_veracrypt13.png)

_Figure 3 : Fenêtre du Type de Volume_

La fenêtre de l’_Assistant de Création de Type de Volume VeraCrypt_ vous permet de spécifier si vous souhaitez créer un volume _Standard_ ou _Caché_.

**Note** : Reportez-vous à la section **Création d’un volume caché** pour plus d’informations sur la création d’un volume caché.

**Étape 4**. Assurez-vous que le _Volume Standard VeraCrypt_ est sélectionné et **cliquez** sur **\[Next\]** pour choisir un nom et un emplacement pour votre fichier conteneur VeraCrypt.

![image](tool_veracrypt14.png)

_Figure 4 : Assistant de Création de Volume - Entrée de l’Emplacement du Volume_

**Étape 5**. **Cliquez** sur **\[Sélectionner un Fichier…\]** pour choisir un emplacement.

![image](tool_veracrypt15.png)

_Figure 5 : Spécifiez l’emplacement et le nom du fichier conteneur VeraCrypt que vous allez créer_

**Étape 6**. Choisissez un emplacement et spécifiez un nom pour le fichier _conteneur_ **VeraCrypt** que vous êtes sur le point de créer.

Vous devrez vous rappeler où vous l’avez mis et comment vous le nommer. Dans cette section, nous allons créer notre _conteneur_ dans le **Bureau** et le nommer **Mon Volume**. Si vous souhaitez plutôt créer un volume standard **VeraCrypt** sur un périphérique de stockage USB, accédez simplement au périphérique (plutôt qu’à votre _Bureau_) et entrez un nom de fichier.

**Conseil** : Vous pouvez utiliser n’importe quel nom de fichier ou extension de fichier pour votre _conteneur_. Par exemple, vous pouvez nommer votre fichier conteneur _recettes.doc, _ ou _vacances.mpg_ dans l’espoir qu’un observateur occasionnel pense qu’il s’agit d’un document _Microsoft Word_ ou d’un fichier vidéo. C’est un moyen qui peut vous aider à dissimuler l’existence d’un conteneur **VeraCrypt**, mais cela ne fonctionnera pas contre une personne disposant du temps et des ressources nécessaires pour effectuer une recherche approfondie sur votre appareil.

**Étape 7**. **Cliquez** sur **\[Sauvegarder\]** pour fermer la fenêtre _Spécifier un Chemin d’accès et un Nom de Fichier_ et revenir à la fenêtre _Assistant de Création d’un Volume_.

![image](tool_veracrypt16.png)

_Figure 6 : Assistant de Création de Volume affichant la fenêtre Emplacement du Volume_

**Étape 8**. **Cliquez** sur **\[Suivant\]**pour activer l’écran des _Options de Chiffrement_

![image](tool_veracrypt17.png)

_Figure 7 : Fenêtre des Options de Chiffrement de l’Assistant de Création de Volume_

Ici, vous pouvez choisir une méthode spécifique (ou un _algorithme_) à utiliser pour chiffrer et déchiffrer les fichiers stockés dans votre conteneur **VeraCrypt**. _Les options par défaut étant considérées comme sécurisées,_ vous devriez donc probablement les laisser telles quelles.

**Étape 9**. **Cliquez** sur **\[Suivant\]** et déterminez la taille de votre volume chiffré.

![image](tool_veracrypt18.png)

_Figure 8 : Assistant de Création de Volume affichant la fenêtre Taille du Volume_

La fenêtre _Taille du Volume_ vous permet de spécifier la taille du _conteneur_ que vous êtes sur le point de créer. Dans cette section, nous allons créer un volume de 250 Mo, mais vous voudrez peut-être spécifier une taille différente. Considérez le nombre de fichiers — et, plus important encore, les _types_ de fichiers — que vous souhaitez stocker dans votre volume chiffré. Les fichiers d’image et les vidéos, en particulier, peuvent remplir très rapidement un petit conteneur **VeraCrypt**.

**Conseil** : Si vous pensez que vous souhaitez sauvegarder votre fichier conteneur sur un CD, vous devez choisir une taille de 700 Mo ou moins. Pour une sauvegarde sur DVD, celle-ci ne devrait pas dépasser 4,5 Go. Si vous avez l’intention de télécharger le fichier conteneur sur un service de stockage en ligne, vous devrez déterminer une taille raisonnable en fonction de la vitesse de votre connexion Internet.

**Étape 10**. **Tapez** la taille du volume que vous souhaitez créer. Assurez-vous de sélectionner la valeur correcte pour **Ko** (kilo-octets), **Mo** (mégaoctets), **Go** (gigaoctets) ou **To** (téraoctets). Puis **cliquez** sur **\[Suivant\]** pour choisir une phrase secrète.

![image](tool_veracrypt19.png)

_Figure 9 : Assistant de Création de Volume contenant la fenêtre de Mot de passe de Volume_

**IMPORTANT** : Le choix d’;une phrase secrète forte est l’une des étapes les plus importantes à effectuer lors de la création d’un volume **VeraCrypt**. Plus la phrase secrète est forte, mieux cela sera. Vous n’êtes pas obligé de choisir vos propres phrases secrètes (ni même de vous en souvenir !) si vous utilisez un _gestionnaire de mots de passe_ tel que **KeePassXC**. Veuillez vous reporter à la leçon **[Mots de passe]**(umbrella://information/passwords) et [**Guide KeePassXC**](umbrella://tools/encryption/s_keepassxc.md) pour en savoir plus sur les bonnes pratiques d’une phrase secrète.

**Étape 11**. **Tapez** votre phrase secrète puis **retapez** votre phrase secrète dans le champ _Confirmer_ pour activer le bouton **\[Suivant\]**.

**IMPORTANT** : Le bouton intitulé "Suivant" restera désactivé jusqu’à ce que les deux phrases secrètes que vous avez entrées correspondent. Si votre phrase secrète est faible, vous verrez un avertissement : Pensez à changer votre phrase secrète ! Bien que **VeraCrypt** accepte n’importe quelle phrase secrète, vos données ne seront pas sécurisées, sauf si vous en choisissez une forte.

**Étape 12**. **Cliquez** sur **\[Suivant\]** pour sélectionner un type de système de fichiers.

![image](tool_veracrypt20.png)

_Figure 10 : Assistant de Création d’un Volume présentant l’écran de Format d’un Volume_

**Étape 13**. **Cliquez** sur **\[Format\]**`pour commencer à créer votre volume standard.

**Note :** La valeur par défaut ("FAT") fonctionnera pour la plupart des utilisateurs et est compatible avec les ordinateurs Windows, Mac OS et Linux. Toutefois, si vous souhaitez stocker des fichiers de plus de 4 Go (pour un seul fichier), vous devrez alors sélectionner un type de système de fichiers différent. **NTFS** fonctionnera sur les ordinateurs **Windows** et la plupart des ordinateurs Linux.

VeraCrypt est maintenant prêt à créer un _volume chiffré standard dans un fichier conteneur_. Si vous déplacez votre souris dans la fenêtre de l’_Assistant de Création d’un Volume VeraCrypt_, des données aléatoires seront générées, ce qui contribuera à renforcer le chiffrement.

![image](tool_veracrypt21.png)

_Figure 11 : Barre de progression de l’Assistant de Création d’un Volume_

**VeraCrypt** va maintenant créer un fichier nommé _Mon Volume_ sur le _Bureau_, comme spécifié ci-dessus. Ce fichier contiendra un fichier de **VeraCrypt** de 250 Mo _conteneur du volume standard_, que vous pourrez utiliser pour stocker vos fichiers en toute sécurité. **VeraCrypt** vous permettra de savoir quand cela sera fait.

![image](tool_veracrypt22.png)

_Figure 12 : Le volume a été créé avec succès_

**Étape 14**. **Cliquez** sur **\[OK\]** pour accuser réception du processus de création et revenir à l’assistant de création d’un volume.

![image](tool_veracrypt23.png)

_Figure 13 : Quitter ou créer un nouveau volume chiffré_

**Étape 15**. **Cliquez** sur **\[Quitter\]** pour fermer l’_Assistant de Création d’un Volume VeraCrypt_ et revenir à la fenêtre principale **VeraCrypt**. (Si vous **cliquez** sur **\[Suivant\]**, **VeraCrypt** va commencer à vous guider dans le processus de création d’un autre volume chiffré.)

Vous devriez désormais voir votre fichier _conteneur_ de 250 Mo où vous l’avez créé.

![image](tool_veracrypt24.png)

_Figure 14 : Fichier conteneur VeraCrypt nouvellement créé sur le Bureau_

4\. Création d’un volume caché
============================

Dans VeraCrypt, un _volume caché_ est stocké dans votre _volume standard_ chiffré, mais son existence est masquée. Même lorsque votre volume standard est _monté_, il n’est pas possible de confirmer l’existence d’un volume caché sans sa phrase secrète (qui est distincte de celle du _volume standard_).

Un _volume caché_ est un peu comme un compartiment secret dans une mallette verrouillée. Vous stockez des fichiers _leurres_ que cela ne vous dérange pas d’avoir confisqué dans la mallette tout en conservant vos fichiers les plus sensibles dans le compartiment secret. L’intérêt d’un _volume caché_ est de cacher sa propre existence, masquant ainsi les fichiers qu’il contient, même si vous êtes obligé de révéler le mot de passe composé de votre _volume standard_. Pour que cette technique soit efficace, vous devez créer une situation dans laquelle la personne exigeant la consultation de vos fichiers sera satisfaite de ce que vous lui montrez. Pour ce faire, vous souhaiterez peut-être implémenter certaines des suggestions suivantes :

*   Mettez des documents confidentiels que vous ne craignez pas d’avoir exposés dans le volume standard. Ces informations doivent être suffisamment sensibles pour que vous ayez intérêt à les conserver dans un volume chiffré.
*   Mettez à jour régulièrement les fichiers du volume standard. Cela créera l’impression que vous utilisez réellement ces fichiers.
*   Sachez que quelqu’un qui demande à voir vos fichiers peut connaître le concept de volumes cachés. Si vous utilisez correctement VeraCrypt, cette personne ne sera pas en mesure de _prouver_ que votre volume caché existe, mais peut le _suspecter_.

Comme mentionné ci-dessus, un _volume caché_ est techniquement stocké dans un _volume standard_. C’est pourquoi VeraCrypt les désigne parfois comme des volumes "internes" et "externes". Heureusement, vous n’avez pas à _monter_ ce dernier pour accéder au premier. Au lieu de cela, VeraCrypt vous permet de créer deux phrases secrètes distinctes : une qui ouvre le _volume standard_ ou externe ("leurre") et une qui ouvre le _volume caché_ ou volume interne.

**Comment Créer un Volume Caché**

Il existe deux manières différentes de créer un _volume caché_. Elles sont toutes deux très similaires au processus de création d’un _volume standard_.

*   Le **mode normal** vous guide tout au long du processus de création d’un _volume standard_ et d’un _volume caché_. (Vous créez un porte-document avec un compartiment secret.)

*   Le **mode direct** suppose que vous avez déjà un _volume standard_ dans lequel vous voulez créer un _volume caché_. (Vous avez déjà le porte-documents, mais vous souhaitez ajouter le compartiment secret.)


Dans cette section, nous allons nous concentrer sur le _mode direct_. Si vous ne possédez pas encore de _volume standard_, suivez simplement les étapes décrites dans la section **Création d’un volume standard** ci-dessus, puis revenez à ce point.

**Étape 1**. Lancez VeraCrypt (**\[Démarrer\]** \> **\[Toutes les Applications\]** \> **\[VeraCrypt\]** \> **\[VeraCrypt\]**) pour ouvrir la fenêtre principale de l’application.

![image](tool_veracrypt25.png)

_Figure 1 : La fenêtre principale de VeraCrypt_

**Étape 2**. **Cliquez** sur **\[Créer un Volume\]** pour activer _l’Assistant de Création d’un Volume VeraCrypt_.

![image](tool_veracrypt26.png)

_Figure 2 : Écran de Création d’un Volume VeraCrypt_

**Étape 3**. **Cliquez** sur **\[Suivant\]** pour accepter l’option par défaut _Créez un fichier conteneur chiffré_.

![image](tool_veracrypt27.png)

_Figure 3 : Création d’un volume caché VeraCrypt_

**Étape 4**. **Cochez** l’option **\[Volume VeraCrypt caché\]**.

**Étape 5**. **Cliquez** sur **\[Suivant\]** pour choisir de créer votre _volume caché_ en utilisant le _mode normal_ ou _mode direct_.

![image](tool_veracrypt28.png)

_Figure 4 : Assistant de Création d’un Volume VeraCrypt - Mode fenêtre_

**Étape 6**. **Cliquez** sur l’option **\[Mode Direct\]**.

**Étape 7**. **Cliquez** sur **\[Suivant\]** pour sélectionner votre _volume standard_ existant.

![image](tool_veracrypt29.png)

_Figure 5 : Écran d’emplacement du volume de VeraCrypt_

**Note :** Assurez-vous que votre _volume standard_ est démonté avant de le sélectionner.

**Étape 8**. **Cliquez** sur **\[Sélectionner un Fichier\]** et localiser votre fichier conteneur de _volume standard_.

![image](tool_veracrypt30.png)

_Figure 6 : Sélection de votre fichier conteneur de volume standard VeraCrypt existant_

**Étape 9**. **Localisez** le fichier conteneur et sélectionnez-le.

Si vous souhaitez créer un conteneur VeraCrypt sur un périphérique de **stockage USB**, accédez simplement au périphérique (plutôt qu’à un dossier de votre ordinateur) avant de choisir un nom de fichier.

**Étape 10**. **Cliquez** sur **\[Ouvrir\]** pour revenir à l’_Assistant de Création de Volume VeraCrypt_.

![image](tool_veracrypt31.png)

_Figure 7 : Conteneur du volume standard VeraCrypt sélectionné_

**Étape 11**. **Cliquez** sur **\[Suivant\]** pour entrer la phrase secrète de votre volume standard existant.

![image](tool_veracrypt32.png)

_Figure 8: Écran de Mot de Passe du Volume Externe VeraCrypt_

**Étape 12**. **Tapez** dans la phrase de passe que vous avez sélectionné lors de la création du _volume standard_ que vous avez sélectionné.

**Étape 13**. **Cliquez** **\[Next\]** pour préparer ce _volume standard_ à l’ajout d’un _volume caché_

![image](tool_veracrypt33.png)

_Figure 9 : Volume standard VeraCrypt préparé_

**Étape 14**. **Cliquez** sur **\[Suivant\]** pour sélectionner les Options de Chiffrement du Volume Caché.

![image](tool_veracrypt34.png)

_Figure 10 : Écran d’Options de Chiffrement du Volume Caché VeraCrypt_

**Étape 15**. **Cliquez** sur **\[Suivant\]**, et vous serez invité à spécifier la taille du _Volume Caché_ que vous êtes sur le point de créer.

**Note** : Laissez les paramètres _Algorithme de Chiffrement_ et _Algorithme de Hachage_ par défaut pour le _Volume Caché_.

![image](tool_veracrypt35.png)

_Figure 11 : Écran de la Taille du Volume Caché VeraCrypt_

Comme lors de la création de votre _volume standard_, tenez compte du nombre et des types de fichiers que vous souhaitez stocker dans votre _volume caché_. Les fichiers image et les vidéos, en particulier, peuvent remplir très rapidement un petit conteneur VeraCrypt. Assurez-vous également de laisser de l’espace pour les fichiers _leurres_ dans votre _volume standard_. Si vous sélectionnez la taille maximale disponible pour le _Volume Caché_, vous ne pourrez plus placer de fichiers dans le _volume standard_ existant. (Dans cette section, nous allons créer un _volume caché_ de 200 Mo dans un _volume standard_ de 250 Mo. Cela laissera environ 50 Mo d’espace pour les fichiers _leurres_.)

**Étape 16**. **Tapez** la taille du volume que vous souhaitez créer. Assurez-vous de sélectionner la valeur correcte pour **Ko** (kilo-octets), **Mo** (mégaoctets), **Go** (gigaoctets) ou **To** (téraoctets).

**Étape 17**. **Cliquez** sur **\[Suivant\]** pour choisir une phrase secrète pour votre _volume caché_.

![image](tool_veracrypt36.png)

_Figure 12 : Écran de création d’un Mot de passe pour le Volume Caché VeraCrypt_

Vous devez maintenant choisir un mot de passe pour le _volume caché_ qui est _différent_ de celui que vous avez choisi pour votre _volume standard_. Encore une fois, rappelez-vous de choisir une phrase secrète forte. Veuillez vous reporter à la leçon **[Mots de passe]** (umbrella://information/passwords) pour en savoir plus.

**Conseil** : Si vous utilisez un _gestionnaire de mots de passe_ tel que **KeePassXC** et que vous souhaitez faire pression sur le contenu de votre conteneur **VeraCrypt**, vous pouvez stocker la phrase secrète de votre _volume standard_ (leurre) dans **KeePassXC**, mais vous devez mémoriser la phrase secrète de votre _volume caché_. Dans le cas contraire, lorsque vous donnerez votre phrase secrète **KeePassXC**, vous pourrez également révéler votre mot de passe secrète du _volume caché_.

**Étape 18**. **Choisissez** une phrase secrète et **tapez** la deux fois.

**Étape 19**. **Cliquez** sur **\[Suivant\]** pour activer l’écran de _Formatage du Volume Caché_.

![image](tool_veracrypt37.png)

_Figure 13 : écran de Format du Volume Caché VeraCrypt_

**Étape 20**. **Cliquez** sur **\[Formater\]** pour formater le volume caché.

**Note :** La valeur par défaut ("FAT") fonctionnera pour la plupart des utilisateurs et est compatible avec les ordinateurs Windows, Mac OS et Linux. Toutefois, si vous souhaitez stocker des fichiers de plus de 4 Go (pour un seul fichier), vous devrez alors sélectionner un type de système de fichiers différent. **NTFS** fonctionnera sur les ordinateurs Windows et la plupart des ordinateurs Linux.

**VeraCrypt** est maintenant prêt à créer un _volume chiffré standard dans un fichier conteneur_. Si vous déplacez votre souris sur la fenêtre de _l’Assistant de Création de Volume VeraCrypt_, des données aléatoires seront générées, ce qui contribuera à renforcer le chiffrement.

![image](tool_veracrypt38.png)

_Figure 14 : Progression du Format du Volume Caché VeraCrypt_

Lorsque VeraCrypt est terminé, un avertissement s’affichera concernant la protection des fichiers de votre _volume caché_ lors de l’ajout de contenu à votre _volume standard_.

![image](tool_veracrypt39.png)

_Figure 15 : Message d’avertissement relatif à la protection du Volume Caché VeraCrypt_

**IMPORTANT** : Cet avertissement est lié à la manière dont VeraCrypt masque l’existence de votre _volume caché_ (interne). Normalement, lorsque vous ouvrez votre _volume standard_ (externe), VeraCrypt et Windows vont _penser_ qu’il occupe tout l’espace disponible dans votre fichier _conteneur_ chiffré. Environ 250 Mo dans cet exemple. (En fait, nous avons créé un _volume caché_ de 200 Mo et avons laissé environ 50 Mo de fichiers leurres dans notre _volume standard_.) VeraCrypt ne peut pas vous avertir si vous essayez de copier un fichier de 60 Mo dans ce _volume standard_ de 50 Mo. En effet, si il vous _avertissait_, il indiquerait à un observateur que vous aviez de la place pour un _volume caché_. Au lieu de cela, il vous permettra de copier ce fichier de 60 Mo. Et, en faisant cela, _il supprimera ou corrompra les fichiers de votre volume caché._

En d’autres termes, cette conception est basée sur l’hypothèse que vous préférez _perdre_ le contenu de votre _volume caché_ plutôt que de révéler son existence.

Ainsi, chaque fois que vous souhaitez ajouter des fichiers leurres à votre volume standard, vous devez cocher la case _protéger le volume caché contre les dommages..._ et saisir à la fois votre phrase secrète du _volume caché_ et votre phrase secrète du _volume standard_. Si vous activez cette fonctionnalité, VeraCrypt pourra vous avertir si vous essayez de copier trop de données dans votre volume externe. (Clairement, la saisie des deux mots de passe devant quelqu’un d’autre révélera l’existence de votre _volume caché_, c’est donc quelque chose que vous ne devriez faire qu’en privé ou en compagnie de ceux en qui vous avez confiance.)

Les étapes spécifiques nécessaires pour modifier le contenu de votre _volume standard_ sont décrites plus en détail dans la section ci-dessous, **Protection de votre volume caché lors de la modification du contenu de votre volume externe**.

**Étape 21**. **Cliquez** sur **\[OK\]** pour terminer la création de votre _volume caché_.

![image](tool_veracrypt40.png)

_Figure 16 : Écran de Création du Volume Caché VeraCrypt_

**Étape 22**. **Cliquez** sur **\[OK\]** pour revenir à la fenêtre principale de VeraCrypt.

Vous pouvez maintenant stocker des fichiers dans votre _volume caché_. Ils resteront indétectables même pour les personnes ayant obtenu la phrase de passe pour votre _volume standard_.

5\. Utilisation de votre volume VeraCrypt
===============================

Cette section de ce guide explique comment utiliser les volumes standard et caché de VeraCrypt sous Windows.

5.1. Montage d’un volume
----------------------

Dans VeraCrypt, _monter_ un volume consiste à le rendre disponible. Lorsque vous montez un volume avec succès, il s’affiche comme un périphérique de stockage portable connecté à votre ordinateur. Vous pouvez utiliser ce disque comme d’habitude pour accéder, créer, modifier ou supprimer des fichiers et des dossiers. Lorsque vous avez fini de l’utiliser, vous pouvez le démonter et le nouveau disque disparaîtra. Vous montez un volume caché de la même manière qu’un volume standard. En fonction du mot de passe que vous entrez, VeraCrypt déterminera s’il faut monter le volume standard ou caché.

Pour monter votre volume, procédez selon les étapes suivantes :

**Étape 1.** Lancez VeraCrypt (**Démarrer** \> **Toutes les applications** \> **VeraCrypt** \> **VeraCrypt**) pour ouvrir la fenêtre principale de l’application.

**Étape 2.** **Sélectionnez** un lecteur dans la liste de la fenêtre principale **VeraCrypt**.

![image](tool_veracrypt41.png)

_Figure 1 : La fenêtre principale de VeraCrypt avec un lecteur disponible sélectionné_

**Note** : Dans _Figure 1_, nous avons choisi de monter notre volume chiffré sur le lecteur _F:_. Vous pouvez choisir l’une des lettres des lecteurs affichées chaque fois que vous montez un volume.

**Étape 3.** **Cliquez** sur **\[Sélectionner un Fichier…\]** et localisez votre fichier _conteneur_ VeraCrypt

![image](tool_veracrypt42.png)

_Figure 2 : Écran de Sélection d’un Volume VeraCrypt_

**Étape 4.** **Sélectionnez** le fichier _conteneur_ que vous voulez monter, puis **cliquez** sur **\[Ouvrir\]** pour revenir à la fenêtre principale **VeraCrypt**. L’emplacement de votre fichier _conteneur_ sera affiché juste à gauche du bouton **\[Sélectionner un Fichier...\]** sur lequel vous avez cliqué précédemment.

![image](tool_veracrypt43.png)

_Figure 3 : La fenêtre principale de VeraCrypt avec un conteneur sélectionné_

**Étape 5.** **Cliquez** sur **\[Monter\]** pour entrer votre phrase secrète.

![image](tool_veracrypt45.png)

_Figure 4 : Écran Entrer un Mot de passe_

**Étape 6.** **Saisissez** votre phrase de passe dans la zone _Mot de passe_.

Si votre _conteneur_ contient un volume caché, choisissez l’une des options ci-dessous :

*   Pour ouvrir un _volume caché_, entrez votre phrase de passe du _volume caché_.

*   Pour ouvrir un _volume standard_ dans un _conteneur_ contenant un _volume caché_ — _tout en étant observé par quelqu’un à qui vous souhaitez cacher l’existence de ce volume_, entrez votre phrase de passe du _volume standard_.

*   Pour ouvrir un _volume standard_ dans un _conteneur_ contenant un _volume caché_ — _afin de modifier vos fichiers "leurres" sans être observé_ — veuillez lire, **Protection de votre volume caché lorsque vous modifiez le contenu de son volume externe.**


**Étape 7.** **Cliquez** sur **\[OK\]** pour commencer à monter le _volume standard_.

Si la phrase secrète que vous avez entrée est incorrecte, **VeraCrypt** vous invitera à la saisir à nouveau. Si elle est correcte, votre volume chiffré sera monté comme suit :

![image](tool_veracrypt44.png)

_Figure 5 : La fenêtre principale de VeraCrypt affichant le volume nouvellement monté_

**Étape 8.** Entrez dans le volume monté

Il existe deux manières d’entrer un volume monté :

1.  **Double-cliquez** sur l’entrée en surbrillance dans la fenêtre principale de **VeraCrypt**, comme indiqué dans la _Figure 5_ ci-dessus.
2.  **Double-cliquez** sur la lettre du lecteur correspondant (ici, nous utilisons _F:_) dans _Ce PC_, comme indiqué dans _Figure 6_ ci-dessous.

![image](tool_veracrypt46.png)

_Figure 6 : Accès au volume VeraCrypt via "Ce PC"_

Le volume ci-dessous est vide. Une fois que vous avez stocké des fichiers, ils seront accessibles (et modifiables) à chaque ouverture du volume.

![image](tool_veracrypt47.png)

_Figure 7 : À l’intérieur du volume VeraCrypt monté_

Ce disque virtuel se comporte comme un périphérique de stockage externe, à la différence qu’il est entièrement chiffré. Vous pouvez copier des fichiers depuis et vers comme vous le feriez pour un périphérique de stockage USB. En les faisant glisser, par exemple, ou en les enregistrant directement dans le volume à partir d’une autre application. Les fichiers sont automatiquement chiffrés lorsque vous les copiez, les déplacez ou les enregistrez sur ce disque virtuel. De plus, lorsque vous déplacez un fichier _en dehors_ du volume VeraCrypt, il est automatiquement déchiffré. Si votre ordinateur est éteint ou s’éteint subitement, le volume chiffré reste inaccessible jusqu’à ce qu’il soit remonté.

**IMPORTANT :** Lorsque votre volume VeraCrypt est monté, les fichiers qu’il contient ne sont pas protégés et sont librement accessibles à toute personne ayant accès à votre ordinateur. Pour protéger vos fichiers sensibles, vous devez démonter votre volume VeraCrypt lorsque vous ne l’utilisez pas. Gardez cela à l’esprit lorsque vous quittez votre ordinateur et dans des circonstances où vous faites face à un risque accru de confiscation ou de vol. Laisser vos volumes chiffrés montés revient à posséder un coffre-fort et à laisser la porte grande ouverte. Si vous arrêtez, redémarrez ou éteignez votre ordinateur, votre volume chiffré sera inaccessible jusqu’à ce qu’il soit remonté. Vous voudrez peut-être vous entraîner à l’une de ces choses le plus rapidement possible.

**Conseil :** Fermer simplement la fenêtre principale en cliquant sur **\[Exit\]** ne suffit pas pour quitter complètement l’application.

5.2. Démontage d’un volume
-------------------------

Dans VeraCrypt, démonter un volume revient à le rendre indisponible. Pour démonter un volume et vous assurer que personne ne pourra accéder aux fichiers qu’il contient sans connaître la phrase de passe appropriée, procédez comme suit :

**Étape 1**. **Sélectionnez** le volume dans la liste des volumes montés dans la fenêtre principale **VeraCrypt**.

![image](tool_veracrypt48.png)

_Figure 1 : Sélection du Volume Standard à démonter_

**Étape 2**. **Cliquez** sur **\[Démonter\]** pour démonter le volume **VeraCrypt**.

Pour récupérer un fichier stocké dans votre volume standard une fois que vous l’avez fermé ou démonté, vous devez le remonter.

**IMPORTANT** : Assurez-vous de démonter votre volume **VeraCrypt** avant :

*   Pour supprimer le périphérique de stockage USB externe sur lequel votre _conteneur_ est stocké (si vous avez choisi de le conserver)
*   Pour mettre votre ordinateur en mode _Veille_ ou _Hibernation_
*   Laisser votre ordinateur sans surveillance
*   Pour entrer dans une situation dans laquelle votre ordinateur est plus susceptible que d’habitude d’être perdu, volé ou confisqué

**Étape 3**. **Faites un clic droit** sur l’icône de la _Barre de tâche_ **VeraCrypt** — dans le coin inférieur droit de votre bureau Windows — et sélectionnez **\[Quitter\]** pour quitter complètement **VeraCrypt**.

![image](tool_veracrypt49.png)

_Figure 2 : Quitter VeraCrypt proprement avec l’icône de la barre de tâche_

**Conseil**. Lorsque vous utilisez la version installée de **VeraCrypt** (par opposition à la version portable), fermer simplement la _fenêtre principale_ en cliquant sur **\[Quitter\]** ne suffit pas pour quitter complètement l’application.

5.3. Protection de votre volume caché lors de la modification du contenu de son volume externe
----------------------------------------------------------------------------------

Comme indiqué dans la section **Création d’un volume caché**, lorsque vous montez un volume **VeraCrypt**, vous pouvez choisir de _Protéger le volume caché contre les dommages causés par l’écriture sur le volume externe_. Cela vous permet d’ajouter de nouveaux fichiers "leurres" à votre volume standard sans risque de suppression ou de corruption accidentelle du contenu de votre volume caché. Vous ne devez pas activer la fonction _Protéger le volume caché_ lorsque vous essayez de cacher l’existence de votre _volume caché_ à quelqu’un qui vous oblige à entrer votre phrase de passe leurre, ce qui vous obligera à entrer les _deux_ mots de passe (ce qui est une indication suffisamment claire que vous avez un _volume caché_ quelque part).

Cependant, lors de la mise à jour de vos fichiers leurres en privé, vous devez _toujours_ activer cette fonctionnalité. Et ne vous inquiétez pas, la _case se désactive automatiquement une fois le volume démonté_.

Pour utiliser la fonctionnalité _Protéger le volume caché_, procédez comme suit :

**Étape 1**. **Sélectionnez** un lecteur à partir de la liste dans la fenêtre principale de **VeraCrypt**

![image](tool_veracrypt50.png)

_Figure 1 : La fenêtre principale de VeraCrypt avec un lecteur disponible sélectionné_

**Note** : Dans _Figure 1_, nous avons choisi de monter notre volume chiffré sur le lecteur _F:_. Vous pouvez choisir l’une des lettres des lecteurs affichées chaque fois que vous montez un volume.

**Étape 2.** **Cliquez** sur **\[Sélectionner un Fichier…\]** et localisez votre fichier _conteneur_ VeraCrypt

![image](tool_veracrypt51.png)

_Figure 2 : L’écran de Sélection d’un Volume VeraCrypt_

**Étape 3.** **Sélectionnez** le fichier _conteneur_ que vous voulez monter, puis **cliquez** sur **\[Ouvrir\]** pour revenir à la fenêtre principale **VeraCrypt**. L’emplacement de votre fichier _conteneur_ sera affiché juste à gauche du bouton **\[Sélectionner un Fichier...\]** sur lequel vous avez cliqué précédemment.

![image](tool_veracrypt52.png)

_Figure 3 : La fenêtre principale de VeraCrypt avec un conteneur sélectionné_

**Étape 4.** **Cliquez** sur **\[Monter\]** pour ouvrir l’écran _Entrer le Mots de passe_

![image](tool_veracrypt53.png)

_Figure 4 : Écran Entrer un Mot de passe_

**Étape 5.** **Tapez** votre phrase de passe du **volume externe** dans la zone _Mot de passe_, comme si vous alliez le monter normalement, **mais ne cliquez pas sur \[OK\]**

**Étape 6.** **Cliquez** sur **\[Options de Montage...\]**, ce qui vous permettra de protéger votre _volume caché_ tout en modifiant le contenu de votre _volume standard_

![image](tool_veracrypt54.png)

_Figure 5 : Écran des Options de Montage de VeraCrypt_

**Étape 7.** **Cochez ** la case intitulée _Protéger le volume caché des dommages causés par l’écriture sur le volume externe_

**Étape 8.** **Tapez** votre phrase de passe du _volume caché_ où cela est indiqué

**Étape 9.** **Cliquez** sur **\[OK\]** pour revenir à l’invite du mot de passe.

![image](tool_veracrypt55.png)

_Figure 6 : Écran Entrer le Mot de passe de VeraCrypt avec le volume caché protégé_

**Étape 10.** **Cliquez** sue **\[OK\]** pour monter votre _volume standard_ tout en protégeant votre _volume caché_ contre es dommages accidentels. VeraCrypt vous fera savoir quand cela est fait.

![image](tool_veracrypt56.png)

_Figure 7 :  Écran VeraCrypt affichant le "Volume caché est désormais protégé"_

**Étape 11.** **Cliquez** sur **\[OK\]** pour revenir à la fenêtre principale de VeraCrypt.

![image](tool_veracrypt57.png)

_Figure 8 :  Écran VeraCrypt affichant le "Volume caché est désormais protégé"_

**Étape 12.** Entrez le volume monté

Comme lors du montage normal d’un volume, il existe deux manières d’entrer un volume monté :

1.  **Double-cliquez** sur l’entrée en surbrillance dans la fenêtre principale de **VeraCrypt**, comme indiqué dans la _Figure 8_ ci-dessus.
2.  **Double-cliquez** sur la lettre du lecteur correspondant (ici, nous utilisons _F:_) dans _Ce PC_

Le volume ci-dessous est vide. Mais, une fois que vous avez stocké des fichiers "leurres" dans votre _volume standard_, ils seront accessibles à chaque fois que vous le monterez. Et, si vous avez protégé votre _volume caché_ avec les étapes ci-dessus, vous pourrez ajouter ou modifier des fichiers.

![image](tool_veracrypt58.png)

_Figure 9 : À l’intérieur du volume standard VeraCrypt monté avec un volume caché protégé_

**Lorsque vous avez terminé de modifier le contenu de votre volume standard, vous pouvez le démonter en suivant les étapes habituelles** décrites à la section **Démontage d’un volume** ci-dessus. Et, la prochaine fois que vous monterez un volume, la _Protection du volume caché contre les dommages causés par l’écriture sur le volume externe_ sera _décoché_ par défaut.

6\. Gestion de votre conteneur VeraCrypt
=====================================

6.1. Importation d’un contenu à partir d’un volume TrueCrypt
----------------------------------------------

**VeraCrypt** peut monter des volumes **TrueCrypt**. Étant donné que **TrueCrypt** n’est plus mis à jour, vous devez déplacer vos fichiers vers un volume **VeraCrypt** dès que possible. Le moyen le plus simple de le faire est de :

1.  Créer un nouveau volume **VeraCrypt** de la taille de votre volume **TrueCrypt** existant (ou plus grand que celui-ci),
2.  Ouvrez les deux volumes en même temps, et
3.  Copiez tout depuis le volume **TrueCrypt** vers le volume **VeraCrypt**

Pour le premier élément ci-dessus, voir **Création d’un volume standard** (et, le cas échéant, ** d’un volume caché**. Cette section suppose que vous disposez déjà d’un ou de plusieurs volumes **VeraCrypt** de taille appropriée. Les étapes ci-dessous concernent le processus de déplacement de fichiers d’un _volume standard_ **TrueCrypt** vers un _volume standard_ **VeraCrypt** déjà monté. Si vous avez des fichiers dans les _deux_, le _volume standard_ et le _volume caché_ d’un conteneur **TrueCrypt**, assurez-vous simplement que vos volumes **VeraCrypt** sont suffisamment volumineux, puis suivez les étapes suivantes deux fois — une fois pour chaque volume.

Lorsque la _fenêtre principale_ de **VeraCrypt** est ouverte et que votre nouveau volume **VeraCrypt** est monté, procédez comme suit :

![image](tool_veracrypt59.png)

_Figure 1 : Fenêtre principale de VeraCrypt montrant un volume monté_

**Étape 1**. **Cliquez** sur une lettre de lecteur qui n’est pas déjà prise par un volume **VeraCrypt** monté

**Étape 2.** **Cliquez** sur **\[Sélectionner un Fichier…\]** pour choisir votre _conteneur_ **TrueCrypt**

![image](tool_veracrypt60.png)

_Figure 2 : Sélection d’un conteneur TrueCrypt_

**Étape 3**. **Naviguez** vers votre conteneur **TrueCrypt**

**Étape 4**. **Cliquez** sur **\[Ouvrir\]** pour revenir à la _fenêtre principale_

![image](tool_veracrypt61.png)

_Figure 3 : Fenêtre principale de VeraCrypt avec un conteneur TrueCrypt sélectionné_

**Étape 5**. **Cliquez** sur **\[Monter\]** afin d’entrer votre phrase de passe pour votre volume **TrueCrypt**

![image](tool_veracrypt62.png)

_Figure 4 : Écran de mot de passe VeraCrypt en mode TrueCrypt_

**Étape 6**. **Cochez** la case **Mode TrueCrypt**

**Étape 7**. **Tapez** la phrase de passe de votre volume TrueCrypt

**Étape 8**. **Cliquez** sur **\[OK\]** pour revenir à la _fenêtre principale_

![image](tool_veracrypt63.png)

_Figure 5 : Fenêtre principale de VeraCrypt avec les deux volumes montés_

**Étape 9**. **Double-cliquez** sur la lettre du lecteur correspondant à votre volume **TrueCrypt** monté pour la saisir.

![image](tool_veracrypt64.png)

_Figure 6: À l’intérieur du volume TrueCrypt monté_

**Étape 10**. Retour à la _fenêtre principale_

![image](tool_veracrypt65.png)

_Figure 7 : Fenêtre principale de VeraCrypt avec les deux volumes montés_

**Étape 11**. **Double-cliquez** sur la lettre du lecteur de votre conteneur **VeraCrypt** monté pour la saisir.

![image](tool_veracrypt66.png)

_Figure 8 : Volumes TrueCrypt et VeraCrypt montés et affichés côte à côte_

**Étape 12**. **Sélectionnez** le contenu de votre volume **TrueCrypt** et faites-le glisser vers la fenêtre représentant votre volume **VeraCrypt**.

![image](tool_veracrypt67.png)

_Figure 9 : Contenu d’un volume TrueCrypt copié sur un volume VeraCrypt_

Une fois vos fichiers copiés, vous devez _démonter_ les deux volumes.

**Étape 13**. Retour à la _fenêtre principale_ de **VeraCrypt**

![image](tool_veracrypt68.png)

_Figure 10 : Fenêtre principale de VeraCrypt_

**Étape 14**. **Sélectionnez** la lettre du lecteur de votre volume **TrueCrypt** monté

**Étape 15**. **Cliquez** sur **\[Démonter\]** pour démonter votre volume **TrueCrypt**

![image](tool_veracrypt69.png)

_Figure 11: Fenêtre principale de VeraCrypt_

**Étape 16**. **Sélectionnez** la lettre du lecteur correspondant à votre volume **VeraCrypt** monté

**Étape 17**. **Cliquez** sur **\[Démonter\]** pour démonter votre volume **VeraCrypt**

6.2. Changement d’une ou deux phrases secrètes pour un conteneur
-----------------------------------------------------

Pour changer la phrase de passe d’un _volume_ **VeraCrypt**, commencez à partir de _l’écran principal_ et suivez les étapes ci-dessous. Ces étapes s’appliquent à la fois aux _volumes standards_ et aux _volumes cachés_ dans les _conteneurs_ **VeraCrypt**. Toutefois, si vous souhaitez modifier les _deux_ mots de passe, vous devrez suivre ce processus à deux reprises.

![image](tool_veracrypt70.png)

_Figure 1 : Fenêtre principale de VeraCrypt_

**Étape 1**. **Cliquez** sur **\[Sélectionner un Fichier…\]** pour choisir votre _conteneur_ pour lequel vous désirez changer la phrase de passe

![image](tool_veracrypt71.png)

_Figure 2 : Sélection d’un fichier conteneur dans VeraCrypt_

**Étape 2**. **Sélectionnez** votre _conteneur_ **VeraCrypt**

**Étape 3**. **Cliquez** sur **\[Ouvrir\]** pour revenir à la _fenêtre principale_

![image](tool_veracrypt72.png)

_Figure 3 : Fenêtre principale de VeraCrypt_

**Étape 4**. **Cliquez** sur **\[Volumes\]**

**Étape 5**. **Sélectionnez** sur **\[Modifier le Mot de passe du Volume...\]** comme indiqué ci-dessous

![image](tool_veracrypt73.png)

_Figure 4 : Modification de la phrase de passe d’un volume VeraCrypt_

Ceci activera l’écran **Changer le mot de passe**

![image](tool_veracrypt74.png)

_Figure 5 : Écran de Modification du Mot de passe VeraCrypt_

**Conseil :** Si vous avez à la fois un volume standard et un volume caché dans ce conteneur, VeraCrypt déterminera automatiquement le mot de passe à modifier en fonction de ce que vous entrez dans le champ **\[Mot de passe Actuel\]**. Si vous souhaitez modifier les deux mots de passe, vous devrez suivre ce processus deux fois.

**Étape 6**. **Tapez** votre mot de passe actuel

**Étape 7**. **Tapez** votre nouvelle phrase secrète deux fois

**Étape 8**. **Cliquez** sur **\[OK\]** pour commencer à générer une nouvelle clé.

**Remarque :** Les versions plus anciennes de VeraCrypt peuvent afficher un avertissement concernant votre valeur "Personal Iterations Multiplier (PIM)" même si vous avez choisi une phrase de passe forte. Si vous voyez cet avertissement, vérifiez que votre phrase de passe contient plus de 20 caractères et que la case Utiliser PIM n’est pas cochée. Puis cliquez sur \[Oui\] pour continuer.

![image](tool_veracrypt75.png)

_Figure 6 : Barre de progression du changement de mot de passe VeraCrypt_

Lorsqu’il sera prêt, **VeraCrypt** affichera l’écran _Enrichissement de Pool Aléatoire_.

![image](tool_veracrypt76.png)

_Figure 7 : Écran d’enrichissement de pool aléatoire de VeraCrypt_

**Conseil :** En déplaçant votre souris dans ’écran _Enrichissement de Pool Aléatoire_, vous pouvez augmenter la puissance du chiffrement fourni par **VeraCrypt**.

**Étape 9**. **Cliquez** sur **\[Continuer\]** pour continuer le processus de modification de votre phrase secrète.

![image](tool_veracrypt77.png)

_Figure 8 : Barre de progression du changement de mot de passe VeraCrypt_

**VeraCrypt** vous indiquera quand cela sera fait en générant une nouvelle clé pour votre volume chiffré

![image](tool_veracrypt78.png)

_Figure 9 : La phrase de passe VeraCrypt a été modifiée avec succès_

**Étape 10**. **Cliquez** sur **\[OK\]** pour compléter le processus de modification de votre phrase secrète.

**IMPORTANT :** La modification de votre phrase de passe ne modifie pas la clé de chiffrement utilisée pour protéger vos données. Concrètement, cela signifie que quiconque ayant les trois choses suivantes peut accéder aux fichiers de votre conteneur VeraCrypt _même après que vous ayez modifié sa phrase de passe_ :

*   Une copie de votre "vieux" conteneur VeraCrypt (de _avant_ que vous ayez changé la phrase secrète)
*   La phrase secrète de cet ancien conteneur VeraCrypt
*   Une copie de votre "nouveau" conteneur VeraCrypt (de _après_ que vous ayez changé la phrase secrète)

Donc, **si vous pensez que quelqu’un possède à la fois une copie de votre conteneur et une connaissance de sa phrase de passe, vous devriez faire beaucoup plus que changer votre phrase de passe**. Vous devez plutôt générer un tout nouveau conteneur (avec une nouvelle phrase de passe), puis copier vos fichiers et supprimer l’ancien conteneur.

7\. VeraCrypt Portable
======================

7.1. Différences entre la version installée et la version portable de VeraCrypt
-------------------------------------------------------------------------

En extrayant **VeraCrypt** en _mode portable_, vous pouvez l’utiliser pour protéger vos fichiers sensibles sans installer le logiciel de la manière habituelle sur votre ordinateur. Dans certaines situations, cette approche peut vous aider à cacher le fait que vous utilisez **VeraCrypt**. Cela, à son tour, rendra moins évident le fait que vous stockez des données chiffrées.

Si vous extrayez la version portable de **VeraCrypt** sur un périphérique de stockage USB, ainsi que votre fichier _conteneur_ chiffré, vous pourrez presque accéder à vos fichiers sur un ordinateur Windows. Gardez toutefois à l’esprit que vos périphériques de stockage externes ne sont sécurisés aussi longtemps que les ordinateurs auxquels vous les connectez sont sécurisés. Le déchiffrement de vos fichiers sensibles sur du matériel inconnu peut vous exposer à des logiciels malveillants capables de lire le contenu de votre _volume chiffré_ lorsqu’il est "ouvert" (ou même d’obtenir votre phrase de passe **VeraCrypt** lorsque vous la saisissez).

Il existe très peu de différences entre les versions installées et portables de **VeraCrypt**, la plus importante étant que la version portable ne vous permet pas de chiffrer votre disque système. Cela fonctionne mieux avec les fichiers _conteneurs_ chiffrés.

7.2. Extraction de la version portable de VeraCrypt
-------------------------------------------------

**Note** : Vous devez créer le dossier dans lequel vous allez extraire la version portable de **VeraCrypt** — généralement sur un périphérique de stockage USB ou quelque part sur votre disque dur — avant de l’extraire

**Étape 1**. **Accédez** à l’emplacement où vous souhaitez extraire la version portable de **VeraCrypt**.

**Étape 2**. **Faites un clic droit** pour activer son menu contextuel.

**Étape 3**. **Sélectionnez** l’élément du menu _Nouveau_, puis **sélectionnez** l’élément du sous-menu _Dossier_, comme indiqué ci-dessous

![image](tool_veracrypt79.png)

_Figure 1 : Création d’un dossier sous Windows_

**Étape 4**. **Tapez** un nom pour le dossier dans lequel vous allez extraire **VeraCrypt**

**Étape 5**. **Appuyez** sur _Entrée_ pour finir de nommer le nouveau dossier

![image](tool_veracrypt80.png)

_Figure 2 : Nommer un dossier sous Windows_

**Étape 6**. **Double-cliquez** sur le programme d’installation de **VeraCrypt** pour ouvrir l’écran d’installation.

![image](tool_veracrypt81.png)

_Figure 3 : L’installateur VeraCrypt_

**Étape 7**. **Double-cliquez** sur le programme d’installation **VeraCrypt** pour activer l’écran de Contrôle du Compte d’Utilisateur.

![image](tool_veracrypt82.png)

_Figure 4 : Écran de Contrôle du Compte Utilisateur VeraCrypt_

**Étape 8**. **Cliquez** sur **\[Oui\]** pour charger l’écran de licence.

![image](tool_veracrypt83.png)

_Figure 5 : Écran de licence VeraCrypt_

**Étape 9**. **Cliquez** sur _J’accepte les termes de la licence_

**Étape 10**. **Cliquez** sur **\[Suivant\]** pour activer le programme d’installation.

![image](tool_veracrypt84.png)

_Figure 6 : Écran principal d’installation de VeraCrypt_

**Étape 11**. **Sélectionnez** _Extraire_

**Étape 12**. **Cliquez** sur **\[Suivant\]** pour activer l’écran d’avertissement.

Les deux écrans d’avertissement ci-dessous ne sont que le moyen utilisé par VeraCrypt pour vous dire que vous devrez fermer l’écran de _Contrôle du Compte d’Utilisateur_ (CCU) _à chaque fois que vous lancez la version portable_ de **VeraCrypt**. (Vous n’aurez pas à le faire si vous installez le logiciel normalement.)

![image](tool_veracrypt85.png)

_Figure 7 : Un message relatif à la manière dont la version portable de VeraCrypt installe les pilotes Windows_

**Étape 13**. **Cliquez** sur **\[OK\]** pour activer un autre écran d’avertissement relatif au pilote.

![image](tool_veracrypt86.png)

_Figure 8 : Avertissement concernant la nécessité d’accuser réception d’un avertissement de Contrôle du Compte Utilisateur lors du démarrage de la version portable de VeraCrypt_

**Étape 14**. **Cliquez** sur **\[Oui\]** pour commencer à choisir votre emplacement d’extraction.

![image](tool_veracrypt87.png)

_Figure 9 : Écran des Options d’Extraction_

**Étape 15**. **Cliquez** sur **\[Rechercher\]** pour choisir votre emplacement d’extraction.

![image](tool_veracrypt88.png)

_Figure 10 : Choix de l’emplacement d’extraction de la version portable de VeraCrypt_

Dans ce guide, nous allons extraire la version portable de **VeraCrypt** dans le dossier "VCP" que nous avons créé dans _Étape 1_. Ce dossier se trouve dans un périphérique de stockage USB appelé "Stockage USB (D:)".

**Étape 16**. Recherchez et sélectionnez le dossier dans lequel vous souhaitez extraire la version portable de **VeraCrypt**.

**Étape 17**. **Cliquez** sur **\[OK\]** pour retourner à l’écran des _Options d’Extraction_

![image](tool_veracrypt89.png)

_Figure 11 : Écran des Options d’Extraction après avoir choisi un emplacement_

**Étape 18**. **Cliquez** sur **\[Extraire\]** pour commencer à extraire **VeraCrypt**. Le programme d’installation **VeraCrypt** vous permettra de savoir quand cela sera fait.

![image](tool_veracrypt90.png)

_Figure 12 : Écran de progression de l’extraction du fichier_

![image](tool_veracrypt91.png)

_Figure 13 : La version portable de VeraCrypt a été extraite avec succès_

**Étape 19**. **Cliquez** sur **\[OK\]** pour activer l’invitation de donation

![image](tool_veracrypt92.png)

_Figure 14 : Invite de donation VeraCrypt_

**Étape 20**. **Cliquez** sur **\[Terminer\]** pour terminer l’extraction de la version portable de **VeraCrypt**

**IMPORTANT** : Si vous avez extrait la version portable de **VeraCrypt** sur un périphérique de stockage USB afin de cacher le fait que vous l’utilisez sur votre ordinateur, assurez-vous de **supprimer le programme d’installation** de votre ordinateur.

7.3. Lancement de la version portable de VeraCrypt
------------------------------------------------

**Étape 1**. **Accédez** au dossier où vous avez extrait la version portable de **VeraCrypt**.

**Étape 2**. **Double-cliquez** sur le fichier **VeraCrypt** (_Figure 1_, ci-dessous) ou le fichier **VeraCrypt-x64** (_Figure 2_), selon si votre système Windows est en 32 bits ou 64 bits.

![image](tool_veracrypt93.png)

_Figure 1 : Le démarrage VeraCrypt portable 32 bits_

![image](tool_veracrypt94.png)

_Figure 2 : Le démarrage de VeraCrypt portable 64 bits_

Ceci activera la fenêtre de _Contrôle du Compte Utilisateur_ **VeraCrypt**

![image](tool_veracrypt95.png)

_Figure 2 : Écran de Contrôle du Compte Utilisateur VeraCrypt_

**Étape 3**. **Cliquez** sur **\[Oui\]** pour lancer la version portable de **VeraCrypt**

![image](tool_veracrypt96.png)

_Figure 3 : Fenêtre principale de VeraCrypt_

Vous pouvez maintenant utiliser **VeraCrypt**, comme d’habitude, pour créer, gérer, monter et démonter des _volumes chiffrés_. Lorsque vous quittez la version portable de **VeraCrypt**, elle télécharge ses pilotes Windows et se ferme proprement. **Si vous exécutez la version portable de VeraCrypt à partir d’un périphérique de stockage USB, assurez-vous de fermer vos volumes ouverts et de quitter le programme avant d’éjecter et de retirer le périphérique de stockage.**

**Conseil :** Pour quitter complètement la version _installée_ de **VeraCrypt** — même après avoir cliqué sur **\[Quitter\]** pour fermer la fenêtre principale — vous devez cliquer avec le bouton droit de la souris sur l’icône de _barre de tâche_ et sélectionnez **\[Quitter\]**. La version portable ne nécessite pas cette étape supplémentaire.

FAQ
===

**_Q_** : Est-ce que je vais devoir passer tout mon temps à taper des phrases secrètes dans **VeraCrypt** ?

**_A_** : Non, il vous suffit d’entrer votre phrase de passe une seule fois pour ouvrir un volume chiffré. Après cela, vous pouvez accéder à vos fichiers sans phrase de passe jusqu’à ce que vous fermiez le volume.

**_Q_** : Puis-je désinstaller **VeraCrypt** si je ne le souhaite plus ? Si je le fais, mes fichiers resteront-ils chiffrés ?

**_A_** : Oui. Vous pouvez désinstaller **VeraCrypt** en ouvrant _Terminal_, en tapant `sudo veracrypt-uninstall.sh` et en entrant le mot de passe composé que vous utilisez pour vous connecter à votre ordinateur. Vous pouvez réinstaller ultérieurement **VeraCrypt** pour accéder aux fichiers de vos conteneurs, qui resteront chiffrés et ne seront pas supprimés lorsque vous supprimerez **VeraCrypt**. De même, si vous transférez votre _fichier conteneur_ chiffré sur un autre ordinateur, vous aurez besoin de votre phrase de passe et du programme **VeraCrypt** pour l’ouvrir.

**_Q_** : Quels types d’informations nécessitent un chiffrement ?

**_A_** : Idéalement, vous devez chiffrer tous vos documents, images et autres fichiers contenant des informations confidentielles et sensibles. Et, si votre système d’exploitation le prend en charge, vous devez configurer le _chiffrement du disque entier_ pour que _tous_ vos fichiers soient chiffrés à la mise hors tension de votre ordinateur.

**_Q_** : Quel sera le niveau de sécurité de mes fichiers ?

**_A_** : **VeraCrypt** a été testé et analysé de manière indépendante par des experts en sécurité afin de vérifier son efficacité et de déterminer s’il offre ou non toutes les fonctions qu’il prétend prendre en charge. Les résultats révèlent que **VeraCrypt** offre un très haut niveau de protection. Cependant, le choix d’un mot de passe complexe est essentiel pour la sécurité de vos données.

**_Q_** : Pourquoi devrais-je utiliser un _volume caché_?

**_A_** : Les _volumes standards_ de **VeraCrypt** protègent vos fichiers avec un chiffrement renforcé. Les _volumes cachés_, qui offrent le même niveau de chiffrement, sont conçus pour vous offrir davantage d’options si quelqu’un exige votre phrase de passe **VeraCrypt**. Plutôt que de donner votre phrase de passe du _volume caché_, vous pouvez abandonner votre phrase de passe du _volume standard_. Si on vous le demande, vous pouvez nier que vous avez un _volume caché_. Cependant, pour utiliser cette fonctionnalité correctement, vous devez maîtriser parfaitement votre propre environnement de sécurité, avoir une bonne compréhension du fonctionnement de **VeraCrypt** et un ensemble convaincant de fichiers "leurres" dans votre _volume standard_.

**_Q_** : Comment monter mon _volume standard_ d’origine, plutôt que celui qui est caché ?

**_A_** : Tout dépend de la phrase de passe que vous entrez dans l’écran de mot de passe. Si vous entrez la phrase de passe du _volume standard_, **VeraCrypt** montera le _volume standard_. Si vous entrez la phrase de passe du _volume caché_, **VeraCrypt** montera le _volume caché_. Ainsi, si quelqu’un vous demande d’ouvrir votre conteneur **VeraCrypt**, vous pouvez monter le _volume standard_ et nier l’existence d’un _volume caché_. Dans de bonnes circonstances, cela pourrait suffire à vous tirer d’affaire.

**_Q_** : Est-il possible d’endommager ou de supprimer par inadvertance un _volume caché_?

**_A_** : Oui. Si vous continuez à ajouter des fichiers à votre _volume standard_ jusqu’à ce que vous manquiez d’espace pour votre volume caché, votre _volume caché_ sera endommagé ou détruit. Lorsque vous montez le volume standard, il existe une option que vous pouvez utiliser pour protéger votre _volume caché_ contre les dommages causés lors de la modification du contenu de votre _volume standard_. Vous ne devez pas utiliser cette option lors de l’observation, car elle révèle l’existence d’un _volume caché_.

**_Q_** : Puis-je modifier la taille d’un volume VeraCrypt après l’avoir créé ?

**_A_** : Non. Vous devrez créer un nouveau conteneur avec un volume plus important, puis déplacer vos fichiers depuis l’ancien volume vers le nouveau. Vous pouvez le faire en montant les deux volumes en même temps. Cela s’applique aux volumes standard et cachés.

**_Q_** : Puis-je utiliser des outils tels que **chkdsk** sur le contenu d’un volume monté **VeraCrypt** ?

**_A_** : Les volumes **VeraCrypt** se comportent comme des périphériques de stockage normaux. Il est donc possible d’utiliser n’importe quel outil de système de fichiers pour vérifier/réparer/défragmenter le contenu de tout volume **VeraCrypt** monté.

**_Q_** : Est-il possible de changer la phrase secrète d’un _volume caché_?

**_A_** : Oui. La fonctionnalité de modification de la phrase secrète s"applique aux volumes _standard_ et _caché_. Tapez simplement la phrase secrète du _volume caché_ dans le champ Mot de passe actuel de l’écran de Modification du mot de passe.

*   [**FAQ Officiel de VeraCrypt**](https://www.veracrypt.fr/en/FAQ.html)