---
title: Meta XR SDK vs Unity XR - Pick Your Poison
slug: meta-sdk-unity-fight
publishDate: 23 June 2025
description: Why using both Meta's SDK and Unity's XR toolkit feels like wrestling two different APIs at once
---

# Meta XR SDK vs Unity XR - Pick Your Poison

So here's a fun one. You'd think that since Meta makes the Quest and Unity supports VR, putting them together would be smooth sailing. Nope.

I'm about two weeks into this project and I keep hitting the same wall: do I go all-in on Meta's XR SDK, or stick with Unity's XR Interaction Toolkit? Because trying to use both is like having two different people give you directions to the same place.

## The Meta Way

Meta's All-in-One SDK is actually pretty solid. Their building blocks for hand tracking, passthrough, and interaction are polished. When you grab their prefabs for controllers or hand interaction, they just work. The OVRCameraRig handles head tracking without any fuss, and their interaction system feels natural in VR.

But here's the thing - it's all Meta. Want to add something that isn't in their toolkit? Good luck making it play nice with their interaction system. Their components have very specific ways they want to be used, and if you step outside that box, you're on your own.

## The Unity Way

Unity's XR Interaction Toolkit, on the other hand, is more flexible. You can mix and match components, extend their base classes, and generally hack things together the way you want. It's built to work across different VR platforms, so the code you write isn't locked to Quest.

The downside? It feels more generic. Getting hand tracking to work smoothly takes more setup. The default interactions don't have that "Meta polish" feel. And honestly, some things that work out of the box with Meta's SDK require way more configuration in Unity's system.

## The Real Problem

The nightmare comes when you try to use both. I started with Meta's SDK because it was easier to get running. Then I needed custom interaction components that Unity's toolkit handles better. So now I have OVRCameraRig for tracking but XRRayInteractor for UI interactions. And they don't always agree on what "selected" means or how hand poses should work.

I spent an entire afternoon debugging why my ray interactions stopped working, only to find out that Meta's hand tracking was overriding Unity's interaction states. Fun times.

## What I'm Doing About It

For now, I'm mostly sticking with Meta's SDK for the core VR stuff - tracking, passthrough, hand detection. But I'm using Unity's XR components for custom interactions that need more flexibility. It's not clean, but it works.

The real lesson here is probably to pick one and stick with it from the start. But when you're prototyping and trying different approaches, you end up with this frankenstein setup whether you want it or not.

Maybe by the time I'm done with this project, Meta and Unity will have figured out how to play together better. Or maybe I'll just have gotten better at working around their differences.

Either way, it's definitely not the "it just works" experience I was hoping for when I started.