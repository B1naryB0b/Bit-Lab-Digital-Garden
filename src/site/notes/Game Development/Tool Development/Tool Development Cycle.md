---
{"dg-publish":true,"permalink":"/game-development/tool-development/tool-development-cycle/","tags":["unfinished"],"noteIcon":"1"}
---

>**"Tools live longer than games"**
>-Some GDC speaker I can't remember the name of

Tools are a peculiar type of software, in that, **considering how much time is spent on them, most will only be used by a few dozen people.**

However don't let this fool you into thinking tools aren't too important. Tools can often make or break a game's development, they can be a major factor in determining the scope of a project.

> [!warning]
> This is especially true for solo developers and small studios:
> 1. **Don't over-scope your tools**, you don't need a full fledged level editor for a game with only one level (or maybe you do, who knows 🤷).
> 2. You are building a game, **any tool you make should help you build the game faster or better. If it doesn't**, and I can't stress this enough, **DON'T MAKE THE TOOL.**
> 3. **Don't reinvent the wheel without a very good reason.** Only do so if existing tools don't meet your needs or integrate well with your workflow. Check out the [[Game Development/Tool Development/Tool Library\|tool library]] if you want to find anything.

> [!tip]
> Use the **reduce, reuse, recycle** mentality. Reduce the number of tools you need to build in the design of your game, reuse tools that already exist if possible and if you must make tools, try to recycle them for future projects.

# Outline 

## Identify the Problem 

Identify the problem you are trying to solve. Define the parameters for it. **There is no point in developing a tool for a problem that doesn't exist** or can already be solved efficiently with existing tools.

## Audience Determines Interface 

**The end user of your tool will determine the user interface.** A tool built for artists is very different to one built for programmers, **look at the kinds of tools they already use as a guideline.** Although you should try to make the tool as intuitive to use as possible regardless.

Most engines allow you to use their editor APIs to create custom user interfaces and there are even tools for building other tools more effectively. These are things such as Odin Inspector for Unity or similar tools.

Although you can get away with minimal UI for more technical roles or if you are the only developer. In most cases you want to **have the UI feel native to the engine**, the highest compliment a tool developer can get is being told "I didn't even realise it wasn't part of the engine."

## Prototype and Feedback

> [!note]
> The later stuff only applies to larger tools. For simple tools you can put together in an hour you might not need to go through all this.

Tools, like any other type of software, should be prototyped before going into full development. 

Feedback in these early stages is crucial, even if it is from yourself. Have the tool be used for its intended purpose during testing.

Did it bug out? Is this a flawed implementation? Or maybe it's a flawed way of solving the problem?

Regardless, **prototype, get feedback, identify issues, rinse and repeat** until you are happy with the direction you are taking, or you have to hit a deadline.

## Development

I would **recommend putting a time limit on yourself for completing a tool** (unless this is your full time job). You can sink in as many hours as you like, **there will always be some use case your tool won't be able to cover** and that will require additional game development time. It's normal, just get as many *useful* features as possible done in that time.

## Documentation

This is the part many new tool developers skip. **Not documenting is a cardinal sin** and the punishment is that no one will be able to use your tool, not even you, 6 months from now.

All tools should have, **at the bare minimum, a [[Software Development/Documentation/README\|README]] file** with some explanation for:
- What the tool is for
- How to use it (give an example if possible)
- Which version of your game engine it is for

**In general, more is better**, but it's highly recommended to at least meet those 3 requirements.

**Tooltips for each setting** when you hover over them also **offer a way to document** what the tool does or what it's parameters adjust. **Just don't go overboard with this for small tools** whose purpose can be described in a single sentence and for parameters that are self evident.

## Recycle

**This phase should occur after you have completed most if not all of your game.** It is a good way to spend pre-production time prepping for your next project, especially before any concrete design decisions have been made. 

This is where you take the tools that you are most likely to reuse in future projects and **make them more generic so that they are usable for a wider variety of game projects.** Pick tools that are more universal time savers to recycle first, things like menu builders, visual debuggers and art pipeline tools. **More game specific systems are also important but might not be worth modifying** due to time or complexity constraints. For instance you might be better off creating a custom camera script rather than turning your old one into a universal camera controller.

Once you have done that you need to decide on how you will **package these tools for recycling.** Many engines feature package/plugin managers that allow you to quickly create and import packages/plugins for a range of projects. This allows you to **download only the tools that you need to carry forward to your new project.**