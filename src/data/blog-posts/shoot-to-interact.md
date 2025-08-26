---
title: Shoot to Interact  
slug: shooting-interaction  
publishDate: 11 June 2025  
description: Building the first real VR interaction  
---

# First Real VR Interaction

after unity and quest 3 were talking the next step was making stuff actually do things. wanted interaction, movement, feedback. nothing says "doing VR dev" like making a gun and shooting stuff.

## building the gun

started with basic controller input. hold controller, see something in virtual hand, feel like you're holding an object. went with the most cliche first test: a gun.

this isn't drag and drop though. lots of headset on, headset off, tweak script, move prefab, fix something floating in wrong dimension. wore the headset backwards more than properly.

modeled simple low-poly pistol, textured it (slapped color on it), turned into unity prefab. dropped in scene, spent forever adjusting position/rotation/scale until it looked believable. nothing fancy but good enough for pew pew.

## shooting logic

next was making it actually shoot. unity scripting time - wired up simple raycast. pull trigger, fire ray from gun barrel forward. if it hits something, register hit. added basic gunshot sound which made it feel way more real even without visuals.

later added visible bullet object. not physics-driven, just 3D shape moving forward. made interaction feel more tactile. crazy how much difference little feedback makes.

## using my apartment as target range

wanted environment to be relevant instead of shooting into grey void. looked into using scan of my apartment as backdrop. already had one from headset's room setup tools.

turns out meta's passthrough features let you bring scanned mesh into unity. rough but gives structure of real space. using SDK building blocks could load scan as stat