---
title: Version Control Saved My Ass
slug: version-control-salvation
publishDate: 07 August 2025
description: How I learned to stop worrying and love committing everything
---

# Version Control Saved My Ass

yesterday my Unity project corrupted. not "oh this script has error" way. "Unity won't even open project anymore" way. three weeks of work potentially gone.

## the backstory

during bachelor's thesis lost about two months work because was idiot about version control. was using git technically but only committed like once a week, had issues with LFS, eventually didn't have anything properly saved.

swore never let that happen again.

## this time different

for this VR project been religious about version control. every day, multiple commits, actual descriptive messages. using Plastic SCM because Unity likes it and honestly been solid.

so when Unity started throwing corrupted project file errors and refusing to open anything wasn't panicking. annoyed sure. but not panicking.

## the corruption

started small. some prefabs stopped working. then scene file got weird - objects weren't where should be, components missing references. classic corruption symptoms.

tried usual Unity fixes:
- delete Library folder and reimport
- restart Unity
- restart computer  
- clear cache
- sacrifice rubber duck to Unity gods

nothing worked. seemed to get worse. eventually Unity refused to open project claiming version was incompatible or corrupted.

## the salvation

here's where version control proved worth. went back to commit history, found version from two days earlier that definitely worked, reverted everything.

five minutes later had working project again. lost maybe six hours work instead of three weeks.

## what actually lost

frustrating part is lost some good work. had just gotten ComfyUI integration working smoothly, fixed bunch interaction bugs, added nice visual feedback for mesh generation.

but rebuilding those six hours with knowledge of what actually works is way faster than figuring it out first time. plus second implementation usually cleaner anyway.

## commit discipline

what learned from bachelor's disaster and applied to project:

**commit every day.** even if just "worked on menu positioning" or "debugging interaction system." future you will thank present you.

**commit before risky changes.** about to rewrite interaction system? commit first. installing new package that might break everything? commit first.

**meaningful messages.** "fixed grab detection when objects close together" infinitely more useful than "fixed stuff" when trying to figure out when something broke.

**branch for experiments.** when testing different ComfyUI integration approaches made separate branches. most were dead ends but successful approach merged back cleanly.

## the lesson

real lesson isn't about version control tools (though Plastic SCM been solid). about treating code like it might disappear any moment because sometimes it will.

hard drives die. projects corrupt. Unity updates break everything. laptops get stolen. these aren't hypothetical disasters - they're Tuesday.

version control isn't just backup. it's time travel. ability to say "this was working yesterday let me go back to yesterday" instead of "guess i'll start over."

## looking forward

actually glad this happened early-ish instead of near deadline. reinforced good habits and proved workflow can handle disasters.

plus rebuilding lost features gave chance to improve them. new ComfyUI integration more robust, interaction system cleaner, better error handling throughout.

sometimes need to lose work to appreciate tools that help you not lose work.

## practical advice

if working on any creative project:

use version control. git, plastic, perforce, whatever. just use something.

commit frequently. daily minimum, hourly if making big changes.

write actual commit messages. future confused self will thank you.

test recovery process. make sure actually know how to revert changes before need to.

and if still not convinced version control matters just wait. eventually hard drive will crash or project will corrupt or laptop will grow legs and walk away.

when that happens you'll either be grateful you have version control or you'll be starting over from scratch.

know which one i'd rather be.