---
title: Version Control Saved My Ass (Again)
slug: version-control-salvation
publishDate: 07 August 2025
description: How I learned to stop worrying and love committing everything
---

# Version Control Saved My Ass (Again)

Yesterday, my Unity project corrupted. Not in a "oh this script has an error" way. In a "Unity won't even open the project anymore" way. Three weeks of work, potentially gone.

## The Backstory

During my bachelor's thesis, I lost about two months of work because I was an idiot about version control. I was using Git, technically, but I only committed like once a week via github, having issues with LTS and eventually not having anything properly saved. We all know how that ended.

I swore I'd never let that happen again.

## This Time Was Different

For this VR project, I've been religious about version control. Every day, multiple commits, actual descriptive messages. Using Plastic SCM because Unity likes it, and honestly it's been solid.

So when Unity started throwing errors about corrupted project files and refusing to open anything, I wasn't panicking. Annoyed, sure. But not panicking.

## The Corruption

It started small. Some prefabs stopped working properly. Then the scene file got weird - objects weren't where they should be, components were missing references. Classic corruption symptoms.

I tried the usual Unity fixes:
- Delete Library folder and reimport
- Restart Unity
- Restart computer
- Clear the cache
- Sacrifice a rubber duck to the Unity gods

Nothing worked. In fact, it seemed to get worse. Eventually Unity just refused to open the project at all, claiming the project version was incompatible or corrupted.

## The Salvation

Here's where version control proved its worth. I went back to my commit history, found a version from two days earlier that definitely worked, and just reverted everything.

Five minutes later, I had a working project again. Lost maybe six hours of work instead of three weeks.

## What I Actually Lost

The frustrating part is that I lost some good work. I had just gotten the ComfyUI integration working smoothly, fixed a bunch of interaction bugs, and added some nice visual feedback for the mesh generation process.

But you know what? Rebuilding those six hours of work with the knowledge of what actually works is way faster than trying to figure it out the first time. Plus, the second implementation is usually cleaner anyway.

## The Commit Discipline

Here's what I learned from my bachelor's disaster and applied to this project:

**Commit every single day.** Even if it's just "worked on menu positioning" or "debugging interaction system." Future you will thank present you.

**Commit before trying anything risky.** About to completely rewrite the interaction system? Commit first. Installing a new package that might break everything? Commit first.

**Meaningful commit messages.** "Fixed grab detection when objects are close together" is infinitely more useful than "fixed stuff" when you're trying to figure out when something broke.

**Branch for experiments.** When I was testing different ways to integrate with ComfyUI, I made separate branches. Most of them were dead ends, but the successful approach got merged back cleanly.

## The Meta Lesson

The real lesson isn't about version control tools (though Plastic SCM has been solid). It's about treating your code like it might disappear at any moment, because sometimes it will.

Hard drives die. Projects corrupt. Unity updates break everything. Your laptop gets stolen. These aren't hypothetical disasters - they're Tuesday.

Version control isn't just backup. It's time travel. It's the ability to say "this was working yesterday, let me go back to yesterday" instead of "I guess I'll start over."

## Looking Forward

I'm actually glad this happened early-ish in the project instead of near the deadline. It reinforced good habits and proved that my workflow can handle disasters.

Plus, rebuilding those lost features gave me a chance to improve them. The new ComfyUI integration is more robust, the interaction system is cleaner, and I have better error handling throughout.

Sometimes you need to lose work to appreciate the tools that help you not lose work.

## Practical Advice

If you're working on any kind of creative project:

1. **Use version control.** Git, Plastic, Perforce, whatever. Just use something.
2. **Commit frequently.** Daily at minimum, hourly if you're making big changes.
3. **Write actual commit messages.** Your future confused self will thank you.
4. **Test your recovery process.** Make sure you actually know how to revert changes before you need to.

And if you're still not convinced that version control matters, just wait. Eventually your hard drive will crash, or your project will corrupt, or your laptop will grow legs and walk away.

When that happens, you'll either be grateful you have version control, or you'll be starting over from scratch.

I know which one I'd rather be.