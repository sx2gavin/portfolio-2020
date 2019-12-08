---
layout: post
title: GoThere December Devlogs
image: assets/images/gothere/hearts.png
date: 2019-12-01 23:15:42 -0500
---

For this month I am going to add jump animation to the character, add a nice HUD for player's health and jewel counts, level design for level 4 and level 5, and add the mechanism to gain one life back by touching a heart.

# Health HUD
Initially player health is represented by two numbers, one number is the current health and the other is the maximum health. I wanted to improve it and make it look better on the screen, so I changed it to three hearts, if the player loses one life, the hearts will become grey.

Each hit point is represented by a heart image. I have a `hitpoints.cs` script that keeps all the heart images in an array. When the player loses one life, it will modify the colour of the image from white to grey, giving it a grey tint.

```
hearts[i].color = new Color32(70, 70, 70, 255);
```