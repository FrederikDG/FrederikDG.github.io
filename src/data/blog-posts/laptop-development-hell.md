---
title: Laptop Development Hell
slug: laptop-development-hell
publishDate: 14 August 2025
description: How moving to different PC turned working VR project into broken mess
---

# Machine-Specific Project Hell

had consult with wouter scheduled and figured work on project from laptop instead of lugging desktop setup to school. should be simple right? same Unity version, same project files, same headset.

everything went wrong.

## package disaster

first problem: project wouldn't even open. Unity throwing errors about missing packages even though committed everything to version control. turns out some Meta XR SDK components don't play nice when moved between machines.

packages were "there" but also "not there." showed up in Package Manager with error icons. half scripts missing references. OVRCameraRig prefab completely broken, showing as empty GameObjects with missing components.

tried reimporting packages, clearing package cache, deleting and re-adding Meta XR SDK. nothing worked consistently. some components would fix themselves, others would break in new creative ways.

## GPU nightmare

desktop has decent RTX 4080. laptop has... laptop 3060 that Unity barely acknowledges exists. suddenly "optimized" VR project that ran smoothly on desktop was getting 5fps in editor.

real kicker? Quest 3 couldn't even connect properly. USB-C link kept failing, wireless streaming was stuttering mess, when finally got connected tracking was jittery.

## ComfyUI catastrophe

remember that Unity-ComfyUI integration i was proud of? completely broken on laptop. HTTP requests timing out, file paths wrong (Windows vs Windows somehow), even when got ComfyUI running locally was so slow mesh generation took five minutes instead of 30 seconds.

laptop's CPU apparently laughs at idea of running AI inference in reasonable timeframe.

## rollback panic

with consult approaching fast made painful decision to roll back to earlier project version - one before latest ComfyUI features and performance optimizations. basically month of work unavailable for demo.

this version was more stable, fewer dependencies, crucially had worked on laptop before. but meant showing wouter less impressive version than what actually had working on main machine.

## lesson learned

not wasting more time trying to make project work perfectly on laptop. just not worth frustration. from now sticking to main development machine for anything critical, treating laptop as backup for lightweight tasks only.

sometimes best fix is avoiding problem entirely.

VR development is finicky enough without adding hardware compatibility issues. when you find setup that works stick with it until project's done.

cross-platform compatibility is nice in theory but reality is modern development involves too many moving pieces with too many dependencies. something always breaks when moving between machines.

better to have one rock-solid development environment than constantly fighting compatibility issues across multiple setups.