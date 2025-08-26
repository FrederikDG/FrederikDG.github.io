---
title: VRAM Poverty
slug: vram-poverty
publishDate: 05 September 2025
description: Moving from 16GB VRAM to 6GB killed my entire workflow
---

# VRAM Poverty

had to move and leave behind my desktop with RTX 4080 and 16GB VRAM. now stuck with laptop's 3060 with 6GB and my entire workflow is fucked.

## the brutal downgrade

went from 16GB VRAM to 6GB overnight. doesn't sound like much but it's difference between working and not working. ComfyUI workflows that ran fine before now crash with out-of-memory errors. Unity play mode that was smooth is now slideshow.

can't run both at same time anymore. have to choose: either test VR project in Unity or generate meshes with ComfyUI. not both. workflow that was "take screenshot, generate mesh, import to Unity" is now "take screenshot, close Unity, open ComfyUI, generate mesh, close ComfyUI, open Unity, import mesh."

kills all momentum. by time you've switched between applications three times you've forgotten what you were testing.

## ComfyUI memory hell

ComfyUI is VRAM hungry beast. Trellis workflow alone uses 6-7GB just to load models. any halfway decent image-to-mesh generation needs multiple models loaded simultaneously.

tried every memory optimization:
- lowvram mode (cuts quality significantly)
- cpu offloading (makes everything 10x slower) 
- model splitting (breaks some workflows entirely)
- reducing batch sizes (fine for single images, useless for multi-view)

even with optimizations still hitting memory limits constantly. models that worked fine on 4080 either crash or produce garbage output on 3060.

## Unity suffering

Unity alone uses 2-3GB VRAM in VR play mode. add passthrough rendering, real-time lighting, and mesh importing and you're at 5-6GB easy. no room left for anything else.

frame rates tanked from solid 90fps to inconsistent 5-10fps. VR becomes nauseating when framerate drops. can't properly test interactions when everything stutters.

tried reducing quality settings but VR already demands certain minimums. lower texture quality too much and everything looks like minecraft. reduce lighting and passthrough integration breaks.

## workflow destruction

old workflow:
1. run Unity in play mode
2. take VR screenshot
3. ComfyUI processes in background
4. mesh appears in Unity within 30 seconds
5. test immediately

new workflow:
1. test something in Unity, make a build
2. close Unity (wait for it to actually close)
3. start up independant build  on quest
4. open ComfyUI, load workflow, process image made in build (wait 2-3 minutes)
5. repeat


what used to be 30-second iteration cycle is now 5-10 minutes with context switching hell.

## the laptop reality

laptop 3060 isn't just smaller VRAM - it's slower everything. memory bandwidth lower, cooling worse, power limits tighter. even when not hitting VRAM limits performance is significantly worse.

thermal throttling kicks in after 10 minutes of heavy use. ComfyUI processing starts fast then slows to crawl as GPU overheats. Unity becomes unresponsive during long operations.

battery life becomes consideration. desktop could run all day plugged in. laptop dies in 2 hours under heavy GPU load. have to plan work sessions around charging cycles.

## workaround attempts

tried running ComfyUI on CPU instead of GPU. works but takes 15+ minutes per mesh instead of 30 seconds. completely kills iterative development.

looked into cloud GPU services but latency makes real-time testing impossible. also gets expensive fast when you're processing dozens of test meshes.

attempted splitting workflow across multiple machines but file syncing and network delays create new problems.

## current reality

development pace cut by at least 75%. what used to be rapid iteration is now careful planning of each test. can't afford to waste GPU cycles on failed experiments.

focusing on optimization over features now. spending time making existing meshes work better instead of generating new ones. less creative exploration, more technical problem solving.

project timeline completely shot. features i planned to finish this month will probably not happen anymore.

## lesson learned

VRAM is everything for modern AI workflows. 6GB feels generous until you try running anything serious. 16GB is minimum for actual development work.

laptop development is exercise in compromise. acceptable for coding and basic 3D work. completely inadequate for AI-powered anything.

never take desktop development environment for granted. when it's gone you realize how much you relied on having actual hardware resources.

moving sucks but moving away from your development machine is special kind of hell.