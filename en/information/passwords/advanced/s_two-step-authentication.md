---
index: 3
title: 2FA
---
# Two-Factor Authentication (2FA)  

*	**Accounts with a password protect your information with something you know.** 
*	**Accounts with 2FA also protect your information with something that you have.**

It's easy to add extra security to your accounts with 2FA, and recommended for everyone.

## To log in with 2FA, set up a second device:  

* A phone that can receive a code by SMS text message; 
* A phone with an authenticator app that you have set up to generate codes; 
* A universal second factor (U2F) token or key, like a Yubikey. 

Even if your password is hacked or stolen, the thief won't be able to log in unless they also have control of the second device, such as your phone, and the special codes that only it can create.

![image](password_adv2.png)

## 2FA apps are more secure than SMS 

SMS text messages can be intercepted, and most U2F devices cost money. The best solution for most people is to use an app like [Google Authenticator](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2). Once they are configured to work with your account, these apps do not require an Internet connection to generate codes.

[FreeOTP](https://freeotp.github.io/) is an open source app that generates codes for 2FA. It is available for iOS and Android devices, and can be used to sign into Google services as well.

The [2FA Directory](https://2fa.directory/) project tracks services and software that allow you to add 2FA.

*If you run communications infrastructure, such as e-mail servers, there is free, open source software you can use to enable 2FA. Look for software offering implementations of the open standard "Time-Based One-Time Passwords" or RFC 6238.*