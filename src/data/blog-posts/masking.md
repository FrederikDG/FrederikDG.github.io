---
title: Masking?  
slug: masking  
publishDate: 20 June 2025  
description: Using object masking to isolate the subject for better 3D mesh results  
---

Now that I had a base workflow, I wanted to make it better. Having basic images placed in the ComfyUI cycle was ok, but it meant that sometimes—especially when your field of vision wasn’t super clean—it just didn’t pick the right subject. Sometimes it mashed a few things together into a weird Frankenstein hybrid, or straight-up ignored the thing I actually cared about.

Now, I mentioned ComfyUI in the last post because I had some fun with it during my internship at **This January** in Washington this past spring. Over there, I made a workflow that masked out objects that were the point of interest. So by combining the two approaches, I ended up generating:
- an image of the scene,
- an alpha matte showing the subject I wanted,
- and a 3D mesh *just* from that object.


The issue I’m hitting now is that in the past, I always used **text prompts** to guide what to mask out—like: “car”, “tree”, “robot” or whatever the main thing was. That works when you’ve got a screen and a keyboard. But once you’re inside the VR headset… things get tricky.

Still brainstorming how to solve that bit, maybe voice commands? Maybe eye tracking? Not sure yet. But getting there.

