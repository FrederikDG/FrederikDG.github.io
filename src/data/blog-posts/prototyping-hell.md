---
title: Prototype Hell - When Every Test Becomes Its Own Project
slug: prototype-hell
publishDate: 27 June 2025
description: How I ended up with seven different Unity projects and learned the hard way about feature creep
---

# Prototype Hell - When Every Test Becomes Its Own Project

Remember that gun demo I made a few weeks back? Well, that was supposed to be a quick test. Just get something working, see if I could hit objects in my scanned room, then move on to the real stuff.

Except... it didn't work that way.

## The Spiral Begins

After showing Wouter the gun prototype, I had this list of "quick things to try":
- What if I could grab objects instead of just shooting them?
- Could I spawn basic shapes and interact with them?
- What about a simple menu system?
- How hard would hand tracking be to add?

Each one seemed like a small addition. Just modify the existing project, right? Wrong.

## Seven Projects and Counting

Here's what actually happened. Every time I wanted to test something new, I'd start changing the gun project. Then I'd break something. Then I'd spend an hour trying to fix it instead of testing the new feature. So I'd make a copy of the project. "Just for this test."

Fast forward three weeks and I have:
- GunDemo_Original
- GunDemo_WithGrabbing  
- HandTracking_Test
- MenuSystem_Prototype
- ShapeSpawner_v1
- ShapeSpawner_v2 (because v1 was "too messy")
- PassthroughUI_Experiment

Each one is in a different Unity version because I kept reading about newer packages that might solve my problems. Some are on 2022.3, others on 2023.2, one unfortunate experiment in Unity 6 that I try not to think about.

## The Integration Nightmare

Now I'm at the point where I need to actually build the real thing. And guess what? All these prototypes work fine in isolation, but trying to combine them is a disaster.

The hand tracking from HandTracking_Test uses different input handling than the grabbing system in GunDemo_WithGrabbing. The menu from MenuSystem_Prototype expects Unity XR components, but my best interaction code is in a project that uses Meta's SDK. And don't get me started on trying to merge different versions of the same package across Unity versions.

## What I Should Have Done

Looking back, I should have:
- Stuck with one Unity version from the start
- Made one solid "kitchen sink" project for all experiments
- Set up proper scene organization instead of treating each test as a separate project
- Actually documented which approaches worked best instead of just leaving them in random project folders

## The Messy Reality

But honestly? This is probably just how prototyping goes. When you're trying to figure out if something will work, the last thing you want to do is spend time setting up proper project structure. You want to test the idea, not build a cathedral.

The real problem is that I didn't plan for the point where all these experiments would need to come together. I was thinking like each test was the final answer, not a stepping stone.

## Moving Forward

Right now I'm doing the unglamorous work of rebuilding the "real" project by cherry-picking the best parts from all these prototypes. It's tedious, but at least I know what works and what doesn't.

And next time? Maybe I'll actually stick to that "one kitchen sink project" plan. Or maybe I'll end up with another folder full of experimental projects. 

Honestly, probably the latter. But at least now I know to expect it.