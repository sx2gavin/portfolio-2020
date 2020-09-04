---
layout: video
title: Building Escape - Tech Demo
description: Building Escape is a tech demo made in Unreal Engine 4.
image: assets/images/buildingescape/room.png
video: https://www.youtube.com/embed/KYLty_B-mXw?autoplay=1&controls=0
show-tile: true
---

Building Escape is a tech demo I created in Unreal Engine 4. It is a dungeon puzzle game that requires the player to solve the hidden puzzle and escape the dungeon. I used [Medieval Dungeon](https://www.unrealengine.com/marketplace/en-US/product/a5b6a73fea5340bda9b8ac33d877c9e2) asset package from Unreal Engine Marketplace to create this level.

# Technical Details
I implemented all the gameplay parts using both blueprint and C++. Specifically, I used Trigger Volumes to control when the doors can be opened or closed, and I used Physics Handle component to grab objects from the scene. In the Demo, two objects are grabbable in the scene, they are both given a weight on them. The Trigger volume will calculate how much weight are the objects within the volume. If it exceeds the weight threshold, the associated door will open. 
