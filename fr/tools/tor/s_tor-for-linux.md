---
index: 19
title: Tor pour LINUX
---
Tor pour Linux
=========================

L’anonymat en ligne

**Leçon à lire : [Internet](umbrella://communications/the-internet)**  
**Niveau**: Débutant-Avancé  
**Temps requis**: 15 minutes—1 heure   
**Publication :** Avril 2018    
**Sources :** FFÉ, Autodéfense contre la surveillance, [Comment : Utiliser Tor pour Linux](https://ssd.eff.org/fr/module/how-use-tor-linux) ; Security in a Box [NAVIGATEUR TOR POUR LINUX - ANONYMAT EN LIGNE ET CONTOURNEMENT](https://securityinabox.org/fr/guide/torbrowser/linux/). 

**En utilisant Tor, vous obtiendrez :**

* La possibilité de dissimuler votre identité en ligne aux sites Internet que vous visitez
* La possibilité de dissimuler les sites Web visités des fournisseurs de services Internet et des programmes de surveillance
* La possibilité de contourner la censure sur Internet et le filtrage en ligne.
* Protection contre les sites Web non sécurisés et potentiellement malveillants via les modules complémentaires de HTTPS Everywhere et du navigateur NoScript

**Téléchargement :** [https://www.torproject.org/download/download-easy.html.en](https://www.torproject.org/download/download-easy.html.en). Si vous ne pouvez pas accéder à ce site Web, lisez ci-dessous *Si la page de téléchargement est bloquée*.   
**Configuration requise :** Une connexion Internet, un ordinateur opérant votre distribution Linux favorite.  
**Version utilisée dans ce guide** : Ubuntu 16.04.1 LTS ; Navigateur Tor : 7.0.2  
**Licence** : Logiciel gratuit ; mélange de licences gratuites et libres

Introduction 
-------------

Ce guide explique comment utiliser le [Navigateur Tor](https://www.torproject.org/projects/torbrowser.html.en) sous Linux.

Tor est un service géré par des bénévoles qui fournit à la fois la confidentialité et l’anonymat en ligne en masquant qui vous êtes et les endroits où vous vous connectez. Le service vous protège également du Réseau Tor lui-même — vous pouvez donc être rassuré, vous resterez anonyme pour les autres utilisateurs de Tor.

Le navigateur Tor Browser fournit un moyen rapide et facile d’utiliser le réseau Tor pour les personnes qui ont parfois besoin d’anonymat et de confidentialité.

Le Navigateur Tor fonctionne comme un navigateur Web, le programme que vous utilisez pour afficher des sites Web. Les exemples incluent Chrome, Firefox et Safari. Contrairement aux autres navigateurs Web, le Navigateur Tor envoie vos communications par l’intermédiaire de Tor, ce qui empêche les personnes qui vous surveillent de savoir exactement ce que vous faites en ligne, et plus difficile pour les personnes surveillant les sites que vous utilisez de savoir d’où vous êtes connectés.

Gardez à l’esprit que seules les activités que vous effectuez au sein du Navigateur Tor seront anonymisées. Avoir le Navigateur Tor installé sur votre ordinateur ne rend pas anonyme ce que vous faites sur le même ordinateur en utilisant un autre logiciel (tel que votre navigateur Web classique).

**Lectures complémentaires** :

*   [https://www.torproject.org/docs/documentation.html.en](https://www.torproject.org/docs/documentation.html.en)
*   [https://tor.stackexchange.com/](https://tor.stackexchange.com/)
*   [https://www.eff.org/pages/tor-and-https](https://www.eff.org/pages/tor-and-https)
 

Obtenir le Navigateur Tor
-------------------------------------

Ouvrez un navigateur tel que Firefox ou Chrome, puis rendez-vous sur :

[https://www.torproject.org/download/download-easy.html.en](https://www.torproject.org/download/download-easy.html.en)

Si vous utilisez un moteur de recherche pour rechercher le Navigateur Tor, assurez-vous que l’URL soit correcte.

N’utilisez aucune autre source. Si le système vous invite à accepter d’autres certificats de sécurité HTTPS (SSL/TLS), ne continuez pas.

![](torforlinux1.png)

Le site Web aura détecté votre système d’exploitation et vous obtiendrez ainsi le fichier correspondant à votre système d’exploitation. Si cela échoue, vous pouvez cliquer sur le lien situé à côté du bouton violet pour télécharger la version appropriée.

Certains navigateurs vous demanderont de confirmer si vous souhaitez télécharger ce fichier. Firefox affiche une fenêtre contextuelle au milieu de la fenêtre de votre navigateur. Pour tout navigateur, il est préférable de sauvegarder le fichier avant de continuer. Cliquez sur le bouton Enregistrer.

Cet exemple montre la version 7.0.2 du Navigateur Tor. Il est possible qu’une version plus récente du Navigateur Tor soit disponible au téléchargement au moment de la lecture. Veuillez télécharger et utiliser la version actuelle fournie par Tor Project.

![](torforlinux2.png)


Installation du Navigateur Tor 
----------------------------------------

Une fois le téléchargement terminé, accédez au dossier Téléchargements. Assurez-vous de toujours faire confiance au logiciel que vous souhaitez installer et à ce que vous obteniez une copie authentique du site officiel via une connexion sécurisée. Puisque vous savez ce que vous voulez, que vous savez où trouver le logiciel et que le téléchargement a été effectué à partir du site HTTPS sécurisé du Projet Tor, double-cliquez sur le fichier “tor-browser-linux64-7.0.2_en-US.tar.xz”.

![](torforlinux3.png)

Après avoir double-cliqué sur le fichier d’archive du Navigateur Tor, attendez qu’il soit téléchargé, puis choisissez l’emplacement où vous souhaitez extraire son contenu.

![](torforlinux4.png)

Une fois l’extraction complète, ouvrez le dossier “tor-browser_en-US”, puis double-cliquez sur le fichier “Tor Browser Setup.”

![](torforlinux5.png)
 

Utilisation du Navigateur Tor 
-----------------

Vous obtiendrez alors une fenêtre vous permettant de modifier certains paramètres si nécessaire. Vous devrez peut-être revenir et modifier certains paramètres de configuration, mais continuez et essayez de vous connecter au Réseau Tor en cliquant sur le bouton Connecter.

![](torforlinux6.png)

Une nouvelle fenêtre s’ouvrira avec une barre orange illustrant le Navigateur Tor se connectant au Réseau Tor.

![](torforlinux7.png)

La première fois que le Navigateur Tor va démarrer, cela peut prendre beaucoup de temps ; mais soyez patient, dans une ou deux minute, le Navigateur Tor s’ouvre et vous félicite.

![](torforlinux8.png)

Cliquez sur le logo Tor Onion dans le coin supérieur gauche du Navigateur Tor, puis sur Paramètres de Confidentialité et de Sécurité.

![](torforlinux9.png)

Certaines fonctionnalités d’un navigateur Web normal peuvent vous rendre vulnérable aux attaques de type "entre les deux". D’autres fonctionnalités présentaient auparavant des bogues révélant l’identité des utilisateurs. Si vous réglez le curseur de sécurité sur une valeur élevée, ces fonctionnalités sont désactivées. Cela vous rendra plus sécurisé contre des attaquants bien financés qui peuvent interférer avec votre connexion Internet ou utiliser de nouveaux bogues inconnus dans ces fonctionnalités. Malheureusement, la désactivation de ces fonctionnalités peut rendre certains sites Web inutilisables. Le paramètre bas par défaut convient à la protection de la vie privée au quotidien, mais vous pouvez le définir sur élevé si vous craignez des attaquants sophistiqués ou si le fait que certains sites Web ne s’affichant pas correctement ne vous dérange pas.

![](torforlinux10.png)

Enfin, la navigation avec Tor diffère à certains égards de l’expérience de navigation normale. Nous vous recommandons de lire [ces conseils](https://www.torproject.org/download/download-easy.html.en#warning) pour naviguer correctement avec Tor et conserver votre anonymat.

![](torforlinux11.png)

Vous êtes maintenant prêt à naviguer anonymement sur Internet avec Tor.

## Vérifiez si le Navigateur Tor fonctionne

Le Navigateur Tor masque votre *adresse IP* des sites Web que vous visitez. Si cela fonctionne correctement, vous devriez accéder à des sites Web à partir d’une localisation sur Internet qui

- Est différente de votre adresse IP normale
- Ne peut pas être liée à votre emplacement physique

Le moyen le plus simple de le confirmer consiste à visiter le site Web *Tor Check*, qui se trouve à l’adresse suivante [**https://check.torproject.org/**](https://check.torproject.org).

Si vous utilisez **pas** Tor, le message suivant s’affichera :

 ![](not-using-tor.png)


Si vous utilisez Tor, les informations suivantes seront affichées :

 ![](using-tor.png) 

Si vous souhaitez vérifier votre adresse IP apparente à l’aide d’un service qui n’est pas associé au Projet Tor, vous disposez de nombreuses options en ligne. Les exemples qui prennent en charge le chiffrement *https* (ce qui complique la tâche de quelqu’un *autre que* le fournisseur de services qui "simule" le résultat) sont les suivants :

- [https://www.iplocation.net/](https://www.iplocation.net/)
- [https://www.ip2location.com/](https://www.ip2location.com/)

Si vous accédez à ces sites *sans* utiliser le Navigateur Tor, ils doivent afficher votre adresse IP réelle, qui est liée à votre emplacement physique. Si vous y accédez via le Navigateur Tor, ils doivent afficher une adresse IP différente.

## Comment créer une nouvelle identité

Vous pouvez créer une "nouvelle identité" pour votre Navigateur Tor. Lorsque vous le faites, le Navigateur Tor sélectionne de manière aléatoire un nouvel ensemble de relais Tor, ce qui vous fera apparaître comme provenant d’une adresse IP différente lorsque vous visitez des sites Web. Pour ce faire, procédez comme suit :

**Étape 1**. **Ouvrez** le menu du Navigateur Tor

 ![](new-identity.png)

**Étape 2**. **Sélectionnez** *Nouvelle Identité* à partir du menu.

Le Navigateur Tor effacera votre historique de navigation et les cookies puis redémarrera. Une fois qu’il a redémarré, vous pouvez confirmer que vous semblez provenir d’une nouvelle adresse IP, comme décrit dans la section précédente.

Problème en utilisant le Navigateur Tor 
-----------------

Si vous ne pouvez pas vous connecter, essayez l’[assistance](https://www.torproject.org/docs/faq.html.en#DoesntWork).

Si vous ne parvenez toujours pas à vous connecter et que vous soupçonnez que votre accès à Tor est peut-être restreint, veuillez lire *Si le Réseau Tor est bloqué* ci-dessous.

Si vous prévoyez de vous rendre dans une région où vous soupçonnez que l’accès à Tor peut être restreint, lisez la section *Comment reconfigurer l’accès au Réseau Tor* ci-dessous.

#Si la page de téléchargement est bloquée

* Il y a un page concernant l’Offre Groupée du Navigateur Tor sur [Github](https://github.com/TheTorProject/gettorbrowser).
* Vous pouvez également envoyer un courriel à gettor@torproject.org avec la version dont vous avez besoin (Windows, OSX ou Linux) dans le corps du message.
* Envoyez un message direct en disant "aide" à [@get_tor](https://twitter.com/get_tor) sur Twitter pour obtenir des instructions pour demander à Tor via DM.

Avant de télécharger un package du Navigateur Tor pour Linux, vous devez déterminer si vous utilisez un système **32 bits** ou **64 bits**. Avant de l’extraire, vous devez vérifier qu’il est authentique.

**Étape 1**. Lancer l’application *Terminal*

**Étape 2**. Exécutez la commande suivante dans *Terminal* :

`uname –m`

Si vous utilisez un système **32 bits**, *Terminal* affiche `i686` ou` i386`. Si vous utilisez un système **64 bits**, il affichera `x86_64`.

**Étape 3**. **Cliquez** sur le lien de téléchargement et enregistrez l’offre groupée dans un endroit pratique (dans votre dossier *Bureau* ou *Documents*, par exemple, ou sur un périphérique de stockage USB). Vous aurez besoin du fichier **.asc** pour *vérifier* l’authenticité de l’offre groupée en vérifiant sa signature. (Voir le [Guide du Projet Tor sur la vérification des signatures](https://www.torproject.org/docs/verifying-signatures.html.en)).

Vérification du Navigateur Tor
------------------

GnuPG est pré-installé sur de nombreux systèmes Linux. Vous pouvez donc probablement vérifier la *signature Open PGP* du Navigateur Tor sans installer de logiciel supplémentaire. (Pour en savoir plus sur PGP, consultez la leçon sur l’[Courriel](umbrella://lesson/courriel/2) et le [Guide de PGP pour LINUX](umbrella://tools/pgp/s_pgp-for-linux.md).)

**Étape 1**. Importez la clé de signature du *Projet Tor* (**0x4E2C6E8793298290**) en lançant *Terminal* et en exécutant la commande suivante :

`gpg --keyserver x-hkp://pool.sks-keyservers.net --recv-keys 0x4E2C6E8793298290`

En réponse, *Terminal* devrait afficher les éléments suivants :

 ![](torforlinux12.png) 

**Étape 2**. Vous pouvez afficher des informations sur cette clé en exécutant la commande suivante dans *Terminal* :

`gpg --fingerprint 0x4E2C6E8793298290`

En réponse, *Terminal* devrait afficher les éléments suivants :

 ![](torforlinux13.png)

**Étape 3**. À l’aide de *Terminal*, entrez le répertoire dans lequel vous avez enregistré l’un des deux fichiers de l’offre groupée du Navigateur Tor ci-dessous :

- *tor-browser-linux64-5.0.4_en-US.tar.xz* 
- *tor-browser-linux32-5.0.4_en-US.tar.xz*

Ce répertoire devrait également contenir l’un des deux fichiers de signature ci-dessous :

- *tor-browser-linux64-5.0.4_en-US.tar.xz.asc* 
- *tor-browser-linux32-5.0.4_en-US.tar.xz.asc* 

**Important** : Dans les exemples ci-dessus et ci-dessous, ces fichiers proviennent de la version **5.0.4** du Navigateur Tor. **Vos fichiers doivent avoir des numéros de version plus élevés.**

**Étape 4**. Au sein de ce répertoire, exécutez l’une des commandes suivantes dans *Terminal* (selon si vous avez téléchargé la version 32-bits ou 64-bits du Navigateur Tor)

- `gpg --verify ./tor-browser-linux32-5.0.4_en-US.tar.xz{.asc*,}`
- `gpg --verify ./tor-browser-linux64-5.0.4_en-US.tar.xz{.asc*,}`

En réponse, *Terminal* devrait afficher les éléments suivants :

 ![](torforlinux14.png)

Ce qui précède vérifie que la *clé privée* correspondant à la *clé publique* que vous avez importé dans *Étape 1* a bien été utilisée pour générer le fichier de signature que vous avez téléchargé dans *Étape 5* de la section précédente (et que ce fichier de signature s’applique à l’offre groupée du Navigateur Tor que vous avez téléchargé dans *Étape 4* de la section précédente).

**Important** : Comme vous pouvez le constater, GPG affiche un avertissement concernant la clé utilisée pour cette signature. En effet, vous n’avez pas réellement vérifié la clé de signature du Projet Tor. La meilleure façon de le faire est de rencontrer les développeurs du Projet Tor en personne et de leur demander l’empreinte de leur clé de signature. Pour les besoins de ce guide, nous nous basons sur le fait qu’une clé GPG bien connue du Projet Tor (**0x4E2C6E8793298290**) a été utilisée pour créer un fichier de signature confirmant l’authenticité de l’offre groupée du Navigateur Tor que vous avez téléchargé.


# Si le Réseau Tor est bloqué

Si vous souhaitez utiliser le Navigateur Tor à partir d’un emplacement où le Réseau Tor est bloqué, vous devrez utiliser un **relais de passerelle**. Les passerelles ne sont pas répertoriées dans le répertoire public des relais Tor, ils sont donc plus difficiles à bloquer. Certaines passerelles prennent également en charge **les transports enfichables**, qui tentent de dissimuler votre trafic vers et depuis le réseau Tor. Cela permet d’empêcher les filtres en ligne d’identifier et de bloquer les relais de passerelle.

Le transport enfichable par défaut, appelé **obfs4**, rend également un peu plus difficile pour les autres de déterminer que vous vous connectez au réseau Tor. Cependant, Tor n’est en général pas conçu pour cacher le fait que vous utilisez Tor.

Vous pouvez en savoir plus sur les passerelles sur le [site Web du Projet Tor](https://bridges.torproject.org/). Il y a deux façons d’utiliser les passerelles. Vous pouvez activer les **passerelles fournies** ou vous pouvez demander des **passerelles personnalisées**.

### Passerelles fournies

Vous pouvez utiliser les passerelles fournies pour vous connecter au Réseau Tor en procédant comme suit :

**Étape 1**. **Double-cliquez** sur le fichier **Tor Browser Setup**. Cela affichera l’écran de configuration du Navigateur Tor.

 ![](tor-running-1.png)


**Étape 2**. Si vous avez un accès restreint, **cliquez** sur **[Configurer]**.

![](tor-bridges-config.png)

**Étape 3**. **Sélectionnez** **Oui**

**Étape 4**. **Cliquez** sur **[Suivant]** pour afficher l’écran de *configuration de la passerelle*

![](provided-bridges.png)

**Étape 5**. **Sélectionnez** **Connecter avec les passerelles fournies**

**Étape 6**. **Cliquez** sur **[Suivant]** pour afficher l’écran de *configuration du proxy local*

Le Navigateur Tor vous demandera maintenant si vous devez utiliser un *proxy local* pour accéder à Internet. Les étapes ci-dessous supposent que vous ne le faites pas. Si vous le *faites*, vous pouvez vérifier les paramètres de votre navigateur et copier votre configuration du proxy. (Dans Firefox, vous pouvez trouver ces paramètres dans l’onglet *Options > Avancé > Réseau* dans *Paramètres de Connexion*. Dans d’autres navigateurs, vous pouvez les trouver dans *Options Internet*. Vous pouvez également utiliser la fonction *Aide* de votre navigateur pour une assistance supplémentaire.

![](no-local-proxy.png)

**Étape 7**. **Sélectionnez** **Non**

**Étape 8**. **Cliquez** sur **[Connecter]** pour lancer le Navigateur Tor.

![](tor-running-2.png)

Dans quelques instants, le Navigateur Tor va s’ouvrir.


### Passerelles personnalisées

Vous pouvez également vous connecter au réseau Tor via des **passerelles personnalisées**, utilisées par moins de personnes que les **passerelles fournies** et par conséquent moins susceptibles d’être bloquées. Si vous ne parvenez pas à accéder au site Web du Projet Tor, vous pouvez demander des adresses de passerelles personnalisées en envoyant un courrier électronique à l’adresse **bridges@torproject.org**, en utilisant un compte *Riseup*, *Gmail* ou *Yahoo*. Inclure la phrase, **obtenir des passerelles** dans le corps de votre message

Si vous pouvez *accéder* au site Web du Projet Tor, vous pouvez obtenir des adresses de passerelles personnalisées en visitant le site **https://bridges.torproject.org/options** et en suivant les étapes ci-dessous.

**Étape 1**. **Cliquez** sur *Donnez-moi des passerelles !*

 ![](just-give-me-bridges.png)


**Étape 2**. Remplissez le captcha et appuyez sur **entrée**.

 ![](bridge-captcha.png)


Cela devrait afficher trois adresses de passerelle.

 ![](bridge-lines.png)


**Étape 3**. Une fois que vous avez vos adresses de passerelles personnalisées, vous pouvez les **saisir** dans l’écran de *Configuration de la Passerelle Tor* illustré ci-dessous.

 ![](custom-bridges.png) 


## Comment reconfigurer l’accès au Réseau Tor

À tout moment, si vous devez accéder au Réseau Tor différemment, par exemple si vous avez voyagé dans un pays qui bloque Tor, vous pouvez mettre à jour vos paramètres depuis le navigateur en procédant comme suit :

**Étape 1 :** **Ouvrez** le menu du Navigateur Tor

 ![](torbrowser-lin-en-v01-901.png)

**Étape 2.** **Sélectionnez** *Paramètres du Réseau Tor* pour modifier le mode de connexion du Navigateur Tor à Internet.

 ![](custom-bridges.png)

Cet écran vous permet d’activer ou de désactiver les Passerelles et d’ajouter des Passerelles personnalisées, entre autres modifications.

**Étape 3**. Lorsque vous avez terminé, **cliquez** sur **[OK]** et **redémarrez** le **Navigateur Tor**.