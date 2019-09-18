---
index: 13
title: Pidgin
---
# GUIDE POUR PIDGIN

## Guide pour Pidgin
Messagerie instantanée chiffrée pour Windows

**Leçon à lire :**
- [Envoi d’un message](umbrella://communications/sending-a-message)**  
**Téléchargement :**
- [https://pidgin.im/download/](https://pidgin.im/download/)   
- [https://otr.cypherpunks.ca/](https://otr.cypherpunks.ca/)  
**Configuration requise pour l’ordinateur :** Une connexion Internet, un ordinateur exécutant Windows XP ou version plus récente, un compte de messagerie XMPP (Jabber).
_(Pidgin est capable de fonctionner avec de nombreux systèmes de messagerie, mais nous allons maintenant nous concentrer sur XMPP, anciennement Jabber)_
**Version utilisée dans ce guide :**
- Windows 7 Ultimate  
- Pidgin 2.10.9, pidgin-otr 4.0.0-1  
**Licence :** Logiciel libre ; mélange de licences de logiciels libres
**Niveau :** Débutant
**Autres lectures :** [https://pidgin.im/cgi-bin/mailman/listinfo/support](https://pidgin.im/cgi-bin/mailman/listinfo/support)  
**Temps requis :** 20 minutes

**L’utilisation de OTR avec Pidgin vous donnera :**
- La possibilité d’organiser et de gérer certains des services de messagerie instantanée les plus populaires via un programme unique.
- La possibilité d’avoir des discussions chiffrées sur la messagerie instantanée, sans que le serveur les enregistre.
- La possibilité de s’assurer que la personne avec laquelle vous discutez est vraiment cette personne.

### 1.0 Avant de commencer

Pidgin est un client de messagerie instantanée facile à utiliser pour Windows qui utilise un protocole appelé OTR (Off-the-Record), qui permet aux utilisateurs d’avoir des conversations confidentielles.

- Note : OTR ne doit pas être confondu avec"Off the record" de Google, qui désactive simplement la journalisation des discussions et ne dispose pas de fonctionnalités de chiffrement ou de vérification.
- Pidgin prend en charge les services de messagerie instantanée suivants : AIM, Bonjour, Gadu-Gadu, Google Hangouts, Groupwise, ICQ, IRC, SILC, SIMPLE, Sametime, Zephyr et tous les clients de messagerie instantanée exécutant le protocole de messagerie XMPP.
- Pidgin ne permet pas la communication entre différents services de messagerie instantanée. Par exemple, si vous utilisez Pidgin pour accéder à votre compte Google Hangouts, vous ne pourrez pas discuter avec un ami à l’aide d’un compte ICQ.
- Toutefois, Pidgin peut être configuré pour gérer plusieurs comptes en fonction de l’un des protocoles de messagerie pris en charge. En d’autres termes, vous pouvez utiliser simultanément les comptes Gmail et ICQ, et discuter avec des correspondants en utilisant l’un de ces services spécifiques (pris en charge par Pidgin).
- Pidgin, enregistre automatiquement les conversations par défaut, mais vous avez la possibilité de désactiver cette fonctionnalité. Cela dit, vous n’avez pas le contrôle sur la personne avec laquelle vous discutez - elle pourrait enregistrer ou prendre des captures d’écran de votre conversation, même si vous avez désactivé vous-même la journalisation.

**Pourquoi devrais-je utiliser Pidgin + OTR ?**
Lorsque vous discutez avec Google Hangouts sur le site Web de Google, ce chat est chiffré avec HTTPS, ce qui signifie que le contenu de votre chat est protégé contre les pirates informatiques et autres tiers. Il n’est toutefois pas protégé contre Google, qui possède les clés de vos conversations et peut les transmettre aux autorités.

Après avoir installé Pidgin, vous pouvez vous y connecter en utilisant plusieurs comptes en même temps. Par exemple, vous pouvez utiliser Google Hangouts, Facebook et XMPP simultanément. Pidgin vous permet également de discuter en utilisant ces outils sans OTR. Comme OTR ne fonctionne que si les deux personnes l’utilisent, cela signifie que même si l’autre personne ne l’a pas installé, vous pouvez toujours discuter avec eux à l’aide de Pidgin.

Pidgin vous permet également d’effectuer une vérification hors bande pour vous assurer que vous parlez à la personne à laquelle vous pensez parler. Pour chaque conversation, il existe une option qui vous montrera les empreintes de clé qu’il a pour vous et pour la personne avec laquelle vous discutez. Une "empreinte de clé" est une chaîne de caractères du type "342e 2309 bd20 0912 ff10 6c63 2192 1928", utilisée pour vérifier une clé publique plus longue. Échangez vos empreintes digitales via un autre canal de communication, comme les DM Twitter ou un courriel, pour vous assurer que personne n’interfère avec votre conversation.

**Limites : Quand ne dois-je pas utiliser Pidgin + OTR ?**

Pidgin est un programme complexe, qui n’a pas été conçu avec une sécurité comme priorité absolue. Il contient certainement des bugs, dont certains pourraient être utilisés par les gouvernements ou même par les grandes entreprises pour pénétrer dans les ordinateurs qui les utilisent. Utiliser Pidgin pour chiffrer vos conversations constitue un excellent moyen de défense contre le type de surveillance non ciblée utilisé pour espionner les conversations Internet de tout le monde. Toutefois, si vous pensez que vous serez personnellement la cible d’un attaquant disposant de ressources suffisantes (comme un État-Nation), vous devriez envisager des mesures plus strictes, telles que le chiffrement de votre courrier électronique avec PGP.

### 2 Téléchargement et installation

### 2.1 Obtenir Pidgin

Vous pouvez obtenir Pidgin sous Windows en téléchargeant le programme d’installation à partir de la page de téléchargement de Pidgin.
![image](tool_pidgin1.png)

Cliquez sur l’onglet _violet_ TÉLÉVHARGER. _Ne cliquez **pas** sur le bouton vert Télécharger Maintenant car vous allez choisir un fichier d’installation différent._ Vous serez redirigé vers la page de téléchargement.
![image](tool_pidgin2.png)

_À nouveau, ne cliquez **pas** sur le bouton vert Télécharger Maintenant car nous voulons choisir un fichier d’installation différent._ Le programme d’installation par défaut de Pidgin est petit car il ne contient pas toutes les informations et télécharge les fichiers à votre place. Cela échoue parfois, donc vous aurez une meilleure chance avec "l’installateur hors ligne" qui contient tout le matériel d’installation nécessaire.

Cliquez sur le lien de **l’installateur hors ligne**. Vous serez redirigé vers une page nommée "Sourceforge" et après quelques secondes, une petite fenêtre contextuelle vous demandera si vous désirez sauvegarder le fichier.

- Note : Bien que la page de téléchargement de Pidgin utilise "HTTPS" et soit donc relativement protégée contre toute modification, le site Web sur lequel il vous recommande de télécharger la version Windows de Pidgin est actuellement Sourceforge, qui utilise "HTTP" non chiffré et n’offre donc aucune protection. Cela signifie que le logiciel que vous téléchargez peut être altéré avant de le télécharger. Ce risque provient principalement d’une personne ayant accès à l’infrastructure Internet locale qui tente de vous surveiller personnellement (par exemple, un fournisseur de points d’accès malveillants), ou d’un État ou d’un gouvernement qui prévoit de distribuer des logiciels compromis à de nombreux utilisateurs. L’extension [HTTPS Everywhere](https://www.eff.org/https-everywhere) peut réécrire les URL de téléchargement Sourceforge en HTTPS. Il est donc recommandé d’installer HTTPS Everywhere avant de télécharger tout autre logiciel. De plus, selon notre expérience, Sourceforge a souvent des publicités sur ses pages de téléchargement qui peuvent amener les gens à installer quelque chose qu’ils ne souhaitent peut-être pas. Vous pouvez installer un bloqueur de publicité avant tout autre logiciel pour éviter que ces publicités prêtent à confusion.

De nombreux navigateurs vous demanderont de confirmer si vous désirez télécharger ce fichier. Internet Explorer 11 montre une barre en bas de la fenêtre du navigateur avec une bordure orange.
![image](tool_pidgin3.png)

Quel que soit le navigateur utilisé, il est préférable de commencer par enregistrer le fichier avant de continuer. Cliquez donc sur le bouton "Enregistrer". Par défaut, la plupart des navigateurs enregistrent les fichiers téléchargés dans le dossier Téléchargements.

### 2.2 Obtenir OTR

Vous pouvez obtenir pidgin-otr, l’extension OTR pour Pidgin, en téléchargeant l’installateur à partir de la [page de téléchargement OTR](https://otr.cypherpunks.ca/).
![image](tool_pidgin4.png)

Cliquez sur l’onglet "Télécharger" pour être redirigé vers la section "Téléchargements" de la page. Cliquez sur le lien de "l’installateur "Win32 pour pidgin".
![image](tool_pidgin5.png)

De nombreux navigateurs vous demanderont de confirmer si vous désirez télécharger ce fichier. Internet Explorer 11 montre une barre en bas de la fenêtre du navigateur avec une bordure orange.
![image](tool_pidgin6.png)

Quel que soit le navigateur utilisé, il est préférable de commencer par enregistrer le fichier avant de continuer. Cliquez donc sur le bouton "Enregistrer". Par défaut, la plupart des navigateurs enregistrent les fichiers téléchargés dans le dossier Téléchargements.

Après avoir téléchargé Pidgin et pidgin-otr, vous devriez avoir deux nouveaux fichiers dans votre

dossier de Téléchargements :
![image](tool_pidgin7.png)

### 2.3 Installation de Pidgin

Gardez la fenêtre de Windows Explorer ouverte et double-cliquez sur pidgin-2.10.9-offline.exe. On vous demandera si vous souhaitez autoriser l’installation de ce programme. Cliquez sur le bouton "Oui".
![image](tool_pidgin8.png)

Une petite fenêtre s’ouvre vous demandant de sélectionner une langue. Cliquez sur le bouton "OK".
![image](tool_pidgin9.png)

Un fenêtre s’ouvre vous donnant un aperçu rapide du processus d’installation. Cliquez sur le bouton "Suivant".
![image](tool_pidgin10.png)

Vous avez désormais un aperçu de la licence. Cliquez sur le bouton "Suivant".
![image](tool_pidgin11.png)

Vous pouvez désormais voir les différents composants qui sont installés. Ne changez pas les paramètres. Cliquez sur le bouton "Suivant".
![image](tool_pidgin12.png)

Vous pouvez désormais voir où Pidgin a été installé. Ne changez pas cette information. Cliquez sur le bouton "Suivant".
![image](tool_pidgin13.png)

Vous verrez désormais une fenêtre avec un texte déroulant jusqu’à "Installation Complète". Cliquez sur le bouton "Suivant".
![image](tool_pidgin14.png)

Enfin, vous verrez la dernière fenêtre de l’installateur Pidgin. Cliquez sur le bouton "Terminer".
![image](tool_pidgin15.png)

### 2.4 Installation de pidgin-otr

Retournez sur la fenêtre de Windows Explorer, ouvrez puis double-cliquez sur pidgin-otr-4.0.0-1.exe. On vous demandera si vous souhaitez autoriser l’installation de ce programme. Cliquez sur le bouton "Oui".
![image](tool_pidgin16.png)

Une fenêtre s’ouvre vous donnant un aperçu rapide du processus d’installation. Cliquez sur le bouton "Suivant".
![image](tool_pidgin17.png)

Vous avez désormais un aperçu de la licence. Cliquez sur le bouton "J’accepte".
![image](tool_pidgin18.png)

Vous verrez où pidgin-otr a été installé. Ne changez pas cette information. Cliquez sur le bouton "Installer".
![image](tool_pidgin19.png)

Enfin, vous verrez la dernière fenêtre de l’installateur de pidgin-otr. Cliquez sur le bouton "Terminer".
![image](tool_pidgin20.png)

### 3 Configuration

### 3.1 Configuration de Pidgin

Allez dans le menu Démarrer, cliquez sur l’icône Windows et sélectionnez Pidgin à partir du menu.
![image](tool_pidgin21.png)

### 3.2 Ajouter un compte

Lorsque Pidgin sera lancé pour la première fois, cette fenêtre de bienvenue s’affichera pour vous permettre d’ajouter un compte. Puisque vous n’avez pas encore de compte configuré, cliquez sur le bouton"Ajouter".
![image](tool_pidgin22.png)

Vous verrez désormais la fenêtre "Ajouter un Compte".

**_Pidgin est capable de fonctionner avec de nombreux systèmes de messagerie, mais nous allons nous concentrer sur XMPP, anciennement Jabber._**

Dans le champ Protocole, sélectionnez l’option "XMPP".

Dans le champ Nom d’utilisateur, saisissez votre nom d’utilisateur XMPP.

Dans le champ Domaine, saisissez le domaine de votre compte XMPP.

Dans le champ Mot de passe, saisissez votre mot de passe XMPP.

Si vous cochez la case à côté de "Mémoriser le mot de passe", l’accès à votre compte sera facilité. Sachez qu’en cliquant sur "Mémoriser le mot de passe", votre mot de passe sera enregistré sur l’ordinateur, le rendant accessible à toute personne susceptible d’accéder à votre ordinateur. Si cela vous préoccupe, ne cochez pas cette case. Vous devrez ensuite saisir le mot de passe de votre compte XMPP chaque fois que vous lancerez Pidgin.
![image](tool_pidgin23.png)

### 3.3 Ajouter un Ami

Vous désirerez maintenant ajouter une personne avec qui vous désirez parler. Cliquez sur le menu "Amis" et sélectionnez "Ajouter un Ami". Une fenêtre "Ajouter un Ami" s’ouvrira.
![image](tool_pidgin24.png)

Dans la "Fenêtre d’Ajout", vous pouvez saisir le nom d’utilisateur de la personne avec laquelle vous désirez parler. Cet autre utilisateur ne doit pas nécessairement provenir du même serveur, mais doit utiliser le même protocole, tel que XMPP.

Dans le champ "Nom d’utilisateur de l’Ami", saisissez le nom d’utilisateur de votre ami avec le nom de domaine. Cela ressemblera à une adresse courriel.

Dans le champ "Alias (Facultatif)", vous pouvez entrer le nom de votre choix pour votre ami. Ceci est entièrement facultatif, mais peut aider si le compte XMPP de la personne avec laquelle vous discutez est difficile à retenir.

Cliquez sur le bouton "Ajouter".
![image](tool_pidgin25.png)

Une fois que vous avez cliqué sur le bouton "Ajouter", Boris recevra un message demandant s’il vous donne l’autorisation de l’ajouter. Une fois que Boris accepte, il ajoutera votre compte et vous recevrez la même demande.

Cliquez sur le bouton "Autoriser".
![image](tool_pidgin26.png)

### 3.4 Configuration de l’extension OTR

Vous allez désormais configurer l’extension OTR afin que vous puissiez discuter en toute sécurité. Cliquez sur le menu "Outils" puis sélectionnez l’option "Extensions".
![image](tool_pidgin27.png)

Faites défiler jusqu’à l’option "Messagerie Off-The-Record", puis cochez la case.

Cliquez sur le champ "Messagerie Off-the-Record" puis cliquez sur le bouton "Configuration Extension".
![image](tool_pidgin28.png)

Vous verrez désormais la fenêtre de configuration de la "Messagerie Off-The-Record". Notez que cela indiquera "Aucune clé présente".

Cliquez sur le bouton "Générer".
![image](tool_pidgin29.png)

Désormais, une petite fenêtre et générera une clé. Lorsque cela est terminé, cliquez sur le bouton "OK".
![image](tool_pidgin30.png)

Vous verrez une nouvelle information : une chaîne de texte de 40 caractères, divisée en 5 groupes de huit caractères. Ceci est votre empreinte OTR. Cliquez sur le bouton "Fermer".
![image](tool_pidgin31.png)

Cliquez maintenant sur le bouton "Fermer" de la fenêtre Extensions.

### 4.0 Discussion sécurisée

Vous pouvez maintenant discuter avec Boris. Vous pouvez tous les deux envoyer des messages. Cependant, nous ne discutons toujours pas en toute sécurité. Même si vous vous connectez au serveur XMPP, il est possible que la connexion entre vous et Boris ne soit pas sécurisée contre l’espionnage.

Si vous regardez la fenêtre de discussion, notez qu’il est indiqué "Non privé" en rouge en bas à droite. Cliquez sur le bouton "Non privé".
![image](tool_pidgin32.png)

Un menu s’ouvrira, sélectionnez "Authentifier ami".
![image](tool_pidgin33.png)

Un fenêtre s’ouvrira. Celle-ci vous demandera : "Comment désirez-vous authentifier votre ami ?"

La liste déroulante possède trois options :

**Option 1 : Secret partagé**

Un secret partagé est une ligne de texte que la personne avec laquelle vous souhaitez discuter et vous-mêmes avaient accepté d’utiliser à l’avance. Vous devriez l’avoir partagé en personne et ne jamais l’avoir échangé sur des canaux non sécurisés tels que les courriels ou Skype.

Votre ami et vous-mêmes avez besoin de saisir ce texte ensemble. Cliquez sur le bouton "Authentifier".
![image](tool_pidgin34.png)

La vérification du secret partagé est utile si vous et votre ami avez déjà pris des dispositions pour dialoguer à l’avenir mais n’avez pas encore créé d’empreintes OTR sur l’ordinateur que vous utilisez.

**Option 2 : Vérification manuelle de l’empreinte**

La vérification manuelle des empreintes est utile si vous avez déjà reçu les empreintes de votre ami et que vous vous connectez maintenant avec Pidgin. Cela ne sera pas utile si votre ami a changé d’ordinateur ou a dû créer de nouvelles empreintes.

Si l’empreinte que l’on vous a donné et l’empreinte sur l’écran correspondent, sélectionnez "Je possède" puis cliquez sur le bouton "Authentifier".
![image](tool_pidgin35.png)

**Option 3 : Question et réponse**

La vérification par question et réponse est utile si vous connaissez votre ami mais n’avez pas établi de secret partagé ni pu partager vos empreintes. Cette méthode est utile pour établir une vérification en fonction de quelque chose que vous connaissez tous les deux, comme un événement partagé ou un souvenir.

Entrez la question que vous voulez poser. Ne le faites pas simple afin que personne ne puisse le deviner facilement, mais ne le rendez pas impossible non plus. Un exemple de bonne question serait "Où sommes-nous allés dîner à Minneapolis ?" et un exemple de mauvaise question serait "Pouvez-vous acheter des pommes à Tokyo ?"

**Les réponses doivent complètement correspondre ; donc gardez cela à l’esprit lorsque vous choisissez une réponse à votre question. La capitalisation est importante, donc considérez le fait d’inclure une note (exemple : utilisez des majuscules et minuscules).**

Saisissez la question et répondez, puis cliquez sur le bouton "Authentifier".
![image](tool_pidgin36.png)

Votre ami aura une fenêtre ouverte avec la question affichée demandant la réponse. Il devra répondre et cliquer sur le bouton "Authentifier". Il recevra ensuite un message lui indiquant si l’authentification a réussi.
![image](tool_pidgin37.png)![image](tool_pidgin38.png)

Une fois que votre ami a terminé la procédure d’authentification, vous obtenez une fenêtre vous informant que l’authentification a réussi.
![image](tool_pidgin39.png)

Votre ami doit également vérifier votre compte afin que vous puissiez tous les deux être sûrs que la communication est sécurisée. Voici à quoi cela ressemblerait pour Akiko et Boris. Remarquez les icônes "Privées" vertes dans le coin inférieur droit de la fenêtre de discussion.![image](tool_pidgin40.png)

### 5 Fonctionnement avec d’autres logiciels

Les mécanismes de vérification de l’authenticité devraient fonctionner entre différents logiciels de messagerie tels que Pidgin et Adium. Vous n’êtes pas obligé d’utiliser le même logiciel de messagerie pour utiliser la messagerie via XMPP et OTR, mais il y a parfois des erreurs dans le logiciel. Adium, un logiciel de discussion pour OS X, possède une erreur lors de la réception de la vérification par question et réponse. Si vous constatez que la vérification des autres échoue lorsque vous utilisez la vérification par questions et réponses, vérifiez si elles utilisent Adium et voyez si vous pouvez utiliser une autre méthode de vérification.