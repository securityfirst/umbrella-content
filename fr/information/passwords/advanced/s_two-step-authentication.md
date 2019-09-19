---
index: 3
title: 2FA
---
# Authentification à deux facteurs (2FA)

*   **Les comptes avec un mot de passe protègent vos informations à l’aide de quelque chose que vous *connaissez***
*   **Les comptes avec 2FA protègent également vos informations avec quelque chose que vous *possédez.***

Il est facile d’ajouter une sécurité supplémentaire à vos comptes avec 2FA, et cela est recommandé à tout le monde.

## Pour vous connecter avec 2FA, configurez un deuxième appareil :

* Un téléphone pouvant recevoir un code par message texte SMS ;
* Un téléphone avec une application d’authentification que vous avez configurée pour générer des codes ;
* Un jeton ou une clé universelle de second facteur (U2F), comme Yubikey.

Même si votre mot de passe est piraté ou volé, le voleur ne pourra pas se connecter s’il ne contrôle pas également le deuxième appareil, tel que votre téléphone, et les codes spéciaux que seul ce dernier peut créer.

![image](password_adv2.png)

## Les applications 2FA sont plus sécurisées que les SMS

Les messages SMS peuvent être interceptés et la plupart des appareils U2F sont coûteux. La meilleure solution pour la plupart des gens consiste à utiliser une application telle que [Google Authenticator](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2).

Le projet [Two Factor Auth](https://twofactorauth.org/) suit les services et les logiciels permettant d’ajouter 2FA.
