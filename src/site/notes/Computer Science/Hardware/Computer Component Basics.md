---
{"dg-publish":true,"permalink":"/computer-science/hardware/computer-component-basics/","tags":["nooblet","beginner","unfinished"]}
---

> [!info]
> **This is not a guide on how to build a computer** as there are already plenty of amazing guides on the internet on that.
> 
> If you are interested I'd recommend checking these out:
> - [**PCPartPicker**](https://pcpartpicker.com/) - I'd highly recommend checking out all of PCPartPicker, it has some amazing forums, documented complete builds and a PC builder tool!
> - **YouTube**
> 	- [Linus Tech Tips](https://www.youtube.com/user/linustechtips)
> 	- [Gamers Nexus](https://www.youtube.com/@GamersNexus)
> 	- [Bitwit](https://www.youtube.com/@Bitwit)
> 	- [JayzTwoCents](https://www.youtube.com/@Jayztwocents)
> - **Reddit**
> 	- [r/buildapc](https://www.reddit.com/r/buildapc/)
> 	- [r/buildmeapc](https://www.reddit.com/r/buildmeapc/)
> 	- [r/PcBuild](https://www.reddit.com/r/PcBuild/)
> 	- [r/hardware](https://www.reddit.com/r/hardware/)

A computer is made up of several fairly straightforward pieces, each with their own role in the operation of the device. These are:

# Motherboard ([[Computer Science/Hardware/Motherboard\|MB]])

The [[Computer Science/Hardware/Motherboard\|motherboard]] is the base of your computer. Although it doesn't store your files, run your games graphics or compute your crypto losses on excel, it is still very important. Like the nervous system of your body, **it acts as a communication line between all the other parts of your computer.**

# Central Processing Unit ([[Computer Science/Hardware/CPU\|CPU]])

The [[Computer Science/Hardware/CPU\|CPU]] is the brain of the computer, **its main job is to do mathematical and logical operations in sequence.** We give it a guide on the operations it can do called an [[Computer Science/Hardware/Instruction Sets\|instruction set]]. It is able to do a set of basic operations billions of times a second, and by chaining them together you can do more complex calculations.

# Random Access Memory ([[Computer Science/Hardware/RAM\|RAM]])

[[Computer Science/Hardware/RAM\|RAM]] is the short term memory of the computer and **is where software is stored when it's running, it can only store data when it is powered** and isn't suitable for long-term storage. [[Computer Science/Hardware/RAM\|RAM]] is split up into memory addresses which act as containers for data.

[[Computer Science/Hardware/RAM\|RAM]] is much faster than long term memory like your [[Computer Science/Hardware/SSD\|SSD]] or [[Computer Science/Hardware/HDD\|HDD]]. The [[Computer Science/Hardware/CPU\|CPU]] can look up a specific memory address with the data it needs to operate on quickly. Once it operates on the data it might store it in a different memory address.

> [!warning]
> **Do not download [[Computer Science/Hardware/RAM\|RAM]]. This is a scam. You will get a virus.**
> 
> If you want to know the performance impact of downloading more [[Computer Science/Hardware/RAM\|RAM]], here is a legit website: https://downloadmoreram.com/
# Storage ([[Computer Science/Hardware/SSD\|SSD]]/[[Computer Science/Hardware/HDD\|HDD]])

Storage is what **keeps all the files you download off the internet and software you run on your computer.** There are two main types of storage used in modern computers. The traditional [[Computer Science/Hardware/HDD\|hard disk drive]] (or [[Computer Science/Hardware/HDD\|HDD]]) which consists of disks where the data is written onto it by a magnet, and the newer and much faster [[Computer Science/Hardware/SSD\|solid state drive]] (or [[Computer Science/Hardware/SSD\|SSD]]) which stores your data as trapped charges.

Despite how fast these have gotten, [[Computer Science/Hardware/RAM\|RAM]] is still orders of magnitude faster and it's the reason why we have both in our computers.

# Graphics Processing Unit ([[Computer Science/Hardware/GPU\|GPU]])

It became fairly evident after some time that although the [[Computer Science/Hardware/CPU\|CPU]] was very capable, as graphics got more and more complex, there was a need for **a special processor more suited for graphics processing.** Hence, the [[Computer Science/Hardware/GPU\|GPU]].

The [[Computer Science/Hardware/GPU\|GPU]] has a fairly different internal layout, there is even a special type of [[Computer Science/Hardware/RAM\|RAM]] called **VRAM used for storing graphical data.** They have much fewer operations in their [[Computer Science/Hardware/Instruction Sets\|instruction set]], but in exchange they can do many simple calculations at the same time. This makes them much more suited for graphics work where you are changing the colour value of many pixels at once or operating on matrices for AI workloads.

# Power Supply Unit ([[Computer Science/Hardware/Power Supply Unit\|PSU]])

Desktop computers all come with a built in [[Computer Science/Hardware/Power Supply Unit\|power supply]] that **transforms the AC coming from your wall into DC that your computer can use.** A good power supply can improve the energy efficiency of your computer significantly, although once it provides your computer enough power reliably, there aren't any significant performance or stability benefits to increasing the wattage of your [[Computer Science/Hardware/Power Supply Unit\|PSU]].

On laptops the [[Computer Science/Hardware/Power Supply Unit\|power supply]] AC to DC transformer is built into the charging brick or on some very slim chargers, the plug head.

```ad-info
title: Fun Fact
The reason a power brick warms up so much is due to the waste heat generated during the conversion from AC to DC, making them ideal foot warmers in the winter.
```

# [[Computer Science/Hardware/Battery\|Battery]]

Lithium-ion batteries are a core part of any portable device and are what make many of them so convenient. **It lets you power the device when you are away from a wall outlet.**

Different devices often prioritise the battery to different extents as having a larger battery means less room for cooling and more weight, important factors to consider for a portable device.

Their capacity is often measured in mAh on phones and Wh on laptops, with upper limits often being determined by price, weight or flight restrictions.

> [!info] Fun Fact
> 99Wh is the legal battery size limit for on-flight cabin bags, which is why you won't find any laptops with batteries larger than that.

# [[Computer Science/Hardware/Heat Sink\|Heat Sink]] 

A [[Computer Science/Hardware/Heat Sink\|heat sink]] is a part that is **mounted on top of heat generating components to help cool them down.** They are often compromised of a stack of thin metal fins connected to copper heat pipes that transfer the heat from a component like a [[Computer Science/Hardware/CPU\|CPU]] or [[Computer Science/Hardware/GPU\|GPU]] to the surrounding air.

