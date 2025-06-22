---
{"dg-publish":true,"permalink":"/game-development/game-physics/delta-time/","tags":["unfinished","beginner"],"noteIcon":"1"}
---

Delta time is the name given to the time between frames in a game. It's used to calculate any time dependent interactions inside a game.

However using delta time has one drawback for use in game physics, and that is the fact that games tend to vary the [[Game Development/Fundamentals/Refresh Rate\|refresh rate]] depending on available computer resources and what is currently on screen. Therefore it can negatively impact the accuracy of physics calculations on say, a mobile device, that runs at a relatively lower [[Game Development/Fundamentals/Refresh Rate\|refresh rate]].

# Fixed Delta Time

To counteract this it's generally advised to use fixed delta time, a predefined internal [[Game Development/Fundamentals/Refresh Rate\|refresh rate]] for specific calculations.

For instance if I set my game's fixed delta time to 16.66ms (=1 second / 60 refreshes) then regardless of if the game is at 90 [[Game Development/Fundamentals/Refresh Rate\|fps]] or at 30 [[Game Development/Fundamentals/Refresh Rate\|fps]] it will exhibit consistent physics behaviours.

```ad-warning
You should avoid putting anything other than physics calculations in fixed delta time as it can cause issues that are difficult to debug.

For example if you check input on every fixed delta time tick/update (let's pick 16.66ms for simplicity), a game running at 140 [[Refresh Rate|fps]] will feel strangely sluggish because the frame updates in 7.14ms, meaning that there is a 2 frame delay between when you enter an input and get a response.
```