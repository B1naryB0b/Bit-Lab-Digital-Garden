---
{"dg-publish":true,"permalink":"/game-development/cameras/camera-shake/","tags":["beginner","intermediate","2D","3D","unfinished"]}
---

This page was inspired by a GDC talk on the topic.

>Camera shake is like salt, add a bit and you're golden. Add too much and you throw up.
>- Me

> [!tldr]
> - Use camera shake consistently and reserve it as a means of giving the player feedback.
> - Use smoothed [[Game Development/Noise/Perlin Noise\|perlin]]/[[Game Development/Noise/Simplex Noise\|simplex]] noise as they create a more natural and smooth camera shake. It also allows you to slow down time in the game wihtout gittering and unlocks the ability to create shaky cam style camera shake.
> - You can use both translational and rotational camera shake in 2D. Use only rotational in 3D to prevent camera clipping.
> - Use camera shake ***EXTREMELY*** sparingly in VR as too much can cause people to vomit uncontrollably.
