---
index: 10
title: PGP pour Linux
---
# GUIDE PGP POUR LINUX

## Guide PGP pour Linux
Courriel chiffré pour Linux

**Leçon à lire : [Courriel](umbrella://lesson/courriel)**  
**Configuration requise pour l’ordinateur:** Une connexion Internet, un ordinateur exécutant Linux, un compte de messagerie  
**Version utilisée dans ce guide :**
- Linux : Debian 7.0 ("Wheezy")  
- Mozilla Thunderbird 24.8.1  
- Enigmail 1.6  
- GPG4Win 1.4.18  

**Licence :** Logiciel libre; mélange de licences de logiciels libres  
**Niveau :** Expert  
**Autres lectures :** [https://www.gnupg.org/documentation/guides.html](https://www.gnupg.org/documentation/guides.html)   
**Temps requis :** 30-60 minutes  

**L’utilisation de PGP vous donnera :**
- La possibilité de protéger vos courriels de toute lecture de la part d’inconnu, sauf de leurs destinataires.
- La possibilité de prouver qu’un courriel provient d’une personne en particulier, au lieu d’être un faux message envoyé par un autre expéditeur (il est très facile de créer un courriel). Les deux sont des défenses importantes si vous êtes ciblé pour la surveillance ou la désinformation.

**Note :** Si vous craignez que les courriels chiffrés par PGP ne soient plus sûrs après la détection de vulnérabilités en Mai 2018, consultez la section Efail de notre leçon avancée sur les [courriel](umbrella://lesson/courriel).

### 1.0 Avant de commencer

Pour utiliser Pretty Good Privacy (PGP), vous devez installer un logiciel supplémentaire qui fonctionnera avec votre programme de messagerie actuel. Vous aurez également besoin de créer une clé privée, que vous garderez privée. La clé privée est ce que vous utiliserez pour déchiffrer les courriers électroniques qui vous sont envoyés et pour signer numériquement les courriers électroniques que vous envoyez pour montrer qu’ils proviennent réellement de vous. Enfin, vous apprendrez à distribuer votre clé publique - un petit bloc d’informations que les autres devront connaître avant de pouvoir vous envoyer du courriel chiffré et qu’ils pourront utiliser pour vérifier les courriels que vous leur envoyez.

Ce guide vous montrera comment utiliser PGP avec un système d’exploitation de type Linux à l’aide de Mozilla Thunderbird, un client de messagerie graphique à code source ouvert populaire.

Actuellement, vous ne pouvez pas utiliser directement PGP avec un service de messagerie Web tel que Gmail, Hotmail, Yahoo! Mail ou Outlook Live. Vous pouvez toujours utiliser votre adresse de messagerie Web. vous devrez simplement le configurer avec le programme Thunderbird sur votre ordinateur.

**Notez que les deux bouts de la conversation par courriel doivent utiliser un logiciel compatible PGP pour que cela fonctionne.**

Les gens l’utiliseront normalement uniquement sur leurs propres appareils personnels, pas sur des appareils partagés. Heureusement, PGP est disponible pour la plupart des ordinateurs de bureau et des périphériques mobiles. Vous pouvez leur indiquer ces guides pour les aider à configurer leur propre version.

### 2.0 Installation de Thunderbird, GnuPG et Enigmail 

PGP est une licence libre, ce qui signifie que plusieurs logiciels peuvent l’utiliser. Le logiciel que nous allons utiliser pour PGP s’appelle GnuPG. Nous allons également ajouter une extension à Thunderbird appelé Enigmail, qui vous permettra d’utiliser GnuPGP à partir de Thunderbird. Les instructions suivantes nécessitent un certain confort avec la ligne de commande.

Si vous utilisez une distribution basée sur Red Hat telle que Red Hat ou Fedora Core, ouvrez un terminal et exécutez les commandes suivantes :

_sudo yum install gnupg thunderbird thunderbird-enigmail_

Si vous utilisez une distribution basée sur Ubuntu telle que Ubuntu ou Linux Mint, ouvrez un terminal et tapez ces commandes pour vous assurer que le bon logiciel soit installé :

_sudo apt-get install gnupg thunderbird enigmail_

Si vous utilisez la distribution Debian, vous constaterez que Thunderbird s’appelle "Icedove". Comme Debian en général, ceci est pour des raisons tout à fait raisonnables mais quelque peu obscures. Hormis le nom, il s’agit exactement du même programme : nous ne mentionnerons plus Icedove, mais vous pouvez simplement remplacer "Thunderbird" par Icedove dans la suite de ce guide, et tout devrait toujours fonctionner.

Utilisez cette commande dans le terminal pour l’installer :

_sudo apt-get install gnupg icedove enigmail_

### 2.1 Configuration de Thunderbird

Maintenant que vous avez installé Thunderbird, ouvrez-le comme une autre application sur votre ordinateur (vous pouvez le choisir dans une liste d’applications ou taper son nom dans une recherche d’application). Vous verrez apparaître le premier assistant d’exécution.
![image](tool_pgplin1.png)

Ensuite, vous verrez l’assistant de première exécution. Pour configurer votre adresse électronique existante, cliquez sur "Ignorer cette option et utiliser mon adresse électronique existante". Ensuite, entrez votre nom, votre adresse électronique et le mot de passe associé à celui-ci.
![image](tool_pgplin2.png)

Si vous utilisez un service de messagerie gratuit et populaire tel que Gmail, Thunderbird devrait pouvoir détecter automatiquement vos paramètres de messagerie lorsque vous cliquez sur "Continuer".

**Si vous utilisez une authentification à deux facteurs avec Google (et en fonction de votre modèle de menace, vous devriez probablement le faire !), Vous ne pouvez pas utiliser votre mot de passe Gmail standard avec Thunderbird. Au lieu de cela, vous devrez créer un nouveau mot de passe spécifique à l’application pour que Thunderbird puisse accéder à votre compte Gmail. Consultez le [guide de Google](https://support.google.com/mail/answer/1173270?hl=fr) pour ce faire.**
![image](tool_pgplin3.png)

Si vous utilisez des services de messagerie gratuits tels que Gmail, Mail devrait pouvoir détecter automatiquement vos paramètres de messagerie lorsque vous cliquez sur Continuer. Si ce n’est pas le cas, vous devrez peut-être configurer manuellement vos paramètres IMAP et SMTP. Adressez-vous à la société de messagerie que vous utilisez ou demandez à un technicien connaissant votre fournisseur de messagerie (un informaticien au travail ou un ami technicien utilisant le même fournisseur d’accès que vous. Ils n’ont pas besoin de connaître PGP, mais vous pouvez leur demander "Pouvez-vous configurer Apple Mail pour moi ?").

### 2.2 Configuration de Enigmail

Enigmail est une extension pour Thunderbird qui chiffre et déchiffre les courriels encodés en PGP et facilite la gestion des clés privées et publiques. Si vous possédez la dernière version d’Enigmail, l’Assistant de configuration d’Enigmail devrait vous être présenté.
![image](tool_pgplin4.png)

Si vous ne le voyez pas, vous pouvez utiliser cette option de menu de Thunderbird pour le faire apparaître. Cliquez sur les trois lignes horizontales (le "menu hamburger") à droite de la fenêtre Thunderbird.
![image](tool_pgplin5.png)

Voici la première option proposée par Enigmail : trois options pour gérer le moment propice au chiffrement de votre courriel.
![image](tool_pgplin6.png)

L’option par défaut consiste à chiffrer les courriels si vous avez la "clé publique" d’une autre personne. Enigmail chiffrera le courriel que vous envoyez mais laissera les courriels non chiffrés si vous n’avez pas encore la clé publique du destinataire. Vous avez également la possibilité de chiffrer en permanence les courriers électroniques envoyés à des personnes possédant des clés PGP, ce qui signifie que vous devrez trouver les clés publiques des personnes pour lesquelles vous ne les avez pas déjà, ou désactiver complètement le chiffrement automatique et utiliser uniquement PGP.

Nous ne savons pas quelle est l’option appropriée pour vous, mais nous pensons que l’option "Chiffrement automatique pratique" est un bon choix. Si vous avez un doute, choisissez "Ne pas chiffrer mes messages par défaut".

Cliquez sur le bouton "Suivant".
![image](tool_pgplin6.png)

Vous avez maintenant la possibilité de signer numériquement tous les courriels sortants. La signature de votre courrier avec PGP permet au destinataire de vérifier que vous avez envoyé le message et que le contenu du message n’a pas été falsifié. Cliquez sur le bouton "Signer mes messages par défaut" pour activer cette fonctionnalité.

Cependant, le désavantage de cela est que cela permet également de signaler à toute personne à qui vous envoyez un courriel que vous utilisez PGP. [Dans certaines régions du monde](www.cryptolaw.org/) (y compris la Chine, l’Iran, la Biélorussie et certains États du Moyen-Orient), l’utilisation d’un chiffrement sans licence, même à des fins personnelles, est illégale. Vous pouvez donc avoir de très bonnes raisons de ne laisser personne savoir que vous utilisez PGP.

Cliquez sur le bouton "Suivant".

Vous verrez désormais une option permettant à Enigmail d’apporter des modifications à la configuration de Mozilla Thunderbird.
![image](tool_pgplin7.png)

Si vous cliquez sur le bouton Détails, vous pouvez vérifier quelles sont ces modifications.

Les options suivantes peuvent être désélectionnées (réactivées), pour une transition plus transparente, si vous utilisez PGP/Mime par défaut (nous en parlerons plus tard) :
- Désactiver le texte fluide
- Voir le corps du message en texte brut
- Ne pas composer de messages HTML

La dernière option évite les problèmes potentiels de chiffrement et de déchiffrement de votre courrier électronique. Sachez qu’en sélectionnant cette case, vous ne pourrez plus envoyer de texte en gras, souligné ou en couleur. Après avoir examiné les modifications, cliquez sur le bouton "OK".

Vous allez désormais commencer à créer votre clé privée et votre clé publique.

### 2.3 Création d’une clé publique et d’une clé privée

L’installation et la configuration du module complémentaire Enigmail sont terminées. Vous avez maintenant la possibilité de créer votre paire de clés publique et privée. Cela suppose que vous n’avez pas créé de clé privée auparavant.
![image](tool_pgplin8.png)

Cliquez sur le bouton "Suivant".

Sauf si vous avez déjà configuré plusieurs comptes de messagerie, Enigmail choisira le compte de messagerie que vous avez déjà configuré. La première chose à faire est de définir une phrase secrète forte pour votre clé privée. Voir la **[leçon sur les Mots de Passe](umbrella://information/passwords)** pour plus d’informations sur la procédure à suivre.

Enigmail affichera des informations sur votre clé privée ainsi que les paramètres de configuration. Nous vous recommandons de créer des clés d’une longueur de 4096 bits. Cliquez sur le bouton "Suivant".
![image](tool_pgplin9.png)

**Votre clé expirera à un moment donné ; lorsque cela se produit, d’autres personnes cesseront de l’utiliser entièrement pour vous envoyer de nouveaux courriels, bien que vous ne receviez peut-être aucun avertissement ni aucune explication quant à pourquoi. Donc, pensez à le marquer sur votre calendrier et faites attention à ce problème environ un mois avant la date d’expiration.**

Il est possible de prolonger la durée de vie d’une clé existante en lui attribuant une nouvelle date d’expiration, ou de la remplacer par une nouvelle clé en en créant une nouvelle à partir de zéro. Les deux processus peuvent nécessiter de contacter des personnes qui vous envoient un courrier électronique et de s’assurer qu’ils obtiennent la clé mise à jour. Les logiciels actuels ne sont pas très efficaces pour automatiser cela. Alors faites un rappel pour vous-même ; si vous pensez ne pas être en mesure de le gérer, vous pouvez envisager de définir la clé de sorte qu’elle n’expire jamais, bien que dans ce cas, d’autres personnes pourraient essayer de l’utiliser lorsque vous contactez une personne dans le futur, même si vous n’utilisez plus la clé privée ou n’utilisez plus PGP.

Enigmail générera la clé et une fois terminée, une petite fenêtre s’ouvrira vous demandant de générer un certificat de révocation. Ce certificat de révocation est important car il vous permet de rendre la clé privée et la clé publique non valides. Il est important de noter que le simple fait de supprimer la clé privée n’invalide pas la clé publique et peut amener des personnes à vous envoyer du courrier chiffré que vous ne pouvez pas déchiffrer.
![image](tool_pgplin10.png)

Cliquez sur le bouton "Générer un Certificat".

Une fenêtre s’ouvrira pour vous permettre de sauvegarder le certificat de révocation. Bien que vous puissiez enregistrer le fichier sur votre ordinateur, nous vous recommandons de l’enregistrer sur un lecteur USB que vous n’utilisez pas et de le stocker dans un endroit sûr. Nous vous recommandons également de supprimer le certificat de révocation de l’ordinateur avec les clés, afin d’éviter toute révocation involontaire.

Mieux encore, enregistrez ce fichier sur un disque chiffré séparé. Choisissez l’emplacement où vous enregistrez ce fichier et cliquez sur le bouton "Enregistrer".

Désormais, Enigmail vous donnera des informations supplémentaires sur la sauvegarde du fichier du certificat de révocation. Cliquez sur le bouton "OK".

Vous avez enfin terminé avec la génération de la clé privée et de la clé publique. Cliquez sur le bouton "Terminer".

### 2.4 Étapes facultatives

### 2.4.1 Affichage des identifiants de clé longues

Les étapes suivantes sont complètement facultatives, mais elles peuvent être utiles lorsque vous utilisez OpenPGP et Enigmail. En bref, l’Identifiant de la clé est une petite partie de l’empreinte numérique. Lorsqu’il s’agit de vérifier qu’une clé publique appartient à une personne en particulier, l’empreinte numérique est la meilleure solution. Changer l’affichage par défaut facilite la lecture des empreintes digitales des certificats que vous connaissez. Cliquez sur le bouton de configuration, puis sur l’option Enigmail, puis sur Gestion des clés.
![image](tool_pgplin11.png)

Une fenêtre s’ouvrira montrant deux colonnes : Nom et Identifiant de la Clé.
![image](tool_pgplin12.png)

À l’extrême droite, il y a un petit bouton. Cliquez sur ce bouton pour configurer les colonnes. Décochez l’option Identifiant de Clé et cliquez sur l’option Empreinte.
![image](tool_pgplin13.png)

Modifiez maintenant la largeur de la colonne Empreinte en déplaçant la souris sur les lignes situées entre chaque en-tête de colonne (c’est-à-dire juste à gauche de l’en-tête "Identifiant de Clé" en haut de la liste des clés), puis en faisant glisser la ligne vers la gauche. Continuez à vous déplacer à gauche jusqu’à ce que vous puissiez voir tous les Identifiants des clés, comme ceci :

Les colonnes ressemblerons désormais à cela :
![image](tool_pgplin14.png)

Vous êtes maintenant configuré pour envoyer et recevoir des courriels réguliers et chiffrés. Vous allez ensuite suivre les étapes pour trouver les personnes avec lesquelles échanger du courrier chiffré.

**L’utilisation de PGP ne chiffre pas complètement votre courrier électronique, de sorte que les informations sur l’expéditeur et le destinataire soient chiffrées. Le chiffrement des informations concernant l’expéditeur et le destinataire romprait le courrier électronique. L’utilisation de Thunderbird avec l’extension Enigmail vous offre un moyen simple de chiffrer et de déchiffrer le contenu de votre courrier électronique.**

### 3.0 Faire savoir aux autres que vous utilisez PGP

**a) Informez les gens que vous utilisez PGP dans vos courriels électroniques**

Vous pouvez facilement envoyer votre clé publique par courrier électronique à une autre personne en lui envoyant une copie en pièce jointe.

Cliquez sur le bouton "Écrire" dans Mozilla Thunderbird.

Entrez une adresse et un objet, par exemple, "ma clé publique", cliquez sur le menu Enigmail et sélectionnez l’option "Joindre ma clé publique".
![image](tool_pgplin15.png)

Vous pouvez désormais envoyer un courrier électronique, et le destinataire pourra télécharger et utiliser la clé publique que vous avez envoyée.

**Si cette méthode est utilisée, il est judicieux de demander au destinataire de vérifier l’empreinte de votre clé publique sur une autre plateforme de communication, au cas où le courrier électronique serait déjà intercepté et falsifié.**

**b) Informez les gens que vous utilisez PGP sur votre site Web**

En plus d’informer les gens par courrier électronique, vous pouvez publier votre clé publique sur votre site Web. Le moyen le plus simple est de télécharger le fichier et d’y accéder. Ce guide ne vous expliquera pas comment faire, mais vous devez savoir comment exporter le certificat sous forme de fichier à utiliser ultérieurement.

Cliquez sur le bouton de configuration, puis sur l’option Enigmail, puis sur Gestion des clés.

Mettez en surbrillance votre certificat en gras, puis cliquez avec le bouton droit de la souris pour afficher le menu, puis sélectionnez Exporter les clés dans un fichier.
![image](tool_pgplin16.png)

Une petite fenêtre apparaîtra avec trois boutons. Cliquez sur le bouton "Exporter les clés publiques uniquement".
![image](tool_pgplin17.png)


**Assurez-vous de ne pas cliquer sur le bouton "Exporter les Clés Secrètes" car l’exportation de la clé secrète pourrait permettre à d’autres personnes de vous imiter si elles sont en mesure de deviner votre mot de passe.**

Une fenêtre s’ouvrira pour vous permettre de sauvegarder le fichier. Afin de faciliter la recherche à l’avenir, sauvegardez le fichier dans le dossier Documents.

Vous pouvez désormais utiliser ce fichier à votre guise.

**c) Téléchargement sur un serveur de clés**

Les serveurs de clés facilitent la recherche et le téléchargement de clés publiques. La plupart des serveurs de clés modernes se synchronisent, ce qui signifie qu’une clé publique téléchargée sur un serveur atteindra finalement tous les serveurs.

Bien que le téléchargement de votre clé publique sur un serveur de clés puisse être un moyen pratique de faire savoir aux personnes que vous possédez un certificat PGP public, vous devez savoir qu’en raison de la manière dont les serveurs de clés fonctionnent, il est impossible de supprimer les clés publiques une fois qu’elles ont été téléchargées. Vous pouvez uniquement les marquer comme révoqués.

**Avant de télécharger votre clé publique sur un serveur de clés, il est bon de prendre un moment pour déterminer si vous souhaitez que le monde entier sache que vous avez une clé publique sans possibilité de supprimer ces informations ultérieurement.**

Si vous choisissez de télécharger votre clé publique sur des serveurs de clés, vous revenez à la fenêtre Gestion des clés d’Enigmail.

Cliquez sur l’élément du menu Serveur de clés et sélectionnez l’option Télécharger les clés publiques.
![image](tool_pgplin18.png)

### 3.1 Rechercher d’autres personnes qui utilisent PGP

**a) Obtenez une clé publique par courriel**

Vous pourriez recevoir une clé publique sous forme de pièce jointe dans un courrier électronique.
![image](tool_pgplin19.png)

Remarquez la pièce jointe au bas de la fenêtre. Cliquez avec le bouton droit sur la pièce jointe et sélectionnez "Importer la clé OpenPGP". Une petite fenêtre s’ouvrira vous donnant les résultats de l’importation. Cliquez sur le bouton OK.

Si vous ouvrez à nouveau la fenêtre de gestion de clés d’Enigmail, vous pouvez vérifier le résultat. Votre clé PGP est en gras car vous disposez à la fois de la clé privée et de la clé publique. La clé publique que vous venez d’importer n’est pas en gras car elle ne contient pas la clé privée.
![image](tool_pgplin20.png)

**b) Obtenez une clé publique sous forme de fichier**

Il est possible que vous obteniez une clé publique en la téléchargeant depuis un site Web ou que quelqu’un l’ait envoyée via un logiciel de discussion. Dans ce cas, vous supposerez que vous avez téléchargé le fichier dans le dossier Téléchargements.

Ouvrez le Gestionnaire de Clés d’Enigmail et cliquez sur le menu "Fichier". Sélectionnez "Importer des Clés à partir d’un Fichier".

La clé publique peut avoir des terminaisons de nom de fichier très différentes, telles que .asc, .pgp ou .gpg. Sélectionnez le fichier et cliquez sur le bouton "Ouvrir". Une petite fenêtre s’ouvrira pour vous donner les résultats de l’importation. Cliquez sur le bouton "OK".

**c) Obtenez une clé publique à partir d’un serveur de clés**

Les serveurs de clés peuvent être un moyen très utile d’obtenir des clés publiques. Essayez de chercher une clé publique. Ouvrez le gestionnaire de clés, puis cliquez sur le menu "Serveur de clés" et sélectionnez "Rechercher des clés".
![image](tool_pgplin21.png)

Une petite fenêtre apparaîtra avec un champ de recherche. Vous pouvez effectuer une recherche par adresse électronique complète, partielle ou par nom. Dans ce cas, vous rechercherez des certificats contenant "eff.org".
![image](tool_pgplin22.png)

Une fenêtre plus grande apparaîtra avec de nombreuses options. Si vous faites défiler l’écran vers le bas, vous remarquerez que certains certificats sont en italique et grisés. Ce sont des certificats qui ont été révoqués ou qui ont expirés par eux-mêmes.
![image](tool_pgplin23.png)

Prenons les clés publiques de Danny O’Brien, par exemple, il a un certificat expiré ou révoqué et un certificat valide. Sélectionnez le certificat valide en cliquant sur la case à gauche, puis appuyez sur le bouton OK.
![image](tool_pgplin24.png)

Dans certains cas, une personne peut avoir plus d’un certificat, tous semblant valables. Notez qu’il est possible pour quiconque de télécharger un certificat public et que l’une de ces clés n’appartienne pas à la personne à qui appartient l’adresse électronique qui lui est associée. Dans ce cas, la vérification de l’empreinte numérique est extrêmement importante.

Une petite fenêtre de notification apparaîtra pour vous indiquer si vous avez réussi. Le Gestionnaire de Clés d’Enigmail affiche désormais les certificats ajoutés :
![image](tool_pgplin25.png)

### 4.0 Envoi d’un courriel chiffré PGP

Vous allez maintenant envoyer votre premier courriel chiffré à un destinataire. Dans la fenêtre principale de Mozilla Thunderbird, cliquez sur le bouton "Écrire". Une nouvelle fenêtre s’ouvrira.

Rédigez votre message et entrez un destinataire. Pour ce test, sélectionnez un destinataire dont vous possédez déjà la clé publique. Enigmail le détectera et chiffrera automatiquement l’courriel (vous pouvez dire qu’il sera chiffré à l’aide de la clé dorée située en bas à droite de l’courriel).
![image](tool_pgplin26.png)

**Notez que la ligne d’objet ne sera pas chiffrée, alors choisissez quelque chose d’inoffensif, comme "bonjour".**

Lorsque vous cliquez sur le bouton "Envoyer", une fenêtre s’ouvre pour vous permettre de saisir le mot de passe de votre clé PGP. Rappelez-vous que que ce dernier est différent de votre mot de passe du compte courriel !

Entrez votre mot de passe puis cliquez sur le bouton "OK" et votre courriel sera chiffré et envoyé.

Le corps de l’courriel a été chiffré et transformé. Par exemple, notre texte ci-dessus a été converti en ceci :
![image](tool_pgplin27.png)

### 4.1 Réception d’un courriel chiffré PGP

Passons en revue ce qui se passe lorsque vous recevez un courrier électronique chiffré. Tout d’abord, cliquez sur le message.

Une petite fenêtre s’ouvre vous demandant le mot de passe de la clé PGP. N’oubliez pas : n’entrez pas votre mot de passe du compte courriel. Cliquez sur le bouton "OK".
![image](tool_pgplin28.png)

Désormais, le message s’affichera comme déchiffré
![image](tool_pgplin29.png)

### 5.0 Révocation de la clé PGP

**a) Révoquez votre clé PGP via l’interface Enigmail**

Les clés PGP générées par Enigmail expirent automatiquement après cinq ans. Donc, si vous perdez tous vos fichiers, vous pouvez espérer que les gens sauront vous demander une autre clé une fois celle-ci expirée.

Vous avez peut-être une bonne raison de désactiver la clé PGP avant son expiration. Peut-être souhaitez-vous générer une nouvelle clé PGP plus puissante. Le moyen le plus simple de révoquer votre propre clé PGP dans Enigmail consiste à utiliser le gestionnaire de clés Enigmail. Cliquez avec le bouton droit sur votre clé PGP (en gras) et sélectionnez l’option "Révoquer la clé".
![image](tool_pgplin30.png)

Une fenêtre s’ouvrira pour vous permettre de savoir ce qui se passe et vous demander votre confirmation. Cliquez sur le bouton "Révoquer la clé".
![image](tool_pgplin31.png)

La fenêtre du mot de passe s’ouvre, entrez votre mot de passe pour la clé PGP et cliquez sur le bouton "OK".

Une nouvelle fenêtre s’ouvrira désormais vous permettant de savoir que vous avez réussi. Cliquez sur le bouton "OK".

Lorsque vous revenez à la fenêtre Gestion des clés d’Enigmail, vous remarquerez une modification de votre clé PGP. Celle-ci est maintenant grisée et en italique.
![image](tool_pgplin32.png)

**b) Révocation d’une clé PGP avec un certificat de révocation**

Comme indiqué précédemment, les clés PGP générées par Enigmail expirent automatiquement après cinq ans. Donc, si vous perdez tous vos fichiers, vous pouvez être sûr que les gens sauront vous demander une autre clé une fois celle-ci expirée.

Comme nous l’avons mentionné précédemment, vous avez peut-être une bonne raison de désactiver la clé PGP avant son expiration.

De même, d’autres personnes peuvent avoir de bonnes raisons de révoquer une clé existante.

Vous pourriez recevoir des certificats de révocation d’amis afin de les informer de leur intention de révoquer leur clé.

Dans la section précédente, vous avez peut-être remarqué qu’Enigmail génère et importe un certificat de révocation en interne lorsque vous utilisez le gestionnaire de clés d’Enigmail pour révoquer une clé. Puisque vous avez déjà un certificat de révocation, vous utiliserez celui que vous avez généré précédemment pour révoquer votre propre clé.

Commencez avec le gestionnaire de clés d’Enigmail, cliquez sur le menu "Fichier", puis sélectionnez "Importer les Clés à partir d’un Fichier".
![image](tool_pgplin33.png)

Une fenêtre s’ouvrira afin que vous puissiez sélectionner le certificat de révocation. Cliquez sur le fichier, puis cliquez sur le bouton "Ouvrir". Vous recevrez une notification indiquant que le certificat a été importé avec succès et qu’une clé a été révoquée. Cliquez sur le bouton "OK".
![image](tool_pgplin34.png)

Une fois que vous avez cliqué sur le bouton "OK", vous êtes redirigé vers le Gestionnaire de Clés d’Enigmail et le certificat que vous avez révoqué est grisé et en italique.
![image](tool_pgplin35.png)

Si la clé que vous avez révoquée est la vôtre et que vous avez déjà chargé votre clé publique sur les serveurs de clés, vous souhaiterez réimporter la clé désormais révoquée sur les serveurs de clés, afin que d’autres personnes ne l’utilisent plus.

Maintenant que vous disposez de tous les outils appropriés, essayez d’envoyer votre propre courrier électronique chiffré avec PGP.
