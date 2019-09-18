---
index: 93
title: Chiffrement de clé publique
---
# Chiffrement de clé publique

Les systèmes de chiffrement traditionnels utilisent le même secret, ou clé, pour chiffrer et déchiffrer un message. Donc, si je chiffre un fichier avec le mot de passe "bluetonicmonster", vous auriez besoin à la fois du fichier et du secret "bluetonicmonster" pour le décoder. Le chiffrement par clé publique utilise deux clés : une pour chiffrer et l’autre pour déchiffrer. Cela possède toutes sortes de conséquences utiles. D’une part, cela signifie que vous pouvez distribuer la clé pour chiffrer les messages, et tant que vous gardez l’autre clé secrète, n’importe qui avec cette clé peut vous parler en toute sécurité. La clé que vous distribuez largement est connue sous le nom de "clé publique" : d’où le nom de la technique. Le chiffrement par clé publique est utilisé pour chiffrer les courriels et les fichiers par Pretty Good Privacy (PGP), OTR pour la messagerie instantanée et SSL/TLS pour la navigation Web.