# AOF (All Of Funs) Software Development Organization

### *Who* we are?

An open source organization from China

We love FOSS

### [Our project](https://github.com/AOF-Dev)

## Other Languages

- [Chinese](./README_zh-CN.md)

# Table of Contents

- [Team Introduction](#Team-Introduction)
- [History](#History)
- [DVM and JVM Virtual Machine](#Virtual-Machine)
- [Game Performance and Error Reporting](#Game-Performance)
- [Current Situation and Future Direction](#Situation)

### <span id="Team-Introduction">Team Introduction</span>

AOF is actually the abbreviation of After Our Friday, which translates to mean "after the holiday" development team (unfortunately, after friday is not necessarily a holiday 😂)

[**Team Homepage** ](https://github.com/AOF-Dev)

 [**Team members**](https://github.com/orgs/AOF-Dev/people)

- longjunyu2 (initiator, main author of MCinabox)  
- JVM (the main author of Boat)  
- Wind
- lambda  
- MCredbear
- ShirosakiMio (澪)
- tsaltedfishking
- (Several developers in the development group who have modified Boat or MCinabox without any sense of existence)  

There are also a few foreign brothers on GitHub (some from our "competitor" [khanhduytran0](https://github.com/khanhduytran0)'s [Pojav](https://github.com/PojavLauncherTeam) team that People who got it)

### <span id="History">"History"</span>

The time goes back to 2014, when Chinese-American Zhang Zhuowei made what should be the first software to run the JAVA version of MC on an Android phone -`BoardWalk`.  
ZhuoWei’s `BoardWalk` has two versions, one is the [DVM](#Virtual-Machine) virtual machine version used by Uncle Min who used to make videos, and the other is the [JVM](#Virtual-Machine) virtual machine version The version of the machine (version number is 1.9). [(The difference between the two)](#Virtual-Machine)  
BoardWalk was not stable at the time and was not open source. The original author Zhang Zhuowei also disappeared from the Internet for several years. In order to get a better gaming experience, the post bar set off a wave of reverse magic to change the BoardWalk.
In 2019, BoardWalk is open sourced. JVM modifies its source code and compiles JVM by itself, making Boat. Since the JVM mobile phone has a 32-bit processor, he only compiled a 32-bit JVM. After that, longjunyu2 and JVM and several other developers began to develop MCinaBox together. Because the JVM mobile phone is 32-bit and the disk space of his computer is insufficient ~~The main reason is that he wants to fish~~, the 64-bit JVM was compiled by longjunyu2 with the help of JVM for a long time.  

### <span id="Virtual-Machine">DVM and JVM Virtual Machine</span>

 **JVM** The virtual machine is the JAVA virtual machine that we commonly use on computers. This virtual machine theoretically allows us to experience Minecraft Java Edition completely and normally (forge, Fabric, etc. can be used), but compiling a JVM for Android is a very troublesome thing.  

 **DVM** The virtual machine is a JAVA virtual machine made by Google specifically for the Android system. Almost all Android applications use it to run. It cannot run .jar directly, it can run `.dex` processed by dx. In addition to dx processing, Minecraft .jar files also need to be processed by `jar2jar` to be able to run. In addition, because of the way it loads class files, if you want to use DVM to run Minecraft with Mod, not only the .jar of Minecraft must be modified, but the .jar of Mod must also be modified. These modification steps are not completed by automatic scripts. The early BoardWalk (not version 1.9) used the DVM virtual machine. The reason why it is very slow to install a version of Minecraft is not only because the download speed is slow, but also because the amount of calculation to execute dx is very large, which needs to be executed on the phone. a long time.  

> Although Minecraft is continuously updated, dx stopped updating early. According to my own test, Minecraft versions 1.9 and above cannot be successfully processed by dx. This is one of the reasons why BoardWalk cannot run the updated version of Minecraft.  

### <span id="Game-Performance">Game Performance and Error Reporting</span>

#### Graphics library

The first thing to mention is Minecraft’s graphics library `OpenGL`, and the graphics library supported by Android phones using Arm processors is its close relative `OpenGL ES`  

Despite being close relatives, the two are completely incompatible with each other. You have to convert `OpenGL` to `OpenGL ES`, which requires [gl4es](https://github.com/ptitSeb/gl4es).  

But `gl4es` is not perfect. First, it only supports the converted version of OpenGL 2.0 and 1.5, which greatly limits the Frame Rates or FPS of Minecraft. Second, it has many bugs, such as Forge's anvil knocking when starting the game. The animation will cause the game to crash (so you have to disable the startup animation and black screen to start the game), adjusting the minmap will render the game screen ~~ strange ♂ strange ♂ strange ♂ strange ♂ ~~... Some people say that black screens and the like are basically worshipped It is bestowed~~.

#### JAVA virtual machine

Whether it is `DVM` or `JVM` virtual machine, the higher the version, the better. (Of course the version of the `DVM` virtual machine depends on your Android system version)  

> In terms of horizontal comparison, I personally think that the performance of DVM is better, because I used khanhduytran0's pojavlauncher to play Minecraft with more than 100 frames on the Snapdragon 855. But now it is said that the team of khanhduytran0 has discussed that the performance of the JVM virtual machine is better, and they will use openjdk9mobile instead.  

#### Submit an error  

Of course, we hope that everyone submits the error in the issue of github and attaches the log file. But the reality is that most people don't use `github` and call out in the `qq` group.  

### <span id="Situation">Current situation and future directions</span>  

- We are thinking of a way to allow `MCinabox` to automatically install `Fabric`. Of course, we must also adapt some Mods as much as possible (but browser Mod is not possible, this thing is completely impossible to run under the Android system).
- Our ~~competitor~~ `khanhduytran0` and his team are now focusing on [PojavLauncher_iOS](https://github.com/PojavLauncherTeam/PojavLauncher_iOS). Yes, you heard that right, you can play the Java version of Minecraft on iOS!



