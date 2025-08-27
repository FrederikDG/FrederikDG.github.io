---
title: GLTF Import Hell
slug: gltf-import-nightmare
publishDate: 14 August 2025
description: Spent days fighting Unity's GLTF importers just to load 3D models without double vision
---

# GLTF Import Hell

needed to import GLB files from my ComfyUI mesh generation into Unity. should be simple right? industry standard format, Unity supports it, what could go wrong?

everything. everything could go wrong.

## GLTFast disaster

started with GLTFast since it's Unity's official GLTF importer. worked perfectly in editor. models loaded correctly, materials looked good, everything positioned right.

then made a build.

suddenly getting cross-eyed double vision nightmare. two identical meshes in different positions with the purple mesh of doom moving at different rates. like someone took my 3D model and gave it an evil twin that follows slightly behind doing its own thing.

spent entire day thinking it was somewhere along the way from comfyUI to Unity that it was screwing up. checked ComfyUI output, verified files, regenerated meshes dozen times. all looked fine in editor. only broke in builds.

## the paid importer rabbit hole

googled "unity gltf importer" and found bunch of asset store options. most were expensive ($50+) and half looked sketchy. some had chinese descriptions with google translate english that made no sense.

but I kept encountering the same issues - worked in editor, broke in builds. or worked in builds but mangled materials. or imported everything sideways for no reason.

one importer claimed to be "industry leading GLTF solution" and couldn't even load basic GLB without throwing null reference exceptions.

## debugging nightmare

the double mesh issue was impossible to debug. Unity's profiler showed nothing wrong. scene hierarchy looked normal - single mesh renderer, single transform. but somehow rendering two copies at different world positions.

tried everything:

- different Unity versions
- different build settings
- different GLB files
- different import settings
- clearing cache and library
- ritual sacrifice to unity gods

nothing worked consistently. would fix it in one build then break again in next.


![Purple mesh of doom](WhatsApp%20Image%202025-08-26%20at%2016.48.15_48dbf17e.jpg)


## Trilib 2 savior

after days of frustration, found the free [Trilib 2 Importer](https://assetstore.unity.com/packages/tools/modeling/trilib-2-model-loading-package-157548?srsltid=AfmBOorkkeoJ8pYbhKOGBSNNMTCq7FL1gjmB8y9Sxq6HjIFxWAw4Nw-g) package (normally $45) on a shady site. probably a virus, I thought, but desperate times.

downloaded sketchy zip file, held breath, imported to project.

it worked perfectly after switching to URP material manager and adding some of its shaders to alwas build with the project.

single mesh, correct positioning, proper materials, identical behavior between editor and builds. finally could load my AI-generated meshes without VR users getting motion sick from double vision.

![Trilib 2 Model Loading Package](https://unityassetcollection.com/wp-content/uploads/2020/10/TriLib-2-Model-Loading-Package.jpg)
\* 
## lessons learned

Unity's official GLTF support is still garbage. GLTFast sounds good in theory but has fundamental issues with build consistency.

paid importers aren't necessarily better. expensive doesn't mean functional.

sometimes random free package from unknown developer works better than official Unity solutions. open source community often fixes problems Unity ignores.

## current state

using Trilib 2 Importer for all GLB imports now. haven't had single issue since switching. models load correctly, position properly, work same in editor and builds.

still don't know why other importers failed so spectacularly. GLTF is supposed to be standardized format but apparently every importer interprets it differently.

at least now can actually show people VR project without them getting nauseous from duplicate geometry floating around.

sometimes best solution is random package you find at 2am when you're desperate enough to try anything.
