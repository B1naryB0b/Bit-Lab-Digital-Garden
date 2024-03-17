---
{"dg-publish":true,"permalink":"/game-development/game-physics/colliders/","tags":["unfinished","beginner"]}
---

Colliders are the boundaries the game engine uses for detecting if two objects are in contact or overlapping each other. 

# How do they work?


# Collision simplification

Colliders can be completely divorced from the meshes or sprites of the object and in many cases are significantly simplified due to the computational cost of checking collisions.

This is the primary reason why [[Game Development/Primitive Shapes\|primitive shapes]] are used for most collision checks even if the [[Game Development/Meshes\|mesh]] geometry is more complex. In many instances there is little need for highly accurate collision bound geometry.

