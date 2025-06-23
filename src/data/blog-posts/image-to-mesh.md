---
title: Image to 3D mesh  
slug: image-to-mesh  
publishDate: 17 June 2025  
description: Options on how to convert image to a mesh  
---

So I got the ball rolling in the VR department, but the next inevitable hurdle came rolling in: turning a still image—snapped from inside the VR headset—into a proper 3D mesh. Something tangible. Something I could pull back into the virtual world, but now with actual depth.

Now, yes, there are **paid services** out there that offer image-to-mesh capabilities. Some of the ones that popped up during my research were:

- **Kaedim** – sleek UI, quick turnaround, great for stylized game assets.  
- **Luma AI** – photorealistic results, captures light and texture well.  
- **RealityCapture** – pro-level photogrammetry, supports huge datasets.

These platforms are great because they:
- Offload the heavy lifting to cloud-based compute.
- Handle photogrammetry pipelines with a single upload.
- Often come with texture baking and PBR export support.

But… I don’t always want to be at the mercy of a paywall or a queue, and more importantly, I wanted something that could run locally—on my own hardware. Which would make the game lean even more into **PCVR** territory, but hey, at least I get to tinker.

## HuggingFace to the rescue

While diving into HuggingFace, I stumbled on a few **open-source options** that can convert images (or multi-view captures) into meshes. Some gems worth mentioning:

- **Stable Video 3D** – by the Stability AI team, surprisingly good single-image reconstructions.  
- **Zero123++** – generates multi-view images from one still and feeds them into reconstruction tools.  
- **Volinga** – a newer experiment that reconstructs scenes via NeRF-style approaches.

What’s nice about these is:
- They’re **free** (as in buy me a beer-free).
- Fully local—great for privacy and fast iteration.
- Highly hackable and composable with other AI workflows.

## ComfyUI + Trellis = 🔁

Out of all of them, I ended up diving into **Trellis**, a relatively new effort that plugs into the world of NeRFs and mesh reconstructions. Even better: someone made a comfy set of **ComfyUI nodes** for it. That meant I could patch it into my existing AI pipeline without rewriting everything from scratch.

Granted, it wasn’t exactly plug-and-play. The original nodes were built for Linux systems, so on Windows I had to:
- Switch versions on other packages like torch and python.
- Patch some shell commands into `.bat` scripts.
- Tweak CUDA paths and recompile some bits.

But eventually, with enough duct tape and patience, I got my first mesh out of a single VR snapshot (copy and pasted, not through the set yet). And it looked… decent! Not triple-A ready, but more than usable for placeholder prototyping in the engine.
