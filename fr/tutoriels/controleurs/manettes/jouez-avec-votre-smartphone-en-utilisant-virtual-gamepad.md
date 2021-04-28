---
title: Jouer avec votre smartphone en utilisant Virtual Gamepad
---

# Jouer avec votre smartphone en utilisant Virtual Gamepad

[Le projet de Miroof - Virtual Gamepads](https://github.com/miroof/node-virtual-gamepads) apporte une nouvelle fonctionnalité à Recalbox : jouer aux jeux avec votre smartphone comme manette !

Vous pouvez ajouter jusqu'à 4 manettes à la fois.

* Quand vous connectez votre Recalbox au réseau, vous n'avez qu'à obtenir votre adresse ip locale dans les **OPTIONS RÉSEAU**.
* Puis à connecter votre smartphone sur le même réseau wifi que votre Recalbox, ouvrir votre navigateur web et taper :

```text
http://[ip de la recalbox]:8080
```

Exemple :

```text
http://192.168.1.30:8080
```

* Une nouvelle manette est alors ajoutée dans Recalbox.

Vous pouvez alors **soit démarrer un jeu** ou aller dans les **réglages manettes** pour **affecter cette nouvelle manette** à un joueur.

![Virtual Gamepad](https://github.com/miroof/node-virtual-gamepads/raw/resources/screenshots/standalone.png?raw=true)

Pour plus d'informations sur la fonctionnalité, vous pouvez consulter la source [ici](https://github.com/jehervy/node-virtual-gamepads#features).

