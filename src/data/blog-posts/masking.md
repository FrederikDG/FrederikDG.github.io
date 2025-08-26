---
title: Object Masking for Better Results  
slug: masking  
publishDate: 20 June 2025  
description: Using object masking to isolate subjects for cleaner 3D mesh generation  
---

# Isolating the Subject

had basic workflow running but wanted better results. when field of vision wasn't clean it would pick wrong subject or mash multiple things into weird hybrids. sometimes straight ignored what i actually cared about.

used ComfyUI during internship at This January in Washington and made workflow that masked out objects of interest. combining approaches meant generating:
- image of scene
- alpha matte showing desired subject  
- 3D mesh from just that object

## the input problem

before i always used text prompts to guide masking - "car", "tree", "robot". works fine with screen and keyboard but inside VR headset gets tricky.

still brainstorming solutions. voice commands maybe? eye tracking? not sure yet but getting closer to figuring it out.