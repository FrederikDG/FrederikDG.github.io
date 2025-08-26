---
title: Unity Setup
slug: unity-setup-quest3
publishDate: 08 june 2025
description: Setting up Unity for Meta Quest 3 development
---

# Getting Unity & Quest 3 to Talk

getting unity to work with quest 3 should be straightforward. it's not.

## version hell

unity just released unity 6 which changed VR development significantly. plus the oculus-to-meta transition means half the tutorials use packages that don't exist anymore.

decided to stick with unity 2022.3 LTS for stability. newer versions are too risky when you're trying to actually build something instead of just experimenting.

## XR plugin choice

had to pick between OpenXR and Oculus plugins. OpenXR is supposedly the future and works across platforms. seemed safer since it's what three.js uses too.

started with empty 3D project instead of VR template so i'd understand what's happening rather than accepting magic prefabs.

## meta's toolkit

meta released the XR interaction toolkit SDK with basic VR building blocks. after lots of tinkering finally got basic passthrough working. no content yet but camera rig moves when i move my head and i can see stuff in the headset.

## lessons learned

VR setup isn't plug-and-play. between version changes, company transitions, and evolving best practices you need to stay adaptable and research thoroughly before diving in.

but once it works it's pretty satisfying seeing your head movement translate to virtual camera movement.