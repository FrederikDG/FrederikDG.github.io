---
title: User Testing - When Reality Punches You in the Face
slug: user-testing-humbling
publishDate: 02 July 2025
description: Watching people use your VR project is both enlightening and terrifying
---

# User Testing - When Reality Punches You in the Face

I thought my VR project was pretty intuitive. Point at things, grab stuff, take pictures, watch AI generate 3D models. Simple, right?

Then I watched my first user try to use it.

## The Setup

I brought the project to a few friends to get some feedback. Nothing formal, just "hey, want to try this VR thing I'm working on?" I figured I'd get some nice validation and maybe a few minor suggestions.

I was not prepared for what actually happened.

## User #1: The Controller Fumbler

First person puts on the headset and immediately starts looking around - good sign. They see the floating menu, point at it with the controller ray... and nothing happens.

Turns out I never explained that you need to pull the trigger to click. In my head, "point and click" was obvious. To them, pointing was the entire interaction.

After I explained the trigger, they started clicking everything rapidly, spawning cubes and spheres everywhere. Apparently my spawn cooldown wasn't aggressive enough to prevent this. Within 30 seconds, the scene was chaos.

## User #2: The Hand Tracking Optimist

Second person immediately asks if they can use hand tracking instead of controllers. Sure, I say, it's supported, it's not

Ha-ha

## User #3: The Feature Hunter

Third person actually gets the basic interactions working pretty quickly. They spawn some objects, grab them, move them around. Great!

Then they start asking questions:
- "Can I change the colors?"
- "What if I want to delete objects?"
- "How do I save my objects?"
- "Can I share this with other people?"

All reasonable questions. All features I hadn't implemented yet because I was focused on the core AI integration.

## The AI Disappointment

When we finally got to the main feature - taking pictures and generating 3D models - that's when things got really humbling.

The first picture they took was of a coffee mug. Perfect test case, I thought. Simple object, clear shape, should work great.

The generated mesh looked like a melted candle. Recognizably mug-shaped, but barely. And it took 40 seconds to generate, during which they just stood there waiting.

"Is it supposed to look like that?" they asked.

No. No it is not.

## What Actually Worked

Not everything was a disaster. A few things people genuinely liked:

- The passthrough integration felt "natural" and "cool"
- Once they understood the spawning system, people enjoyed creating little scenes
- The floating menu following their gaze was intuitive
- When the AI generation actually worked, the "wow factor" was real
