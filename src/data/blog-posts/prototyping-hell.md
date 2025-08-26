---
title: Prototype Hell  
slug: prototype-hell
publishDate: 27 June 2025
description: How every test became its own Unity project
---

# When Every Test Becomes a Project

remember that gun demo from few weeks back? supposed to be quick test. get something working, see if could hit objects in scanned room, move on.

didn't work that way.

## the feature creep spiral

after showing wouter the gun prototype had list of "quick things to try":
- grab objects instead of just shooting?
- spawn basic shapes and interact?
- simple menu system?
- how hard is hand tracking?

each seemed like small addition. just modify existing project right?

wrong.

## seven projects later

here's what actually happened. every time wanted to test something new i'd start changing gun project. then break something. spend hour fixing instead of testing new feature. so made project copy "just for this test."

three weeks later have:
- GunDemo_Original
- GunDemo_WithGrabbing
- HandTracking_Test  
- MenuSystem_Prototype
- ShapeSpawner_v1
- ShapeSpawner_v2 (v1 was "too messy")
- PassthroughUI_Experiment

each in different Unity version because kept reading about newer packages that might solve problems. some 2022.3, others 2023.2, one unfortunate Unity 6 experiment i try not to think about.

## integration nightmare

now need to build actual thing. all these prototypes work fine alone but combining them is disaster.

hand tracking from HandTracking_Test uses different input handling than grabbing system in GunDemo_WithGrabbing. menu from MenuSystem_Prototype expects Unity XR components but best interaction code is in project using Meta's SDK.

trying to merge different package versions across Unity versions is its own special hell.

## what i should have done

looking back should have:
- stuck with one Unity version from start
- made one solid project for all experiments  
- set up proper scene organization instead of treating each test separately
- documented which approaches worked instead of leaving them scattered

## messy reality

but honestly this is probably just how prototyping goes. when trying to figure out if something works last thing you want is spending time on proper project structure. want to test idea, not build cathedral.

real problem was not planning for point where experiments need to come together. was thinking each test was final answer, not stepping stone.

## moving forward

doing unglamorous work of rebuilding "real" project by cherry-picking best parts from prototypes. tedious but at least know what works and what doesn't.

next time maybe stick to "one kitchen sink project" plan. or maybe end up with another folder full of experiments.

honestly probably the latter. but at least now expect it.