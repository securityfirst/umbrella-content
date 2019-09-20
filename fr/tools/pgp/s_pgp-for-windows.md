---
index: 12
title: PGP pour Windows
---
# Guide de PGP pour Windows PC

Courriel chiffré pour Windows

**Leçon à lire : [Courriel](umbrella://lesson/courriel)**  
**Téléchargement :**
- GPG4Win   
- Mozilla Thunderbird  
- Enigmail  

**Configuration requise pour l’ordinateur:** Une connexion Internet, un ordinateur exécutant Windows, un compte de messagerie  
**Version utilisée dans ce guide :**
- Windows : Windows 7 Ultimate  
- Mozilla Thunderbird 24.6.0  
- Enigmail 1.7  
- GPG4Win 2.2.1  

**Licence :** Logiciel libre ; mélange de licences de logiciels libres  
**Niveau :** Avancé  
**Temps requis :** 30-60 minutes

**L’utilisation de PGP vous donnera :**
- La possibilité de protéger vos courriels de toute lecture de la part d’inconnu, sauf de leurs destinataires.
- La possibilité de prouver qu’un courriel provient d’une personne en particulier, au lieu d’être un faux message envoyé par un autre expéditeur (il est très facile de créer un courriel). Les deux sont des défenses importantes si vous êtes ciblé pour la surveillance ou la désinformation.

**Note :** Si vous craignez que les courriels chiffrés par PGP ne soient plus sûrs après la détection de vulnérabilités en Mai 2018, consultez la section Efail de notre leçon avancée sur les [courriel](umbrella://lesson/courriel).

### 1.0 Avant de commencer

Pour utiliser Pretty Good Privacy (PGP), vous devez installer un logiciel supplémentaire qui fonctionnera avec votre programme de messagerie actuel. Vous aurez également besoin de créer une clé privée, que vous garderez privée. La clé privée est ce que vous utiliserez pour déchiffrer les courriers électroniques qui vous sont envoyés et pour signer numériquement les courriers électroniques que vous envoyez pour montrer qu’ils proviennent réellement de vous. Enfin, vous apprendrez à distribuer votre clé publique - un petit bloc d’informations que les autres devront connaître avant de pouvoir vous envoyer du courriel chiffré et qu’ils pourront utiliser pour vérifier les courriels que vous leur envoyez.

**Notez que les deux bouts de la conversation par courriel doivent utiliser un logiciel compatible PGP pour que cela fonctionne.**

Les gens l’utiliseront normalement uniquement sur leurs propres appareils personnels, pas sur des appareils partagés. Heureusement, PGP est disponible pour la plupart des ordinateurs de bureau et des périphériques mobiles et vous pouvez leur indiquer ces guides pour les aider à configurer leur propre version. Ce guide est pour les utilisateurs Windows.

### 1.1 Vue d’ensemble

Pour utiliser PGP afin d’échanger des courriels sécurisés, vous devez réunir trois programmes : GPG4Win (GNU Privacy Guard pour Windows connu sous le nom de GnuPG), Mozilla Thunderbird et Enigmail.

- GnuPG est le programme qui chiffre et déchiffre le contenu de votre courriel.
- Mozilla Thunderbird est un client de messagerie qui vous permet de lire et écrire des courriels sans utiliser de navigateur.
- Enigmail est une extension de Mozilla Thunderbird qui relie tout cela.

Remarque ! Ce guide explique comment utiliser PGP avec Mozilla Thunderbird, un programme client de messagerie offrant une fonction similaire à Outlook. Vous pouvez avoir votre propre logiciel de messagerie préféré (ou utiliser un service de messagerie Web tel que Google Mail ou Outlook.com). Ce guide ne vous expliquera pas comment utiliser PGP avec ces programmes. Vous pouvez choisir d’installer Thunderbird et expérimenter PGP avec un nouveau client de messagerie. Vous pouvez également rechercher d’autres solutions permettant d’utiliser PGP avec votre logiciel habituel. Nous n’avons toujours pas trouvé de solution satisfaisante pour ces autres programmes.

**L’utilisation de PGP ne chiffre pas complètement votre courrier électronique : les informations sur l’expéditeur et le destinataire ne sont pas chiffrées, de même pour la ligne d’objet !**

Chiffrer les informations de l’expéditeur et du destinataire est impossible dans le système de messagerie existant. L’utilisation de Mozilla Thunderbird avec le module complémentaire Enigmail constitue un moyen simple de chiffrer le contenu de votre courrier électronique. Une personne qui espionne vos courriels peut toujours voir l’identité des personnes avec lesquelles vous communiquez et quand vous leur envoyez un courrier électronique.

Tout d’abord, téléchargez tous les logiciels nécessaires, installez-les, puis terminez par la configuration et l’utilisation de ces derniers.

### 2 Téléchargement du logiciel

### 2.1 Obtenir GPG4Win

Vous pouvez obtenir GnuPG (également appelé GPG) sous Windows en téléchargeant le petit programme d’installation à partir de la page de téléchargement de GPG4Win.
![image](tool_pgpwin1.png)

Cliquez sur la version la plus récente de GPG4Win avec le composant GnuPG (Vanilla ou Light) uniquement pour télécharger le programme d’installation de GPG.

**Note : Cette version de GPG est disponible uniquement sur un site Web proposant des téléchargements "http", et "https" signifiant que cela est sécurisé. Si vous craignez que votre entreprise puisse être surveillée par une organisation susceptible d’altérer votre connexion Internet, vous pouvez explorer des solutions plus radicales, telles que le téléchargement et l’exécution de Tails, un système d’exploitation sécurisé qui remplace Windows.**

De nombreux navigateurs vous demanderont de confirmer si vous souhaitez télécharger ce fichier. Internet Explorer 11 affiche une barre au bas de la fenêtre du navigateur avec une bordure orange.

Pour tous les navigateurs, il est préférable d’enregistrer d’abord le fichier avant de continuer, donc _cliquez sur le bouton "Enregistrer". Par défaut, la plupart des navigateurs enregistrent les fichiers téléchargés dans le dossier Téléchargements.

### 2.2 Obtenir Mozilla Thunderbird

Allez sur le site Web de Mozilla Thunderbird.
![image](tool_pgpwin2.png)

Cliquez sur le bouton vert intitulé "Thunderbird Free Download."

Le site Web de Mozilla Thunderbird aura détecté votre langue préférée. Si vous souhaitez utiliser Thunderbird dans une autre langue, cliquez sur le lien "Autres Systèmes et Langues", puis faites votre choix.

De nombreux navigateurs vous demanderont de confirmer si vous souhaitez télécharger ce fichier. Internet Explorer 11 affiche une barre au bas de la fenêtre du navigateur avec une bordure orange.
![image](tool_pgpwin3.png)

Quel que soit le navigateur utilisé, il est préférable de commencer par enregistrer le fichier avant de continuer. Cliquez donc sur le bouton "Enregistrer". Par défaut, la plupart des navigateurs enregistrent les fichiers téléchargés dans le dossier Téléchargements.

### 2.3 Obtenir Enigmail

Vous pouvez obtenir Enigmail à partir du site Web Enigmail.
![image](tool_pgpwin4.png)

De nombreux navigateurs vous demanderont de confirmer si vous souhaitez télécharger ce fichier. Internet Explorer 11 affiche une barre au bas de la fenêtre du navigateur avec une bordure orange.
![image](tool_pgpwin5.png)
Pour tout navigateur, il est préférable de commencer par enregistrer le fichier avant de continuer, cliquez donc sur le bouton "Enregistrer". Par défaut, la plupart des navigateurs enregistrent les fichiers téléchargés dans le dossier Téléchargements.


Après avoir téléchargé Enigmail, GPG4Win et Mozilla Thunderbird, vous devriez avoir trois nouveaux fichiers dans votre dossier Téléchargements :
![image](tool_pgpwin6.png)

### 3 Installation du logiciel

### 3.1 Installation de GPG4Win

Laissez la fenêtre de l’explorateur Windows ouverte et double-cliquez sur gpg4win-xxx-x.x.x.exe. On vous demandera si vous souhaitez autoriser l’installation de ce programme. Cliquez sur le bouton "Oui".
![image](tool_pgpwin7.png)

Une fenêtre s’ouvrira pour vous donner un aperçu de ce qui sera installé. Cliquez sur le bouton "Suivant".
![image](tool_pgpwin8.png)

Une fenêtre avec le contrat de licence s’ouvrira. Cliquez sur le bouton "Suivant".
![image](tool_pgpwin9.png)

Le package GPG4Win Vanilla n’a pas de composants à sélectionner, cliquez donc à nouveau sur le bouton "Suivant". Pour le package GPG4Win-Light, désélectionnez tous les composants optionnels pour installer uniquement GnuPG.
![image](tool_pgpwin10.png)

Ensuite, vous pourrez choisir l’emplacement d’installation de GPG. Ne changez pas le paramètre par défaut. Cliquez sur le bouton "Suivant".
![image](tool_pgpwin11.png)

Les deux prochaines fenêtres auront quelques options d’installation. Cliquez sur le bouton "Suivant" puis sur le bouton "Installer" :
![image](tool_pgpwin12.png)![image](tool_pgpwin13.png)

Vous verrez une fenêtre avec une barre de progression. Une fois l’opération terminée, elle indiquera "Installation terminée". Cliquez à nouveau sur le bouton "Suivant" .
![image](tool_pgpwin14.png)

Enfin, vous êtes à la dernière étape de l’installation. Décochez "Afficher le fichier README" et cliquez sur le bouton "Terminer".
![image](tool_pgpwin15.png)

C’est tout. Passons maintenant à l’installation de Mozilla Thunderbird.

### 3.2 Installation de Mozilla Thunderbird

Comme pour GPG4Win, vous installez Mozilla Thunderbird en double-cliquant sur le fichier Thunderbird Setup 24.6.0.exe. Comme d’habitude, il vous sera demandé si vous voulez exécuter ce fichier. Cliquez sur le bouton "Exécuter".
![image](tool_pgpwin16.png)

Il vous sera demandé si vous souhaitez autoriser Mozilla Thunderbird à réaliser un changement sur votre ordinateur en installant un logiciel. Cliquez sur le bouton "Oui".
![image](tool_pgpwin17.png)

Vous verrez la fenêtre d’installation de Mozilla Thunderbird. Cliquez sur le bouton "Suivant".
![image](tool_pgpwin18.png)

Ensuite, vous aurez le choix entre une configuration standard et une configuration personnalisée. Conservez la sélection de configuration standard et cliquez sur le bouton "Suivant".
![image](tool_pgpwin18.png)

Vous recevrez un résumé de l’emplacement de l’installation des fichiers de Mozilla Thunderbird. Cliquez sur le bouton "Installer".
![image](tool_pgpwin19.png)

Une fois le processus d’installation terminé, vous verrez une dernière fenêtre vous permettant de lancer Mozilla Thunderbird. Cliquez sur le bouton "Terminer".
![image](tool_pgpwin20.png)

### 3.3. Installation d’Enigmail

**Étape 1. Préparation**

Lorsque Mozilla Thunderbird sera lancé pour la première fois, vous verrez cette petite fenêtre de confirmation vous interroger sur certains paramètres par défaut. Nous vous recommandons de cliquer sur le bouton "Définir par défaut".
![image](tool_pgpwin21.png)

Ensuite, il vous sera demandé si vous souhaitez une nouvelle adresse courriel. Cliquez sur le bouton "Ignorer ceci et utiliser mon courriel existant". Vous allez maintenant configurer Mozilla Thunderbird pour envoyer et recevoir des courriels. Si vous avez l’habitude de lire et d’envoyer des courriels via gmail.com, outlook.com ou yahoo.com, Mozilla Thunderbird sera une nouvelle expérience, mais ce n’est pas si différent dans l’ensemble.
![image](tool_pgpwin22.png)

**Étape 2. Ajout d’un compte de messagerie à Mozilla Thunderbird**

Une nouvelle fenêtre s’ouvrira.
![image](tool_pgpwin23.png)

Entrez votre nom, votre adresse électronique et le mot de passe associé à votre compte de messagerie. Mozilla n’a pas accès à votre mot de passe ni à votre compte de messagerie. Cliquez sur le bouton "Continuer".
![image](tool_pgpwin24.png)

Dans de nombreux cas, Mozilla Thunderbird détectera automatiquement les paramètres nécessaires. Dans certains cas, Mozilla Thunderbird ne dispose pas d’informations complètes et vous devrez les saisir vous-même. Voici un exemple des instructions fournies par Google pour Gmail :

Serveur de Courriel Entrant (IMAP) - Nécessite SSL
- imap.gmail.com  
- Port : 993  
- Nécessite SSL : Oui

Serveur de Courriel Sortant (SMTP) - Nécessite TLS
- smtp.gmail.com  
- Port : 465 ou 587
- Nécessite SSL : Oui
- Nécessite une authentification : Oui
- Utilisez les mêmes paramètres que le serveur de courriel entrant

**Nom Complet ou Nom d’Affichage :** [votre nom ou pseudonyme]

**Nom du Compte ou Nom d’Utilisateur :** votre adresse Gmail complète (nomutilisateur@gmail.com). Pour les utilisateurs de Google Apps, entrez nomutilisateur@votre_domaine.com.

**Adresse courriel :** votre adresse Gmail complète (nomutilisateur@gmail.com). Pour les utilisateurs de Google Apps, veuillez entrer nomutilisateur@votre_domaine.com

**Mot de Passe :** votre mot de passe Gmail

**Si vous utilisez une authentification à deux facteurs avec Google (et en fonction de votre modèle de menace, vous devriez probablement le faire !), Vous ne pouvez pas utiliser votre mot de passe Gmail standard avec Thunderbird. Au lieu de cela, vous devrez créer un nouveau mot de passe spécifique à l’application pour que Thunderbird puisse accéder à votre compte Gmail. Consultez le [guide de Google](https://support.google.com/mail/answer/1173270?hl=fr) pour ce faire.**

Lorsque toutes les informations sont entrées correctement, cliquez sur le bouton "Terminé".
![image](tool_pgpwin25.png)

Mozilla Thunderbird commencera à télécharger des copies de votre courrier électronique sur votre ordinateur. Essayez d’envoyer un courriel de test à vos amis.

**Étape 3. Installation Enigmail**

Enigmail est installé de manière différente de Mozilla Thunderbird et de GPG4Win. Comme mentionné précédemment, Enigmail est une extension pour Mozilla Thunderbird. Cliquez sur le bouton "Menu, également appelé le bouton Hamburger, et sélectionnez "Extension".
![image](tool_pgpwin26.png)

Vous serez redirigé vers l’onglet du Gestionnaire d’Extensions.
![image](tool_pgpwin27.png)

Cliquez sur le rouage pour afficher un petit menu et sélectionnez "Installer l’extension à partir d’un fichier", ce qui affichera une fenêtre de sélection de fichier.
![image](tool_pgpwin28.png)

La fenêtre de sélection de fichier s’ouvrira probablement dans le dossier Téléchargements. Si ce n’est pas le cas, allez dans le dossier Téléchargements (où Enigmail a été enregistré), cliquez sur enigmail-1.7-tb+sm.xpi, puis sur le bouton "Ouvrir".
![image](tool_pgpwin29.png)

Vous verrez maintenant une petite fenêtre vous demandant de confirmer si vous souhaitez installer Enigmail. Cliquez sur le bouton "Installer maintenant".
![image](tool_pgpwin30.png)

Une fois l’extension Enigmail installée, Mozilla Thunderbird demandera de redémarrer le navigateur pour activer Enigmail. Cliquez sur le bouton "Redémarrer maintenant" pour que Mozilla Thunderbird redémarre.
![image](tool_pgpwin31.png)

Lorsque Mozilla Thunderbird redémarre, une fenêtre supplémentaire s’ouvrira qui lancera le processus de configuration de l’extension Enigmail. Gardez le bouton "Oui, j’aimerais que l’assistant démarre" sélectionné et cliquez sur le bouton "Suivant".
![image](tool_pgpwin32.png)

Enigmail vous offre trois options pour gérer le courriel. L’option par défaut consiste à chiffrer les courriels si vous avez la "clé publique" d’une autre personne. Enigmail chiffrera le courriel que vous envoyez mais laissera les courriels non chiffrés si vous n’avez pas encore la clé publique du destinataire. Vous avez également la possibilité de chiffrer en permanence les courriers électroniques avec des clés PGP, ce qui signifie que vous devrez trouver les clés publiques des personnes pour lesquelles vous ne les avez pas déjà, ou désactiver complètement le chiffrement automatique et utiliser uniquement PGP.
![image](tool_pgpwin33.png)

Nous ne savons pas quelle est l’option appropriée pour vous, mais nous pensons que l’option "Chiffrement automatique pratique" est un bon choix. Si vous avez un doute, choisissez "Ne pas chiffrer mes messages par défaut". Cliquez sur le bouton "Suivant".

Vous avez maintenant la possibilité de signer numériquement tous les courriels sortants. La signature de votre courrier avec PGP permet au destinataire de vérifier que vous avez envoyé le message et que le contenu du message n’a pas été falsifié. Cliquez sur le bouton "Signer mes messages par défaut" pour activer cette fonctionnalité. Le désavantage de cela, cependant, est que cela permet également de signaler à toute personne à qui vous envoyez un courriel que vous utilisez PGP. [Dans certaines régions du monde](www.cryptolaw.org/) (y compris la Chine, l’Iran, la Biélorussie et certains États du Moyen-Orient), l’utilisation d’un chiffrement sans licence, même à des fins personnelles, est illégale. Vous pouvez donc avoir de très bonnes raisons de cacher le fait que vous utilisez PGP.

Cliquez sur le bouton "Suivant".
![image](tool_pgplin34.png)

Vous verrez maintenant une option permettant à Enigmail d’apporter des modifications à la configuration de Mozilla Thunderbird.
![image](tool_pgpwin35.png)

Si vous cliquez sur le bouton Détails, vous pouvez vérifier quelles sont ces modifications.
![image](tool_pgpwin36.png)

Les options suivantes peuvent être désélectionnées (réactivées), pour une transition plus transparente, si vous utilisez PGP/Mime par défaut (nous le définirons plus tard) :

- Désactiver le texte fluide
- Voir le corps du message en texte brut
- Ne pas composer de messages HTML
La dernière option évite les problèmes potentiels de chiffrement et de déchiffrement de votre courrier électronique. Sachez qu’en sélectionnant cette case, vous ne pourrez plus envoyer de texte en gras, souligné ou en couleur. Après avoir examiné les modifications, cliquez sur le bouton "OK".


La petite fenêtre va se fermer. Cliquez sur le bouton "Suivant".

Vous allez désormais commencer à créer votre clé privée et votre clé publique.

### 4 Création d’une clé publique et d’une clé privée

L’installation et la configuration du module complémentaire Enigmail sont terminées. Vous avez maintenant la possibilité de créer votre paire de clés publique et privée. Cela suppose que vous n’avez pas créé de clé privée auparavant.

Cliquez sur le bouton "Suivant".
![image](tool_pgplin37.png)

Sauf si vous avez déjà configuré plusieurs comptes de messagerie, Enigmail choisira le compte de messagerie que vous avez déjà configuré. La première chose à faire est de définir une phrase secrète forte pour votre clé privée. Voir la **[leçon sur les Mots de Passe](umbrella://information/passwords)** pour plus d’informations sur la procédure à suivre.

Assurez-vous d’avoir écrit cette phrase secrète sur le papier jusqu’à ce que vous l’ayez mémorisée. Conservez-la dans un endroit où vous pouvez savoir si elle a été volé ou visualisé (comme votre portefeuille ou votre sac à main). Assurez-vous simplement de ne pas laisser ce papier traîner.

Cliquez sur le bouton "Suivant".

Enigmail affichera des informations sur votre clé privée ainsi que les paramètres de configuration. Nous vous recommandons de créer des clés d’une longueur de 4096 bits. Cliquez sur le bouton "Suivant".
![image](tool_pgplin38.png)

**Votre clé expirera à un moment donné ; lorsque cela se produit, d’autres personnes cesseront de l’utiliser entièrement pour vous envoyer de nouveaux courriels, bien que vous ne receviez peut-être aucun avertissement ni aucune explication quant à pourquoi. Donc, pensez à le marquer sur votre calendrier et faites attention à ce problème environ un mois avant la date d’expiration.**

Il est possible de prolonger la durée de vie d’une clé existante en lui attribuant une nouvelle date d’expiration, ou de la remplacer par une nouvelle clé en en créant une nouvelle à partir de zéro. Les deux processus peuvent nécessiter de contacter des personnes qui vous envoient un courrier électronique et de s’assurer qu’ils obtiennent la clé mise à jour. Les logiciels actuels ne sont pas très efficaces pour automatiser cela. Alors faites un rappel pour vous-même ; si vous pensez ne pas être en mesure de le gérer, vous pouvez envisager de définir la clé de sorte qu’elle n’expire jamais, bien que dans ce cas, d’autres personnes pourraient essayer de l’utiliser lorsque vous contactez une personne dans le futur, même si vous n’utilisez plus la clé privée ou n’utilisez plus PGP.

Enigmail générera la clé et une fois terminée, une petite fenêtre s’ouvrira vous demandant de générer un certificat de révocation. Ce certificat de révocation est important car il vous permet de rendre la clé privée et la clé publique non valides. Il est important de noter que le simple fait de supprimer la clé privée n’invalide pas la clé publique et peut amener des personnes à vous envoyer du courrier chiffré que vous ne pouvez pas déchiffrer.

Cliquez sur le bouton "Générer un Certificat".
![image](tool_pgpwin39.png)

Une fenêtre s’ouvrira pour vous permettre de sauvegarder le certificat de révocation. Bien que vous puissiez enregistrer le fichier sur votre ordinateur, nous vous recommandons de l’enregistrer sur un lecteur USB que vous n’utilisez pas et de le stocker dans un endroit sûr. Nous vous recommandons également de supprimer le certificat de révocation de l’ordinateur avec les clés, afin d’éviter toute révocation involontaire.

Mieux encore, enregistrez ce fichier sur un disque chiffré séparé. Choisissez l’emplacement où vous enregistrez ce fichier et cliquez sur le bouton "Enregistrer".
![image](tool_pgpwin40.png)

Désormais, Enigmail vous donnera des informations supplémentaires sur la sauvegarde du fichier du certificat de révocation. Cliquez sur le bouton "OK".
![image](tool_pgpwin41.png)

Vous avez enfin terminé avec la génération de la clé privée et de la clé publique. Cliquez sur le bouton "Terminer".
![image](tool_pgpwin42.png)

### 5 Étapes facultatives

### 5.1 Affichage des identifiants de clé longues

Les étapes suivantes sont complètement facultatives, mais elles peuvent être utiles lorsque vous utilisez OpenPGP et Enigmail. En bref, l’Identifiant de la clé est une petite partie de l’empreinte numérique. Lorsqu’il s’agit de vérifier qu’une clé publique appartient à une personne en particulier, l’empreinte numérique est la meilleure solution. Changer l’affichage par défaut facilite la lecture des empreintes digitales des certificats que vous connaissez. Cliquez sur le bouton de configuration, puis sur l’option Enigmail, puis sur Gestionnaire des Clés.
![image](tool_pgplin43.png)

Une fenêtre s’ouvrira montrant deux colonnes : Nom et Identifiant de la Clé.
![image](tool_pgplin43.png)

À l’extrême droite, il y a un petit bouton. Cliquez sur ce bouton pour configurer les colonnes. Décochez l’option Identifiant de Clé et cliquez sur l’option Empreinte.
![image](tool_pgplin44.png)

Les colonnes ressemblerons désormais à cela :
![image](tool_pgplin45.png)

Vous êtes maintenant configuré pour envoyer et recevoir des courriels réguliers et chiffrés. Vous allez ensuite suivre les étapes pour trouver les personnes avec lesquelles échanger du courrier chiffré.

### 5.2 Utilisation de PGP/MIME

Une dernière étape de configuration facultative consiste à activer PGP/MIME, ce qui facilite l’envoi de pièces jointes chiffrées et signées.

Vous pouvez trouver ce paramètre en cliquant sur le bouton Menu, en survolant Options , puis en cliquant sur Paramètres du compte. La fenêtre Paramètres du compte s’ouvrira.
![image](tool_pgpwin46.png)

Lorsque la fenêtre Paramètres du compte s’ouvre, cliquez sur l’onglet Sécurité OpenPGP, puis cochez la case Utiliser PGP/MIME par défaut. Cliquez ensuite sur le bouton OK. Maintenant, Enigmail utilisera PGP/MIME par défaut.
![image](tool_pgpwin47.png)

**L’utilisation de PGP ne chiffre pas complètement votre courrier électronique, de sorte que les informations sur l’expéditeur et le destinataire soient chiffrées. Le chiffrement des informations concernant l’expéditeur et le destinataire romprait le courrier électronique. L’utilisation de Thunderbird avec l’extension Enigmail vous offre un moyen simple de chiffrer et de déchiffrer le contenu de votre courrier électronique.**

### 6.1 Faire savoir aux autres que vous utilisez PGP

Maintenant que vous avez PGP, vous souhaitez que les autres utilisateurs sachent que vous l’utilisez afin qu’ils puissent également vous envoyer des messages chiffrés à l’aide de PGP.

Examinons trois manières différentes de faire savoir aux gens que vous utilisez PGP.

**a) Informer les gens que vous utilisez PGP dans vos courriels électroniques**

Vous pouvez facilement envoyer votre clé publique par courrier électronique à une autre personne en lui envoyant une copie en pièce jointe.

Cliquez sur le bouton "Écrire" dans Mozilla Thunderbird.
![image](tool_pgpwin48.png)

Entrez une adresse et un objet, par exemple, "ma clé publique", cliquez sur le menu Enigmail et sélectionnez l’option "Joindre ma Clé Publique".
![image](tool_pgplin49.png)

Vous pouvez désormais envoyer un courrier électronique, et le destinataire pourra télécharger et utiliser la clé publique que vous avez envoyée.

Si cette méthode est utilisée, il est judicieux de demander au destinataire de vérifier l’empreinte de votre clé publique sur une autre plateforme de communication, au cas où le courrier électronique serait déjà intercepté et falsifié.

**b) Informer les gens que vous utilisez PGP sur votre site Web**

En plus d’informer les gens par courrier électronique, vous pouvez publier votre clé publique sur votre site Web. Le moyen le plus simple est de télécharger le fichier et d’y accéder. Ce guide ne vous expliquera pas comment faire, mais vous devez savoir comment exporter le certificat sous forme de fichier à utiliser ultérieurement.

Cliquez sur le bouton de configuration, puis sur l’option Enigmail, puis sur Gestion des clés.

Mettez en surbrillance votre certificat en gras, puis cliquez avec le bouton droit de la souris pour afficher le menu, puis sélectionnez Exporter les clés dans un fichier.
![image](tool_pgplin50.png)

Une petite fenêtre apparaîtra avec trois boutons. Cliquez sur le bouton "Exporter les clés publiques uniquement".
![image](tool_pgplin51.png)

Assurez-vous de ne pas cliquer sur le bouton "Exporter les Clés Secrètes" car l’exportation de la clé secrète pourrait permettre à d’autres personnes de vous imiter si elles sont en mesure de deviner votre mot de passe.

Une fenêtre s’ouvrira pour vous permettre de sauvegarder le fichier. Afin de faciliter la recherche à l’avenir, sauvegardez le fichier dans le dossier Documents.
![image](tool_pgpwin52.png)

Vous pouvez désormais utiliser ce fichier à votre guise.

**c) Téléchargement sur un serveur de clés**

Les serveurs de clés facilitent la recherche et le téléchargement de clés publiques. La plupart des serveurs de clés modernes se synchronisent, ce qui signifie qu’une clé publique téléchargée sur un serveur atteindra finalement tous les serveurs.

Bien que le téléchargement de votre clé publique sur un serveur de clés puisse être un moyen pratique de faire savoir aux personnes que vous possédez un certificat PGP public, vous devez savoir qu’en raison de la manière dont les serveurs de clés fonctionnent, il est impossible de supprimer les clés publiques une fois qu’elles ont été téléchargées. Vous pouvez uniquement les marquer comme révoqués.

**Avant de télécharger votre clé publique sur un serveur de clés, il est bon de prendre un moment pour déterminer si vous souhaitez que le monde entier sache que vous avez une clé publique sans possibilité de supprimer ces informations ultérieurement.**

Si vous choisissez de télécharger votre clé publique sur des serveurs de clés, vous revenez à la fenêtre Gestionnaire des Clés d’Enigmail.

Cliquez sur l’élément du menu Serveur de clés et sélectionnez l’option Télécharger les clés publiques.
![image](tool_pgplin53.png)

### 6.2 Rechercher d’autres personnes qui utilisent PGP

**a) Obtenir une clé publique par courriel**

Vous pourriez recevoir une clé publique sous forme de pièce jointe dans un courrier électronique.
![image](tool_pgplin54.png)

Double-cliquez sur le nouveau message, un nouvel onglet s’affichera. Remarquez la pièce jointe au bas de la fenêtre. Cliquez avec le bouton droit sur la pièce jointe et sélectionnez "Importer la clé OpenPGP". Une petite fenêtre s’ouvrira vous donnant les résultats de l’importation. Cliquez sur le bouton OK.
![image](tool_pgpwin55.png)

Si vous ouvrez à nouveau la fenêtre du Gestionnaire de Clés d’Enigmail, vous pouvez vérifier le résultat. Votre clé PGP est en gras car vous disposez à la fois de la clé privée et de la clé publique. La clé publique que vous venez d’importer n’est pas en gras car elle ne contient pas la clé privée.
![image](tool_pgplin56.png)

**b) Obtenir une clé publique sous forme de fichier**

Il est possible que vous obteniez une clé publique en la téléchargeant depuis un site Web ou que quelqu’un l’ait envoyée via un logiciel de discussion. Dans ce cas, vous supposerez que vous avez téléchargé le fichier dans le dossier Téléchargements.

Ouvrez le Gestionnaire de Clés d’Enigmail, cliquez sur le menu "Fichier", puis sélectionnez "Importer les Clés à partir d’un Fichier".
![image](tool_pgplin57.png)

La clé publique peut avoir des terminaisons de nom de fichier très différentes, telles que .asc, .pgp ou .gpg. Sélectionnez le fichier et cliquez sur le bouton "Ouvrir".
![image](tool_pgpwin58.png)

Une petite fenêtre s’ouvrira pour vous donner les résultats de l’importation. Cliquez sur le bouton "OK".
![image](tool_pgpwin59.png)

**c) Obtenir une clé publique à partir d’un serveur de clés**

Les serveurs de clés peuvent être un moyen très utile d’obtenir des clés publiques. Essayez de chercher une clé publique. Ouvrez le gestionnaire de clés, puis cliquez sur le menu "Serveur de clés" et sélectionnez "Rechercher des clés".
![image](tool_pgplin60.png)

Une petite fenêtre apparaîtra avec un champ de recherche. Vous pouvez effectuer une recherche par adresse électronique complète, partielle ou par nom. Dans ce cas, vous rechercherez des certificats contenant "eff.org".
![image](tool_pgplin61.png)

Une fenêtre plus grande apparaîtra avec de nombreuses options. Si vous faites défiler l’écran vers le bas, vous remarquerez que certains certificats sont en italique et grisés. Ce sont des certificats qui ont été révoqués ou qui ont expirés par eux-mêmes.
![image](tool_pgplin62.png)

Prenons les clés publiques de Danny O’Brien, par exemple, il a un certificat expiré ou révoqué et un certificat valide. Sélectionnez le certificat valide en cliquant sur la case à gauche, puis appuyez sur le bouton OK.
![image](tool_pgplin63.png)

Dans certains cas, une personne peut avoir plus d’un certificat, tous semblant valables. Notez qu’il est possible pour quiconque de télécharger un certificat public et que l’une de ces clés n’appartienne pas à la personne à qui appartient l’adresse électronique qui lui est associée. Dans ce cas, la vérification de l’empreinte numérique est extrêmement importante.

Une petite fenêtre de notification apparaîtra pour vous indiquer si vous avez réussi.
![image](tool_pgplin64.png)

Le Gestionnaire de Clés d’Enigmail vous montrera désormais les certificats ajoutés :
![image](tool_pgplin65.png)

### 7.1 Envoi d’un courriel chiffré PGP

Vous allez maintenant envoyer votre premier courriel chiffré à un destinataire. Dans la fenêtre principale de Mozilla Thunderbird, cliquez sur le bouton "Écrire". Une nouvelle fenêtre s’ouvrira.
![image](tool_pgpwin66.png)

Rédigez votre message et entrez un destinataire. Pour ce test, sélectionnez un destinataire dont vous possédez déjà la clé publique. Enigmail le détectera et chiffrera automatiquement l’courriel.
![image](tool_pgplin67.png)

_Notez que la ligne d’objet ne sera pas chiffrée, alors choisissez quelque chose d’inoffensif, comme "bonjour."_

Lorsque vous cliquez sur le bouton "Envoyer", une fenêtre s’ouvre pour vous permettre de saisir le mot de passe de votre clé PGP. Rappelez-vous que que ce dernier est différent de votre mot de passe du compte courriel !

Entrez votre mot de passe puis cliquez sur le bouton "OK" et votre courriel sera chiffré et envoyé.
![image](tool_pgpwin68.png)

Le corps de l’courriel a été chiffré et transformé. Par exemple, ce texte :
![image](tool_pgplin69.png)

se transformera comme ceci :
![image](tool_pgpwin70.png)

### 7.2 Réception d’un courriel chiffré PGP

Passons en revue ce qui se passe lorsque vous recevez un courrier électronique chiffré. Remarquez que Mozilla Thunderbird vous notifie d’un nouvel courriel. Cliquez alors sur le message.
![image](tool_pgpwin71.png)

Une petite fenêtre s’ouvre vous demandant le mot de passe de la clé PGP. N’oubliez pas : n’entrez pas votre mot de passe du compte courriel. Cliquez sur le bouton "OK".
![image](tool_pgplin72.png)

Désormais, le message s’affichera comme déchiffré
![image](tool_pgplin73.png)

### 8 Révocation de la clé PGP

**a) Révocation de votre clé PGP via l’interface Enigmail**

Les clés PGP générées par Enigmail expirent automatiquement après cinq ans. Donc, si vous perdez tous vos fichiers, vous pouvez espérer que les gens sauront vous demander une autre clé une fois celle-ci expirée.

Vous avez peut-être une bonne raison de désactiver la clé PGP avant son expiration. Peut-être souhaitez-vous générer une nouvelle clé PGP plus puissante. Le moyen le plus simple de révoquer votre propre clé PGP dans Enigmail consiste à utiliser le Gestionnaire de Clés Enigmail.
![image](tool_pgplin74.png)

Cliquez avec le bouton droit sur votre clé PGP (en gras) et sélectionnez l’option "Révoquer la Clé".
![image](tool_pgpwin75.png)

Une fenêtre s’ouvrira pour vous permettre de savoir ce qui se passe et vous demander votre confirmation. Cliquez sur le bouton "Révoquer la Clé".
![image](tool_pgplin76.png)

La fenêtre du mot de passe s’ouvre, entrez votre mot de passe pour la clé PGP et cliquez sur le bouton "OK".
![image](tool_pgpwin77.png)

Une nouvelle fenêtre s’ouvrira désormais vous permettant de savoir que vous avez réussi. Cliquez sur le bouton "OK".
![image](tool_pgpwin78.png)

Lorsque vous revenez à la fenêtre Gestion des clés d’Enigmail, vous remarquerez une modification de votre clé PGP. Celle-ci est maintenant grisée et en italique.
![image](tool_pgplin79.png)

**b) Révocation d’une clé PGP avec un certificat de révocation**

Comme indiqué précédemment, les clés PGP générées par Enigmail expirent automatiquement après cinq ans. Donc, si vous perdez tous vos fichiers, vous pouvez être sûr que les gens sauront vous demander une autre clé une fois celle-ci expirée.

Comme nous l’avons mentionné précédemment, vous avez peut-être une bonne raison de désactiver la clé PGP avant son expiration.

De même, d’autres personnes peuvent avoir de bonnes raisons de révoquer une clé existante.

Vous pourriez recevoir des certificats de révocation d’amis afin de les informer de leur intention de révoquer leur clé.

Dans la section précédente, vous avez peut-être remarqué qu’Enigmail génère et importe un certificat de révocation en interne lorsque vous utilisez le Gestionnaire de Clés d’Enigmail pour révoquer une clé. Puisque vous avez déjà un certificat de révocation, vous utiliserez celui que vous avez généré précédemment pour révoquer votre propre clé.

Commencez avec le Gestionnaire de Clés d’Enigmail, cliquez sur le menu "Fichier", puis sélectionnez "Importer les Clés à partir d’un Fichier".
![image](tool_pgplin80.png)

Une fenêtre s’ouvrira afin que vous puissiez sélectionner le certificat de révocation. Cliquez sur le fichier, puis cliquez sur le bouton "Ouvrir".
![image](tool_pgplin81.png)

Vous recevrez une notification indiquant que le certificat a été importé avec succès et qu’une clé a été révoquée. Cliquez sur le bouton "OK".
![image](tool_pgplin82.png)

Une fois que vous avez cliqué sur le bouton "OK", vous êtes redirigé vers le Gestionnaire de Clés d’Enigmail et le certificat que vous avez révoqué est grisé et en italique.
![image](tool_pgplin83.png)

Si la clé que vous avez révoquée est la vôtre et que vous avez déjà chargé votre clé publique sur les serveurs de clés, vous souhaiterez réimporter la clé désormais révoquée sur les serveurs de clés, afin que d’autres personnes ne l’utilisent plus.

Maintenant que vous disposez de tous les outils appropriés, essayez d’envoyer votre propre courrier électronique chiffré avec PGP.
