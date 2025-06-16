---
title: The Goal  
slug: goal  
publishDate: 04 june 2025  
description: The subject of my passion project  
---

# The Goal: AI-Powered Immersion in VR

Back in December 2024, I kicked off a passion project that’s been sitting in my head for way too long. I wanted to explore how artificial intelligence could level up virtual reality. Not just in a flashy tech-demo way, but in a way that actually feels meaningful and interactive. Something that feels alive while you're in it.

The question I started with was pretty simple:

> **How can AI make VR more immersive, more interactive, and maybe even help create learning experiences that feel personal?**

That's what I wanted to figure out.

## Why I'm Doing This

VR is cool. It’s gotten way better over the past few years. Headsets look less like scuba gear, graphics are sharp, and the worlds you can step into are massive. But the way you actually interact inside those worlds? Still kinda stiff. Mostly pre-built, mostly linear, and definitely not adaptive.

What I’m after is something that moves with you. A VR experience that watches how you behave and shifts itself around that. Something that doesn’t just play out like a movie but changes depending on who you are and how you move through it. Imagine a world that reacts to your curiosity instead of just your controller input. That’s the vibe I’m going for.

## The Concept That Clicked

After some messy whiteboards, late-night notes, and a good chat with a few people who know their stuff, the idea started forming. The core concept is a **passthrough-powered VR setup** that lets users bring real-world objects into the virtual space. Literally grab something from your desk, have the headset capture it, and then boom — you're interacting with its digital version in VR.

### Here’s the plan:

1. You pick up a real object, the passthrough camera sees it.  
2. AI kicks in and rebuilds it as a 3D model.  
3. That model gets dropped into a virtual environment where you can mess around with it.

Basically, the real world and virtual world start blending together in real time. And AI is what ties it all together.

## Under the Hood

To make this work, I’m looking at two main tech paths.

### First: Image-Based Object Capture  
This one's all about using the passthrough cameras to take images from different angles. Then those shots get fed into something like a NeRF model that reconstructs a 3D shape. Think of it like photogrammetry, but powered by machine learning.

### Second: Sensor Data (if available)  
If the headset’s got decent infrared or LiDAR support, I can mix that in to get better depth info. That data goes into a model trained to combine RGB images with depth maps, so the 3D output is cleaner and more accurate.

Depending on what headset I’m using and what it supports, I’ll switch between these two or maybe combine them.

## The Practical Bits

There are a bunch of things I had to consider before even writing a single line of code.

- The hardware matters. Meta Quest Pro and Vision Pro both have solid passthrough support and sensors, so they’re perfect for testing this.
- Latency is the big killer. If capturing and building the object takes too long, it ruins the feeling. So it needs to be real-time or close to it.
- The user experience has to feel natural. Like you’re scanning and summoning stuff, not doing a mini science project.
- AI needs to run lightweight. I don’t want to rely on cloud processing if I don’t have to. The faster it runs locally, the smoother the experience.

## Where It’s Headed

I’m still in the early stages of building all this out, but the foundation is there. A system that blends real and virtual objects in a smart way. One that watches and learns from how you interact. And maybe, just maybe, one that can help people actually learn better while they’re in VR.

More soon once I start prototyping.
