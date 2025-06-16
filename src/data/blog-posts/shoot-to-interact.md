---
title: Shoot to Interact  
slug: shooting-interaction  
publishDate: 08 June 2025  
description: Building the first real VR interaction  
---

# Shoot to Interact

Alright, so after I got Unity and the Meta Quest 3 set up and talking to each other, the next logical step was making things... do stuff. I wanted interaction. Movement. Feedback. And honestly, nothing screams "I'm actually doing VR dev now" like spawning a gun and shooting something.

## The Gun Phase (obviously)

I kicked it off by trying to get some controller input working, nothing too wild yet. Just the basics. Hold the controller, have something show up in my virtual hand, feel like I’m holding something. So of course, I went with the most cliché (and most fun) first test: a gun.

Now, getting this to work is not just drag and drop. It’s a *lot* of headset on, headset off, tweak this script, move that prefab, reposition something that’s floating in the wrong dimension. I was wearing the headset more like a backwards cap than properly on my face. Very flattering.

I quickly modeled a super simple low-poly pistol, textured it (and by "textured" I mean slapped some color on it), and turned it into a Unity prefab. Dropped it into the scene, lined it up with my right controller, and adjusted the position/rotation/scale until it looked halfway believable. Nothing fancy, but good enough to go pew pew.

## Pew Pew Logic

Next up: make it actually shoot. That meant diving into some Unity scripting and wiring up a simple raycast. Pull the trigger, fire a ray from the gun barrel forward. If it hits something, it returns a hit. I also added a basic gunshot sound, which honestly made it feel *way* more real even without any visuals.

Later on, I got fancy and added a visible bullet object. Not a physics-driven one yet, just a 3D shape moving forward in space. But it already made the interaction feel more tactile. It’s crazy how much difference a little feedback makes.

## Using My Apartment as a Target

So the next part got a bit more meta. I wanted to make the environment relevant, not just throw bullets into a grey void. So I looked into using a scan of my apartment as a backdrop. I already had one from using the headset’s room setup tools (you know, the thing that helps you not walk into a wall), and figured: why not use it?

Turns out, Meta’s passthrough features actually let you bring that scanned mesh into Unity. It’s rough, but it gives you the structure of your real-world space. Using one of their SDK building blocks, I was able to load that scan in as a static mesh and layer it into my passthrough.

Now, when I fired a bullet, it wouldn’t just vanish, it would hit the walls or floor of my scanned apartment. It didn’t break or react yet (I wasn’t at the physics stage), but just seeing bullets land in familiar spots was kinda surreal.

## Sharing the Base with Wouter

I brought this whole prototype to Wouter during a consult, mostly to show the concept was working. The idea was simple but key: get a basic interaction loop working inside a real scanned space. Nothing too polished yet, but you could see the gun, hear it shoot, and watch bullets fly into your environment and stick.

That moment was important, it was the first real "ok, this is a thing now" checkpoint. I had something working, and from here I could start building toward deeper interactions and more realistic environments.

Still no physics, baby steps.
