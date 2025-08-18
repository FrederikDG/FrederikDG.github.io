---
title: When OVR Takes Over Your Project - Layers, Tags, and Other Surprises
slug: ovr-layers-chaos
publishDate: 03 August 2025
description: How Meta's SDK quietly reorganizes your entire Unity project without asking
---

# When OVR Takes Over Your Project - Layers, Tags, and Other Surprises

So here's something nobody warns you about when you import Meta's XR SDK: it doesn't just add some prefabs and scripts. It basically moves into your Unity project and starts rearranging the furniture.

## The Great Layer Shuffle

I had a perfectly organized layer setup. UI on layer 5, interactive objects on layer 8, environment on layer 10. Simple, clean, worked great.

Then I imported the Meta XR All-in-One SDK.

Suddenly I have new layers I didn't create:
- OVROverlay
- OVRUnderlay  
- VirtualObjects
- PhysicalObjects
- Whatever else Meta decided I needed

And my existing objects? Some of them got moved to different layers automatically. My UI elements that were on layer 5 are now on some Meta-specific UI layer. My interactive objects are scattered across three different layers based on whether Meta thinks they're "physical" or "virtual."

## Tag Invasion

Same thing happened with tags. I had maybe five custom tags for different object types. After the SDK import, my tag list looks like a Meta developer's todo list:

- OVRTouchable
- OVRGrabbable  
- OVRInteractable
- OVRSceneAnchor
- OVRPassthroughObject

And the kicker? Some of my existing objects got retagged automatically. My grabbable cubes that had the tag "Interactive" now have "OVRGrabbable" instead.

## Camera Setup Chaos

This one really got me. I had a simple camera setup for testing - just the main camera with some basic settings. After importing Meta's SDK and adding their camera rig, my original camera was still there but completely ignored.

It took me way too long to figure out that the OVRCameraRig creates its own camera hierarchy and expects to be the only camera system in the scene. My original camera wasn't broken, it just became irrelevant.

## Passthrough vs Everything Else

The most confusing part is how passthrough interacts with the rest of your scene. It's not just a background - it's this whole separate rendering layer that has opinions about what should render in front of it and what shouldn't.

I had UI elements that worked fine in normal VR suddenly becoming invisible because they were rendering "behind" the passthrough layer. Turns out you need to use OVROverlayCanvas instead of regular Canvas components if you want UI to show up properly in passthrough mode.

But nobody tells you this upfront. You just start testing and wonder why half your interface disappeared.

## The Physics Surprise

Here's a fun one: Meta's SDK has strong opinions about physics layers too. Some interactions only work if objects are on specific physics layers. My basic rigidbody objects that worked fine for collision detection suddenly couldn't be grabbed by Meta's interaction system because they weren't on the right layer.

The documentation mentions this, but it's buried in some sub-section about advanced configuration. Meanwhile, you're just trying to make a cube grabbable.

## Scene Hierarchy Madness

The OVRCameraRig doesn't just add a camera - it adds a whole hierarchy of anchors, trackers, and child objects. If you're not careful about where you parent your objects, you end up with stuff attached to the wrong transform and moving in weird ways.

I had objects that were supposed to be world-positioned suddenly following my head movement because I accidentally parented them to the CenterEyeAnchor instead of the scene root.

## What I Learned

The big lesson here is that Meta's SDK isn't just an addition to your project - it's a takeover. It wants to be the primary VR system, and it will reorganize things to make that happen.

This isn't necessarily bad. Meta's organization probably makes more sense than my random layer assignments. But it's surprising when you're not expecting it.

Next time I start a VR project, I'm importing the Meta SDK first, then building around their structure instead of trying to retrofit it into my existing setup.

Or maybe I'll just accept that every VR project will have that moment where I wonder why nothing works anymore, then remember I need to check which layer everything ended up on.