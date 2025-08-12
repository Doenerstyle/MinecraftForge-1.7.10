# Minecraft Forge 1.7.10 (slightly updated)

Hello there, fellow modders and mod enjoyers!

This repository is a fork of [Minecraft Forge](https://github.com/MinecraftForge/MinecraftForge) for Minecraft 1.7.10 containing various improvements and optimizations.
It is compatible with almost all mods out there (read more about **very minor** incompatibilities at the end of the README) and is designed to improve the **user experience** and performance while keeping changes as little as possible. It is interchangeable with Forge v10.13.4.1614 for Minecraft 1.7.10 servers as well as clients.

## Improvements made in this fork

Some of the most **notable improvements** of this fork include:
* A reduced startup time

## Goal of this fork
Originally, I intended to create a fork that removes the useless/broken `Minecraft Realms` and `Mod Options...` buttons to save GUI space and improve the user experience, especially for new players.
However, I quickly came to realize that there are probably some more things that could be improved/adjusted without breaking mod compatibility, too.

Therefore, the goal is to create the **best widely-compatible 1.7.10 Forge version possible** that suits any mods/modpacks without creating any downsides/breaking anything that's even close to noteworthy, all of this while clearly documenting every change made.

Note, however, that I do **not** intend to actively maintain/update this fork in general. I might make changes to it whenever I feel like it, but as Forge 1.7.10 is provenly stable, there should be no need to regularly update this fork.
**If you know something that could be improved (and is suitable for every/very most use cases), don't hesitate to open an issue (or even PR) and let me know, though!**

## How well-tested is this fork/Can I safely use this?
Personally, I use this fork for every 1.7.10 modpack I create/play, but I cannot _guarantee_ that it won't break things and thus don't recommend to use this in any productive/important environment without properly testing compatibility first.
Of course, **you're free to open issues if you encounter bugs or incompatibilities/crashes and PRs are always welcome, including new/updated localization files**!

My **largest concern** about this fork is the fact that the building process for Forge 1.7.10 is somewhat broken (it errors as "BUILD FAILED"). While it does generate a usable jar file, that jar file lacks some contents which are present in the latest official Forge 1.7.10 build. I have yet to verify which files are missing and whether that's a problem.

## Using/updating this fork
These instructions assume you're using a Minecraft launcher that uses a similar file structure to Mojang's. For some launchers, the location of the forge jar file might differ.
- In order to benefit from this fork's improvements, you need to have a working version of Forge v10.13.4.1614 already installed.
- Visit the [releases page](https://github.com/Doenerstyle/MinecraftForge-1.7.10/releases) of this fork and download the latest release's `forge-1.7.10...universal.jar`.
- In the root directory of the according Minecraft installation/modpack, enter the `libraries` folder and proceed entering `net/minecraftforge/forge-10.13.4.1614/`. Inside that directory, replace the `forge-10.13.4.1614-1.7.10-universal.jar` file with the one downloaded from this fork. Whether or not you also adjust the version number in the `forge-10.13.x.xxxx` directory name is up to you. (Note: some Launchers **require** the file's version number to be 1614, in that case, you need to rename the downloaded file name to the original Forge's file name.)
- Upon launch, the game should now display the correct Forge version in the main menu.

## Building this fork
Setting up this fork for development works exactly the same way as with the official Forge 1.7.10.

Clone the repository to somewhere local, run `gradlew setupForge eclipse` inside of it, then launch Eclipse and select `./eclipse` as workspace. Make sure you **clone** the repository, rather than just downloading it as a zip file.

Building this fork is also identical to the official Forge 1.7.10:

run **gradlew genPatches** (only required if working with/creating patches), then **gradlew build**. It will say "BUILD FAILED". However, upon entering ./build/distributions, you will find a working `forge-1.7.10...universal.jar` which you can use just like any other forge.jar.

## Incompatibilities
While this fork generally keeps up compatibility as much as possible, there are some niche cases where it might cause problems:
* BaseMods, which are highly uncommon nowadays, are ignored/not loaded to allow for a notably quicker startup.
