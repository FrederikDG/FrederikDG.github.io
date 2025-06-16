---
title: Unity Setup
slug: unity-setup-quest3
publishDate: 08 June 2025
description: Setting up Unity for Meta Quest 3 development
---

# Getting Unity & Meta Quest 3 to Talk

So, after deciding to build this VR experience, the next step was getting Unity to play nice with my Meta Quest 3. Sounds straightforward, right? Well, not quite.

## The Setup Struggle

I started by trying to connect my PC to Unity and get everything set up. That involved tweaking settings on the VR headset, preparing the headset itself, and, of course, setting up Unity. But here's where things got a bit messy.

Unity had just released a new version—Unity 6—which changed a lot of things about how to approach VR development. On top of that, the transition from Oculus to Meta for the headsets introduced its own set of changes. This meant that if I was following one tutorial on YouTube, it might contradict another because of differences in timestamps and workflows.

Eventually, I decided to stick with Unity 2022.3.62f1 (Long Term Support) to keep things stable. This version had better support for the tools I needed and was less prone to unexpected changes.

## Choosing the Right XR Plugin

With Meta's acquisition of Oculus, features and integrations shifted. I needed to select a way of compiling the game, and the two main options were OpenXR and Oculus. OpenXR was widely regarded as the better option, especially since it's used in other platforms like three.js. So, it came to mind quicker.

But then I had to make sure it still worked with the plugins too! For ease of use, I created an empty 3D project file instead of using the VR template to ensure I understood what I was doing.

## Leveraging Meta's Tools

Meta released the Meta XR Interaction Toolkit SDK to help developers set up their VR games. It includes basic building blocks to have the bare bones working. After a lot of tinkering and adjusting, I finally had the first official passthrough ready. There was no content yet, but I saw the camera rig in Unity move when I moved my head, and I saw stuff in the headset.

## Lessons Learned

Setting up Unity for Meta Quest 3 development isn't as plug-and-play as one might hope. Between version changes, shifting company structures, and evolving best practices, it's essential to stay adaptable and do thorough research before diving in.
