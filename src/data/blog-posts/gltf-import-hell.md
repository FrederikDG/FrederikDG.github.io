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

suddenly getting cross-eyed double vision nightmare. two identical meshes in different positions moving at different rates. like someone took my 3D model and gave it an evil twin that follows slightly behind doing its own thing.

spent entire day thinking it was my mesh generation screwing up. checked ComfyUI output, verified files, regenerated meshes dozen times. all looked fine in editor. only broke in builds.

## the paid importer rabbit hole

googled "unity gltf importer" and found bunch of asset store options. most were expensive ($50+) and half looked sketchy. some had chinese descriptions with google translate english that made no sense.

tried few paid ones during free trial periods. same issues - worked in editor, broke in builds. or worked in builds but mangled materials. or imported everything sideways for no reason.

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

## trimesh savior

after days of frustration found some free "Trimesh Importer" package on github. looked abandoned and documentation was minimal. probably virus i thought but desperate times.

downloaded sketchy zip file, held breath, imported to project.

it worked perfectly.

single mesh, correct positioning, proper materials, identical behavior between editor and builds. finally could load my AI-generated meshes without VR users getting motion sick from double vision.

## lessons learned

Unity's official GLTF support is still garbage. GLTFast sounds good in theory but has fundamental issues with build consistency.

paid importers aren't necessarily better. expensive doesn't mean functional.

sometimes random free package from unknown developer works better than official Unity solutions. open source community often fixes problems Unity ignores.

## current state

using Trimesh Importer for all GLB imports now. haven't had single issue since switching. models load correctly, position properly, work same in editor and builds.

still don't know why other importers failed so spectacularly. GLTF is supposed to be standardized format but apparently every importer interprets it differently.

at least now can actually show people VR project without them getting nauseous from duplicate geometry floating around.

sometimes best solution is random package you find at 2am when you're desperate enough to try anything.