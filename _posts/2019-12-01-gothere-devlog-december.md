---
layout: post
title: GoThere December Devlogs
image: assets/images/gothere/hearts.png
date: 2019-12-14 23:04:42 -0500
---

For this month I am going to add jump animation to the character, add a nice HUD for player's health and jewel counts, level design for level 4 and level 5, and add the mechanism to gain one life back by touching a heart.

# Health HUD
Initially player health is represented by two numbers, one number is the current health and the other is the maximum health. I wanted to improve it and make it look better on the screen, so I changed it to three hearts, if the player loses one life, the hearts will become grey.

Each hit point is represented by a heart image. I have a `hitpoints.cs` script that keeps all the heart images in an array. When the player loses one life, it will modify the colour of the image from white to grey, giving it a grey tint.

```
hearts[i].color = new Color32(70, 70, 70, 255);
```

# Add Simple Water
I added a water shader using Unity's latest light weight render pipeline to add an area of water in my levels. That way the islands are not just floating above the ground, they are actually in the water. When the main character touches the water he will die and the level will reload.

In order to start using the light weight render pipeline, a Pipeline Asset needs to be created in the `assets` folder, this file contains all the settings associated with the render pipeline. Then go to _Edit->Project Settings->Graphics_ and set the pipeline asset to _Scriptable Render Pipeline Settings_ to start using LWRP(light weight render pipeline).

Now the entire project will start using LWRP, but there is an issue. All of my objects are now turned pink because they are still using all the old materials. The solution to this problem is to select all the materials being used by all the objects, select _Edit->Render Pipeline->Lightweight Render Pipeline->Upgrade Selected Materials to LightweightRP Materials_, and that will convert all the materials to LWRP materials and now I can see my objects with the proper color again.

To create a water shader, I created a _Shader->PBR Graph_ in my assets folder and edited it the graph editor. To use this shader graph as a material, right click on the shader graph asset and go to create a new material, that material will automatically use this shader graph. I used a combination of radial shear, voronoi node to add some moving waves to the material. Then I used a combination of gradient noise and normal vector nodes to manipulate the position of the surface. 

Once the water material has been created, drag that material to a plane mesh object to see the end result. Now I have great looking water.

![water-1]({{ site.baseurl }}/assets/images/gothere/water-1.png)

![water-2]({{ site.baseurl }}/assets/images/gothere/water-2.png)
