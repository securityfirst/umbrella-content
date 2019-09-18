---
index: 6
title: KeePassXC
---
KeePassXC
=========

Gestionnaire de Mot de Passe Sécurisé

** Leçon à lire : [Mots de passe](umbrella://information/passwords/advanced). **
** Niveau** : Débutant
** Temps requis** : 5 minutes à configurer pour une vie d’utilisation de mots de passe forts.
** Publié : ** Avril 2018
** Sources : ** FFÉ, Autodéfense contre la surveillance, [Guide pratique : utiliser KeePassXC](https://ssd.eff.org/fr/module/guide-pratique-utiliser-keepassxc) ; [https://github.com/keepassxreboot/keepassxc/wiki](https://github.com/keepassxreboot/keepassxc/wiki].

** Utiliser KeepassXC vous donnera : **
\* La possibilité d’utiliser de nombreux mots de passe différents sur différents sites et services sans avoir à les mémoriser.

** Télécharger : ** Pour Windows/Mac/Linux : [https://keepassxc.org/download](https://keepassxc.org/download).
** Configuration requise : ** Windows 7 ou supérieur, MacOS X 10.7 ou supérieur, Linux (la plupart des distributions)
** Version utilisée dans ce guide **: KeePassXC 2.2.0 (KeePassXC est une version multiplate-forme du programme KeePass pour Windows uniquement.)
** Licence ** : FOSS (principalement GPLv2)

introduction
------------

KeePassXC est un gestionnaire de mots de passe multi-plateformes qui vous permet de stocker tous vos mots de passe au même endroit. Un gestionnaire de mots de passe est un outil qui crée et stocke des mots de passe pour vous. Vous pouvez donc utiliser de nombreux mots de passe différents sur différents sites et services sans avoir à les mémoriser. Vous n’avez besoin que de mémoriser un mot de passe maître qui vous permet d’accéder à la base de données chiffrée du gestionnaire de mots de passe de tous vos mots de passe.

_Il existe un certain nombre de programmes dont le nom s’apparente à KeePassXC, tels que KeePassX, KeePass et KeePass2. Certains d’entre eux sont basés sur le même code, tandis que d’autres utilisent simplement le même format de base de données. Ce guide recommande_ [_KeePassXC_](https://keepassxc.org/) _parce qu’il est multi-plateforme et développé plus activement que certaines alternatives ._

Note : L’utilisation d’un gestionnaire de mots de passe crée un point d’échec unique et constitue une cible évidente pour les mauvais acteurs ou adversaires. Les recherches suggèrent que de nombreux gestionnaires de mots de passe couramment utilisés comportent des vulnérabilités. Par conséquent, soyez prudent lorsque vous déterminez s’il s’agit du bon outil pour vous.

Comment KeePassXC fonctionne
-------------------

KeePassXC fonctionne avec les bases de données de mots de passe, qui sont des fichiers contenant une liste de tous vos mots de passe. Ces bases de données sont chiffrées lorsqu’elles sont stockées sur le disque dur de votre ordinateur. Donc, si votre ordinateur est éteint et que quelqu’un le vole, il ne pourra pas lire vos mots de passe.

Les bases de données de mots de passe peuvent être chiffrées à l’aide d’un mot de passe maître Étant donné que votre mot de passe maître protège tous vos autres mots de passe, vous devez le renforcer au maximum. (Apprenez à créer des [Mots de passe] forts (umbrella://information/passwords/beginner).)

Utilisation d’un mot de passe maître
-----------------------

Un mot de passe maître agit comme une clé. Pour ouvrir la base de données de mots de passe, vous avez besoin d’un mot de passe maître correct. Sans cela, personne ne peut voir ce qui se trouve dans la base de données de mots de passe. Lorsque vous utilisez un mot de passe maître pour sécuriser votre base de données de mots de passe, tenez compte des points suivants.

*   Ce mot de passe déchiffrera tous vos mots de passe, il doit donc être fort ! Celui-ci devrait être difficile à deviner et long. Plus il est long, moins vous devez vous inquiéter d’avoir des caractères spéciaux, des lettres majuscules ou des chiffres. Alors, faites de votre mot de passe maître un mot de passe. Une phrase de passe est une chaîne de nombreux mots faciles à retenir pour vous mais difficiles à deviner.
*   Vous pouvez créer une phrase de passe principale forte [en utilisant des mots ordinaires et aléatoires](https://www.eff.org/dice). Celles-ci sont plus faciles à mémoriser que des combinaisons non naturelles de symboles et de lettres majuscules. (En savoir plus sur les [Mots de passe](umbrella://information/passwords).)

Débuter avec KeePassXC
------------------------------

Installez KeePassXC et lancez-le. Cliquez sur le menu Fichier et sélectionnez "Créer une nouvelle Base de données". Vous serez invité à enregistrer votre base de données de mots de passe. Notez que vous pouvez déplacer le fichier de base de données de mots de passe plus tard où bon vous semble sur votre disque dur ou sur d’autres ordinateurs. Vous pourrez toujours l’ouvrir à l’aide de KeePassXC et du mot de passe ou du fichier de clés que vous avez spécifié auparavant.

![](tool_keepassxc1._creating_an_account.png)

** _ Qu’est-ce qu’un fichier clé ? _ ** _L’utilisation d’un fichier clé en plus de votre mot de passe maître peut rendre plus difficile le déchiffrage de votre base de données de mots de passe s’ils volent une copie. Vous pouvez utiliser n’importe quel fichier existant en tant que fichier clé. Une image de votre chat, par exemple — peut être utilisée en tant que fichier de clés. Assurez-vous simplement que le fichier que vous choisissez ne sera jamais modifié, car si son contenu est modifié, il ne déchiffrera plus votre base de données de mots de passe. Parfois, l’ouverture d’un fichier dans un autre programme peut suffire à le modifier. Ne l’ouvrez pas, sauf pour déverrouiller KeePassXC. (Cependant, il est prudent de déplacer ou de renommer le fichier clé.) Généralement, un mot de passe maître fort est suffisant. Si vous choisissez d’utiliser un fichier clé en plus de votre mot de passe maître, veillez à le stocker séparément de votre base de données de mots de passe._

Ensuite, une boîte de dialogue apparaît et vous demande de saisir un mot de passe maître et/ou d’utiliser un fichier clé. Cochez la ou les cases appropriées en fonction de votre choix.

Si vous voulez voir le mot de passe que vous tapez (au lieu de le masquer avec des points), cliquez sur le bouton avec l’œil vers la droite.

![](tool_keepassxc2._creating_master_key.png)

Organiser les mots de passe
--------------------

KeePassXC vous permet d’organiser les mots de passe en "Groupes", qui ne sont essentiellement que des dossiers. Vous pouvez créer, supprimer ou éditer des Groupes ou des Sous-groupes en allant dans le menu Groupes de la barre de menu ou en cliquant avec le bouton droit de la souris sur un groupe dans la fenêtre KeePassXC. Le regroupement de mots de passe n’a aucune incidence sur les fonctionnalités de KeePassXC, c’est un outil d’organisation très utile.

Stockage/génération/édition de mots de passe
------------------------------------

Pour créer un nouveau mot de passe ou enregistrer le mot de passe que vous avez déjà, cliquez avec le bouton droit de la souris sur le groupe dans lequel vous souhaitez enregistrer le mot de passe, puis choisissez "Ajouter une Nouvelle Entrée". (Vous pouvez également choisir "Entrées> Ajouter une Nouvelle Entrée" dans la barre de menu.) Pour l’utilisation du mot de passe de base :

*   Entrez un titre descriptif que vous pouvez utiliser pour reconnaître la saisie du mot de passe dans le champ "Titre". Par exemple, il peut s’agir du nom du site Web ou du service auquel le mot de passe est destiné.
*   Entrez le nom d’utilisateur associé à l’entrée du mot de passe dans le champ "Nom d’utilisateur". (S’il n’y a pas de nom d’utilisateur, laissez ce champ vide.)
*   Entrez votre mot de passe dans le champ "Mot de passe". Si vous créez un nouveau mot de passe, cliquez sur l’icône du dé à droite. Vous voudrez peut-être faire cela lorsque vous vous inscrivez pour un nouveau site Web ou lorsque vous remplacez des mots de passe plus anciens et plus faibles par de nouvelles phrases de passe uniques et aléatoires. ” Après avoir cliqué sur l’icône du dé, une boîte de dialogue de génération de mot de passe apparaît. Vous pouvez l’utiliser pour générer un mot de passe aléatoire. Cette boîte de dialogue propose plusieurs options, notamment les types de caractères à inclure et la durée de création du mot de passe.
    *   Notez que si vous générez un mot de passe aléatoire, vous n’avez pas à vous rappeler (ni même savoir !) en quoi consiste ce mot de passe. KeePassXC le stocke pour vous, et chaque fois que vous en aurez besoin, vous pourrez le copier/coller dans le programme approprié. C’est tout l’intérêt d’un gestionnaire de mots de passe — vous pouvez utiliser différents mots de passe longs et aléatoires pour chaque site Web/service, sans même savoir quels sont les mots de passe !
    *   Pour cette raison, vous devez définir le mot de passe aussi longtemps que le service le permettra et utilisera autant de types de caractères différents que possible.
*   Lorsque les options vous conviennent, cliquez sur "Générer" dans le coin inférieur droit pour générer le mot de passe, puis cliquez sur "OK". Le mot de passe aléatoire généré sera automatiquement saisi dans les champs "Mot de passe" et "Répéter". (Si vous ne générez pas de mot de passe aléatoire, vous devrez alors saisir à nouveau le mot de passe choisi dans le champ "Répéter".)
*   Cliquez sur OK. Votre mot de passe est maintenant stocké dans votre base de données de mots de passe. Pour vous assurer que les modifications sont enregistrées, sauvegardez la base de données de mots de passe modifiée en sélectionnant "Fichier> Enregistrer la base de données". (Alternativement, si vous faites une erreur, vous pouvez fermer et ouvrir à nouveau le fichier de la base de données et toutes les modifications seront perdues.)

![](tool_keepassxc3._adding_an_entry.png)

Si vous devez changer/éditer le mot de passe stocké, vous pouvez simplement choisir son groupe, puis double-cliquer sur son titre dans le volet de droite. La boîte de dialogue "Nouvelle Entrée" réapparaîtra.

Utilisation Normale
----------

Pour utiliser une entrée dans votre base de données de mots de passe, cliquez dessus avec le bouton droit de la souris et choisissez "Copier ’Identifiant dans le Presse-papier" ou "Copier le Mot de passe dans le Presse-papier". Accédez à la fenêtre/au site Web où vous souhaitez entrer votre nom d’utilisateur/mot de passe et collez-le dans le champ approprié. (Au lieu de cliquer avec le bouton droit de la souris sur l’entrée, vous pouvez également double-cliquer sur le nom d’utilisateur ou le mot de passe de l’entrée souhaitée. Le nom d’utilisateur ou le mot de passe sera automatiquement copié dans votre presse-papiers.)

![](tool_keepassxc4._viewing_the_database.png)

![](tool_keepassxc5._using_an_entry.png)

Autres Fonctionnalités
--------------

KeePassXC vous permet de :

*   Recherchez votre base de données à l’aide de la zone de recherche (la zone de texte de la barre d’outils de la fenêtre principale de KeePassXC).
*   Triez vos entrées en cliquant sur l’en-tête de la colonne dans la fenêtre principale.
*   "Verrouillez" KeePassXC en choisissant "Outils> Verrouiller les bases de données". Cela vous permet de laisser KeePassXC ouvert, mais votre mot de passe maître (et/ou fichier clé) vous sera demandé avant de pouvoir accéder à nouveau à votre base de données de mots de passe. Vous pouvez également faire en sorte que KeePassXC se verrouille automatiquement après une certaine période d’inactivité. Cela peut empêcher quelqu’un d’accéder à vos mots de passe si vous vous en éloignez ou si vous le perdez. Pour activer cette fonctionnalité sur macOS, choisissez "Préférences> Paramètres" dans le menu, puis cliquez sur les options de sécurité. Cochez ensuite la case "Verrouiller la base de données après une inactivité de \[nombre\] secondes." Sous Linux ou Windows, choisissez "Outils> Paramètres" dans le menu, puis cliquez sur les options de sécurité. Cochez ensuite la case "Verrouiller la base de données après une inactivité de \[nombre\] secondes."

KeePassXC peut également stocker plus que des noms d’utilisateur et des mots de passe. Par exemple, vous pouvez créer des entrées pour stocker des éléments importants tels que les numéros de compte, les clés de produit, les informations sur les grands voyageurs des compagnies aériennes ou les numéros de série. Il n’est pas nécessaire que les données que vous saisissez dans le champ "Mot de passe" soient bien un mot de passe. Entrez simplement ce que vous désirez stocker dans le champ "Mot de passe" au lieu d’un mot de passe réel (et laissez le champ "Nom d’utilisateur" vierge s’il n’y a pas de nom d’utilisateur) et KeePassXC s’en souviendra pour vous en toute sécurité.

Comment Installer l’Extension de Navigateur
------------------------------------

Une extension de navigateur est un composant logiciel qui ajoute des fonctionnalités supplémentaires à votre navigateur Web. L’utilisation de l’extension KeePassXC constitue un moyen pratique pour votre navigateur et votre application KeePassXC de communiquer. Cela vous permettra de sauvegarder rapidement ou de saisir automatiquement les mots de passe sur le Web.

Pour intégrer KeePassXC dans votre navigateur, vous devez :

1.  Activer le protocole HTTP KeePassXC

    Aller dans "Préférences> Paramètres" dans le menu et cliquez sur les options HTTP. Cochez ensuite la case "Activer le protocole HTTP KeePassXC". Cela permet à KeePassXC et à l’extension de navigateur de communiquer.

2.  Télécharger l’extension du navigateur

    Pour Firefox, installer [Passifox](https://addons.mozilla.org/en-US/firefox/addon/passifox/). Pour Chrome, installer [chromeIPass](https://chrome.google.com/webstore/detail/chromeipass/ompiailgknfdndiefoaoiligalphfdae). Une fois l’installation terminée, une petite icône représentant un verrou apparaît dans la barre d’outils de votre navigateur.

    ![](tool_keepassxc6._chromeipass_extension.png)

3.  Connecter l’extension du navigateur à KeePassXC

    Pour que KeePassXC et votre navigateur puissent communiquer, vous devez les connecter en créant une association. Pendant que KeePassXC est en cours d’exécution, ouvrez votre navigateur et cliquez sur l’icône de l’extension KeePass. Cliquez ensuite sur "Connecter".

    Cela ouvrira une boîte de dialogue "Nouvelle demande de dialogue d’association de clés". Donnez à ce nom d’association un nom descriptif tel que Chrome. L’utilisation d’un nom descriptif vous aide à identifier cette association dans le futur.

    ![](tool_keepassxc7._enabling_browser_extension.png)


Maintenant que votre navigateur est connecté à KeePassXC, vous verrez ce message lorsque vous cliquerez sur l’icône d’extension KeePass.

L’utilisation de la saisie automatique peut être préjudiciable à votre vie privée. Pour le désactiver, décochez les paramètres "Remplir automatiquement les informations d’identification uniques" et "Activer la saisie semi-automatique pour les champs de nom d’utilisateur".

C’est prêt ! Maintenant, vous pouvez enregistrer toutes les informations d’identification que vous entrez sur le Web. Vous pourrez également saisir automatiquement vos noms d’utilisateur/mots de passe.

KeePassXC est un logiciel robuste et facile à utiliser. Nous vous recommandons d’explorer ce programme pour apprendre toutes les choses utiles que ce dernier peut faire pour vous.