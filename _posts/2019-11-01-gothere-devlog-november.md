---
layout: post
title: GoThere November Devlogs
image: assets/images/gothere/terrain.png
---

For this month I added some audio in GoThere, added collectable jewels, added audio mixer to adjust volumes for different audio sources of the game, created low poly terrain using Blender, added some VFX to the game and added saving and loading for my game.

# Audio
For audio, I added a nice little background music for the game, it is a very happy background music. I also added foot steps sound and touch jewel sound. I attached the background music as a Audio Source on the camera so it is always close to the Audio Listener, which is also attached to the camera.

In order to mix all the sounds, an audio mixer is used to adjust all the volumes for each audio source. This is better than finding each audio source and adjust volume separately.

![mixer]({{ site.baseurl }}/assets/images/gothere/mixer.png)

# Gem
I added a collectable object that looks like a gem. For each level there will be three gems to be collected. Each gem presents a challenge to the player to obtain it. Added mechanism to touch a gem and obtain it.

# Low Poly Terrain
I created a terrain using Unity's default terrain tool but I didn't like the result because it looked very smooth. I wanted to have a low poly feel for my game so I exported my terrain as an .obj file and then imported into Blender, then I used Blender to modify the terrain to decrease its poly count to have that low poly feel.

### Terrain Created by Unity Terrain Tool
![old_terrain]({{ site.baseurl }}/assets/images/gothere/old_terrain.png)

### Low Poly Terrain Using Blender
![terrain]({{ site.baseurl }}/assets/images/gothere/terrain.png)

# VFX
Added some particle system effects for dust and blood. For simplicity I just generate small cubes to represent dust or blood.

### Dust
![dust]({{ site.baseurl }}/assets/images/gothere/dust.png)

### Blood
![blood]({{ site.baseurl }}/assets/images/gothere/blood.png)
