---
title: When OVR Takes Over Your Project
slug: ovr-layers-chaos
publishDate: 03 August 2025
description: How Meta's SDK quietly reorganizes your Unity project
---

# Meta SDK Hostile Takeover

nobody warns you about this when importing Meta's XR SDK: it doesn't just add prefabs and scripts. basically moves into your Unity project and starts rearranging furniture.

## the layer shuffle

had perfectly organized layer setup. UI on layer 5, interactive objects on layer 8, environment on layer 10. simple, clean, worked.

then imported Meta XR SDK.

suddenly have new layers i didn't create:
- OVROverlay
- OVRUnderlay  
- VirtualObjects
- PhysicalObjects

my existing objects? some moved to different layers automatically. UI elements that were layer 5 now on some Meta-specific UI layer. interactive objects scattered across three layers based on whether Meta thinks they're "physical" or "virtual."

## tag invasion

same thing with tags. had maybe five custom tags for object types. after SDK import tag list looks like Meta developer's todo:

- OVRTouchable
- OVRGrabbable  
- OVRInteractable
- OVRSceneAnchor
- OVRPassthroughObject

some existing objects got retagged automatically. grabbable cubes with "Interactive" tag now have "OVRGrabbable" instead.

## camera hierarchy madness

had simple camera setup for testing - main camera with basic settings. after importing SDK and adding camera rig my original camera was still there but completely ignored.

took too long to figure out OVRCameraRig creates its own camera hierarchy and expects to be only camera system in scene. original camera wasn't broken, just became irrelevant.

## passthrough rendering confusion

most confusing part is how passthrough interacts with scene rendering. not just background - separate layer with opinions about what renders in front and what doesn't.

had UI elements working fine in normal VR suddenly becoming invisible because rendering "behind" passthrough layer. turns out need OVROverlayCanvas instead of regular Canvas for UI to show in passthrough mode.

nobody mentions this upfront. you just test and wonder why half interface disappeared.

## physics layer opinions

Meta's SDK has strong opinions about physics layers too. some interactions only work if objects on specific layers. basic rigidbody objects that worked for collision suddenly couldn't be grabbed because weren't on right layer.

documentation mentions this but buried in sub-section about advanced configuration. meanwhile just trying to make cube grabbable.

## what i learned

Meta's SDK isn't addition to your project - it's takeover. wants to be primary VR system and will reorganize things to make that happen.

not necessarily bad. Meta's organization probably makes more sense than my random assignments. but surprising when not expecting it.

next VR project importing Meta SDK first then building around their structure instead of retrofitting into existing setup.

or maybe just accept every VR project has that moment where you wonder why nothing works then remember to check which layer everything ended up on.