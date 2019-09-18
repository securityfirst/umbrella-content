---
index: 6
title: Efail
---
**Efail**
=====================================

**Date :** 15 Mai 2018

Cette semaine, des chercheurs en sécurité ont publié des informations sur les vulnérabilités des clients de messagerie PGP susceptibles d’exposer du contenu passé ou futur, même s’il était chiffré. La FFÉ [a averti](https://www.eff.org/deeplinks/2018/05/not-so-pretty-what-you-need-know-about-e-fail-and-pgp-flaw-0) les utilisateurs de ces clients de messagerie pour désactiver ou désinstaller les extensions PGP et passer à une autre méthode de communication sécurisée. Thunderbird avec Enigmail est recommandé dans les guides PGP d’Umbrella pour [Linux](umbrella://tools/pgp/s_pgp-for-linux.md), [Mac OS](umbrella://tools/pgp/s_pgp-for-mac-os-x.md) et [Windows](umbrella://tools/pgp/s_pgp-for-windows.md).)
.

Voici ce que vous devez savoir :

* Les services de messagerie sécurisés tels que Signal sont plus faciles, plus courants et donc plus fiables que le chiffrement du courrier électronique. C’est donc un bon conseil. Si vous envoyez des informations sensibles, faites-le dans un message sécurisé au lieu d’un courriel. (Apprenez-en plus sur l’[envoi d’un message](umbrella://communications/sending-a-message).)
* La FFÉ suggère de désactiver les clients de messagerie PGP pour les empêcher de déchiffrer automatiquement les messages, ce qui *pourrait* rendre le contenu vulnérable. C’est également un bon conseil, mais comme le dit la FFÉ, il s’agit d’un palliatif "temporaire et conservateur". Cela ne signifie *pas* que le chiffrement PGP n’est pas sécurisé ou que vous devez envoyer un courrier électronique non chiffré.
* Comme dans tous les scénarios de sécurité, prenez en compte votre modèle de menace personnel. (Apprenez-en sur la [gestion de l’information](umbrella://information/managing-information).) Si vous courez un risque élevé d’attaques sophistiquées et ciblées sur le contenu chiffré de vos courriels, un palliatif conservateur sera approprié. Si votre risque est faible, il se peut que ce ne soit pas le cas.

Si vous choisissez de continuer à utiliser le courrier électronique, il est préférable de le chiffrer à l’aide de PGP que de ne pas le chiffrer du tout. Procédez alors comme suit :

1. Assurez-vous que tous les logiciels que vous utilisez sont à jour. Installez les nouvelles mises à jour *immédiatement*. (Vous le ferez si vous avez lu la leçon de Umbrella sur les [programme malveillant](umbrella://information/malware).)
2. Vérifiez les [paramètres](https://twitter.com/GPGTools/status/995986721891405825?s=19) dans votre client de messagerie pour une option permettant de "charger le contenu distant dans les messages". Cette option doit être désactivée ou *décochée*. En effet, l’attaque suppose qu’un pirate informatique peut déjà accéder à votre courrier électronique chiffré et modifier le code HTML qui extrait du contenu, tel que des images, depuis un serveur distant. Ce changement pourrait leur permettre de voir l’intégralité de l’courriel sans chiffrement si le client de messagerie n’a pas encore implémenté la mise à jour appropriée.
3.  Suivez attentivement les développements Efail. Nous publierons des mises à jour sur Twitter [@_SecurityFirst](https://twitter.com/_SecurityFirst).