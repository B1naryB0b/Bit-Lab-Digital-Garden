---
{"dg-publish":true,"dg-path":"Bit Hubs/Graviton Universal Gravity System.md","permalink":"/bit-hubs/graviton-universal-gravity-system/","hide":true,"hideInGraph":true,"noteIcon":"1"}
---


# **Falling** with *Style*

This is our journey to building a gravity system that 
**"Just Works"**

---

### Some Background

The system I'm going to show is being developed for a game with working title **Graviton**

Although, as with all working names, I get the feeling it's going to *stick*

**NOTE: This is a WIP, have mercy**

---

![TitleCard_03.png|1080](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/TitleCard_03.png)

I'm working on this as part of a small indie studio called Lunaboot studios, we are currently looking for funding for this project so if you are interested feel free to send me a DM. Anyways, now that that's out the way what actually IS the game.

---

The pitch:

It's a combination of

**Portal + Monument Valley + SUPERHOT**

---

The puzzle and narrative design elements of portal

![old_testchamber.webp|1080](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/old_testchamber.webp)

---

The surface traversal of monument valley

![caledonia.jpg|540](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/caledonia.jpg)

---

And the bullet time of super hot

![545c9ed2-051a-4548-8203-676ea9ccc62b-2560x1440-50a78bf68aecdf1a565ab646ce463eae.jpg|1080](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/545c9ed2-051a-4548-8203-676ea9ccc62b-2560x1440-50a78bf68aecdf1a565ab646ce463eae.jpg)

---

The core thesis of the game is that:
### **Everything** is *Relative*

---

<iframe src="https://www.youtube.com/embed/4JZPQ9T5hMw" title="Graviton Demo Reel" style="width: 100%; aspect-ratio: 16/9; border-radius: 8px; overflow: hidden;" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

There is no singular time scale, you can slow things down, speed them back up, have them interact with each other or animate at multiple different time scales.

And there is no specific up or down direction. If you can draw a continuous path from A to B, you can walk it.
 
---

### How did we get **here?**

Lets start from the beginning as there were many, many poor decisions made along the way.

---

### The Prototype

We made our first prototype in Unity and got quite far along, we even had a level editor and plans to have a system that allowed us to build the game inside the game. But the more we worked in Unity the more we realised the physics engine being a black box was going to be a problem.

<iframe src="https://www.youtube.com/embed/is-QEFXtPX4" title="Graviton Unity Prototype" style="width: 100%; aspect-ratio: 16/9; border-radius: 8px; overflow: hidden;" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

So we
### Migrated to Unreal & Perforce

**List of mistakes**
- We **self-hosted** our own instance of Perforce, terrible idea really
- We had **no workflow** plan, well nothing concrete at least
- We made a **fork of the engine** (seriously what were we thinking)

*They did all pay off on the end but they sure did suck in the moment*

---

And to top it all off I had
### Basically never used Unreal before

![How hard can it be meme.webp|720](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/How%20hard%20can%20it%20be%20meme.webp)

---

We got to rebuilding, so
### Under the hood

we had a self-orienting character controller that aligned to a given direction and calculated it's forward and right directions based on that

![Player Orientation.excalidraw.png|480](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/Player%20Orientation.excalidraw.png)

---

Every piece of the environment modular kit would have a custom trigger box we called a rotator. When the player is inside the rotator they return a direction based on a mathematical function for which way is up to the CC.

For overlapping rotator we used a priority system that just checks which rotator had a higher priority order and used the vector from that one.

![Rotators.excalidraw.png|600](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/Rotators.excalidraw.png)


---
But there was
### A problem
Complex shapes were still *complex*, very complex

imagine trying to get something like this working, even with basic shapes it's definitely not easy

![1_bmOXIEfUPQ7V1UpY9xYvcA.jpg|540](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/1_bmOXIEfUPQ7V1UpY9xYvcA.jpg)

---

Also, it

**Takes too long per piece**

![Screenshot 2025-02-16 212902.png|720](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/Screenshot%202025-02-16%20212902.png)

On top of making the mesh, you would have to:
- Research the needed function 
- Create a prefab/blueprint
- Test edge cases/bugs 

*End-to-end, probably around 4hrs/pcs*

---

At **300-400pcs** that's between: **1200-1600hrs** of **programmer time**

And 

*This does **NOT** include art time spent making trigger meshes*

---

And arbitrary shapes? **a pipe dream**

![TWcb-NAVqnU-ytQq.jpeg|720](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/TWcb-NAVqnU-ytQq.jpeg)

---
### A new (old) way to do gravity

**Vector fields** have been around for a long time and have been used for describing gravitational fields since before I was born

Could we use our environment surfaces to create a vector field instead of creating the function and meshes for it ourselves?


![VectorField.svg.png|480](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/VectorField.svg.png)

---

We start by projecting the normals and stepping them out a few times, creating what we call the normal field, this already gives use a pretty decent field to use for the player direction

![Normal Field.excalidraw.png|540](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/Normal%20Field.excalidraw.png)

---

We run a k nearest neighbour algorithm to sample the closest normals in the field and viola, we have the direction of the player

![KNN.excalidraw.png|540](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/KNN.excalidraw.png)

---

Now for our game we want to have cut off points around sharp edges, that way the player doesn't accidentally snap to a wall they should be sliding down.

To do this we find the closest vector in the normal field and use that as our alignment vector and use a dot product to filter or cull any vectors in our k closest normals for the direction sampling

![Alignment Culling.excalidraw.png|540](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/Alignment%20Culling.excalidraw.png)

---

Now to help smooth things out we use a weighting function for calculating the falloff in influence of each of the sampled vectors

we can use 1 / sqr dist, a gaussian, polynomial or exponential falloff for the weight function, we are still experimenting with this at the moment

![Weighting.excalidraw.png|540](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/Weighting.excalidraw.png)

---

However, there is still an issue with using normals directly, and that is that the field isn't uniform, and therefore you can have places with much higher and lower vector density which can create some weird snapping in parts of the environment, particularly in the air around the piece.

Instead we ran the above for discrete points in space to create a uniform vector field we call the gravity field. This produces a much smoother and more consistent experience when sampled.

![Vector Field.excalidraw.png|540](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/Vector%20Field.excalidraw.png)

---

Now that we had gotten the easy bit out of the way, we move onto the next phase:
### Just optimise it bro

![can-i-get-a-virus-from-my-potato-pc-v0-bscpyh0w76ec1.webp|540](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/can-i-get-a-virus-from-my-potato-pc-v0-bscpyh0w76ec1.webp)

---

We started with the low hanging fruit, with most of the computation being in the KNN we used Unreal's `Heapify()` function to build
### Heaps for KNN

A heap essentially maintains a specific order (in our case a min-heap) where parents are always smaller than their children

By building the heap we could quickly get the shortest distances

Heaps allow for **`O(n) + O(k log(n))`** rather than the **`O(n log(n))`** of the naïve solution of just going through every element in the array
![minheap_0.png|600](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/minheap_0.png)

---

For very large **`n`** we get:
**`O(n) + O(k log(n)) ~ O(n)`**

![0_P5FlnSY6h2Y7hAE5.png|600](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/0_P5FlnSY6h2Y7hAE5.png)
So as the vector field density increased the performance gains were more apparent

---

Next was
### Spacial partitioning

We chose octrees because **they are built into the engine**, but we might change it for something more optimised for uniform grids

![ec4384970592733fa1afd8d3b5c726fd23d74e46_2_1024x623.png|600](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/ec4384970592733fa1afd8d3b5c726fd23d74e46_2_1024x623.png)

---

In Unreal they have a class called `TOctree`... which is DEPRECATED, so how does Epic Games fix this? By slapping a number on the end of the class and calling it a day

And thus, TOctree**2** was born

Epic, I get why you did it, but I still hate it

```cpp
class TOctree : public TOctree_DEPRECATED
```

```cpp
class TOctree2
```

---

By partitioning the sampling space we could reduce `n` significantly and improve performance without affecting the final output quality, especially for sparse grids with empty regions

We use it for:
- **Sampling candidates** for the KNN 
- **Culling points** far away from a projected normal

By doing this **we can skip massive parts of the level** and do global vector field generation

---

But what use is this if we leave the hardware untapped, so we decided to
### Give it more **JUICE**

The setup is **currently multi-threaded on the CPU** for the most intensive parts

And we are going to be **adding a GPU implementation** to allow for a hybrid of both

---

### Going Forward

**We aren't done yet**

![test_chamber_concept-4.png|600](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/test_chamber_concept-4.png)

---

**Signed distance fields** for all meshes using a **jump flood algorithm**

![9f18748a-f13d-4f94-bc37-4c4efcee2ed9_1920x1080.jpg|600](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/9f18748a-f13d-4f94-bc37-4c4efcee2ed9_1920x1080.jpg)

---

**Generate lookup textures** for gravity (similar to baking lightmaps)

![Hald_CLUT_view.png|400](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/Hald_CLUT_view.png)

**Streaming** LUTs to reduce memory footprint

---

**And many more**
- Vector field per volume settings
- Dynamic field generation
- Static and dynamic field blending
- Spatial hashing
- *Etc*


---

# Q&A

*Assuming I haven't been kicked off stage already*

![princaple1 copy.jpg|600](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/princaple1%20copy.jpg)

---
# Thanks for listening!

![2t3cra.jpg|600](/img/user/_Bit%20Lab%20Organisation/Bit%20Lab%20Site%20Images/2t3cra.jpg)