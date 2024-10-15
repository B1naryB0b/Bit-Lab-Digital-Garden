---
{"dg-publish":true,"permalink":"/game-development/game-jams/","tags":["unfinished"]}
---

Game jams, inspired by jamming in music, are game making marathons that can be anywhere from 1 hour to multiple months with the gold standard for a game jam being the 48 hr long weekend game jam.

These are no/low stakes competitions to create a game. Rules vary from jam to jam, but generally you are given a theme for the game and they ask you to build as much of the game from scratch as possible. The theme is normally revealed at the start of the jam to act as inspiration and prevent people from getting an early start.

And although game jams are *technically* competitive. The end goal is really to have fun and experiment with different game ideas.

# Experimenting

Game jams are the perfect testing ground for experimental games. If you want to test out a mechanic or full game.

Just note that if you are thinking of turning it into a full game later on, start from scratch or refactor. Most of the time the code and assets made in the game jam aren't your best work, and often it will save you time to structure the project properly from the beginning.

# Solo Jammers

The main point of solo jamming tends to be to develop your personal skills and to improve your abilities as a generalist. The constraint of having to take on every aspect of your game yourself, means you have to learn about a wide range of disciplines outside your comfort zone. It also gives you a much better idea of your limits (currently) than when working as part of a team.

This is considered the original game jam, a test of an individuals skill in making a whole game from scratch, without the use of external assets (although any tool is allowed), and within a 48 hour time limit. 

# Team Building

Game jam teams can vary in size wildly, from a 2-man band to over a dozen people working on a project.

There can be a huge range of skill level and disciplines in a game jam team. With many roles that need filling, people might be doing certain things for the first time, so it's beneficial to have a good spread of roles covered where possible.

Here are some example roles:
- [[Game Development/Roles/Programmers\|Programmers]]
- [[Game Development/Roles/Artists\|Artists]] 
- [[Game Development/Roles/Designers\|Designers]] 
- [[Game Development/Roles/Composers\|Composers]] 
…and many many more.

It's important to have a good spread of roles on your team, however you also need to identify which game ideas suit your teams composition. There is no point in making a 3D puzzle game with 2 [[Game Development/Roles/Composers\|composers]] and a [[Game Development/Roles/Writers\|game writer]], you would be much better off making a visual novel or text based adventure game. Similarly you don't want to make a rhythm game with 2 [[Game Development/Roles/Programmers\|programmers]] and an [[Game Development/Roles/Artists\|artist]], when you would be better off making that 3D puzzle game.

**Play to the strengths of your team. Making games is hard enough, don't shoot yourself in the foot.**

# Team Work

Once you exceed 3 people it becomes increasingly important to have someone to take on a [[Game Development/Roles/Producers\|producer]] role, although they might work on other things too. 

The reason for this is that communication and feature prioritisation become exponentially more difficult as the number of people increases. It's very easy for scope to creep when you add something that creates work for other members of your team, especially because it's often difficult to judge how long something outside your discipline will take.

```ad-fail
title:DON'T

A [[Programmers|programmer]] is working on an enemy health script. When the enemy takes damage, it should give some feedback to the player. 

So they implement a white flash effect, but feel like it could be better, so they also have it trigger a particle effect and leave it to the artist to figure out how to make it fit each enemy.
```
```ad-check
title: DO

The [[Programmers|programmer]], instead of implementing the particle effect trigger right away, asks the artists if they should. If the answer is:
NO - Don't add it
DON'T KNOW - Don't add it
MAYBE - Don't add it, but put it on a list as a strech goal
YES - Add it, but keep it simple
```

