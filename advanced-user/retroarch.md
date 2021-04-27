---
description: An emulator launching program which RecalBox makes use of
---

# Retroarch

## What's this ?

Retroarch is a libretro front-end, which means it can run libretro cores, but also unifies how they work with the system.

Cores are programs optimized to work with libretro front-ends, in that case, they're emulators for the most part.

## Features

Retroarch, in its core, is a program launching other small programs, not only that, but it also tells them how inputs work \(so that you only need to configure your game pad once, and not do it for every core\), the new features are generally available across multiple cores and can be accessed equally across them. Simply put, it sets a standard that cores will then follow.

The retroarch interface let's you tweak a lot of settings, however in most cases, the defaults should be fine, however, Core options for exemple can let you change the region of the system you are currently playing if need be. As usual, those settings should not be used without thinking.

It also includes the basic features an emulator gives \(such as save states, screenshots, disc-swapping for CD based systems, ...\), as well as some more advanced settings \(shaders, rewind and fast-forward, netplay, ...\) some of them are accessible using the [hotkey combinations](../basic-manual/getting-started/#b-special-commands).

## Required

While Retroarch and recalbox try to ease the pain for the end user as much as possible, some cores do have requirements to work properly, such as BIOSes or the right file format for a game, the webmanager can tell you which BIOSes you have or need for the different emulated systems, and the readme.txt files inside each system will tell you which formats are supported for each system.

We also strongly advise you to understand what you are doing for some systems \(like the arcade\), as putting random files in and expecting it to work can simply not work at all depending on the situation.

