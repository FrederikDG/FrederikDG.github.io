---
title: User Testing Reality Check
slug: user-testing-humbling
publishDate: 02 July 2025
description: Watching people use your VR project is both enlightening and terrifying
---

# When Users Meet Your Project

thought my VR project was intuitive. point at things, grab stuff, take pictures, watch AI generate 3D models. simple right?

then watched first user try it.

## the setup

brought project to few friends for feedback. nothing formal, just "want to try this VR thing i'm working on?" figured i'd get validation and minor suggestions.

was not prepared for what actually happened.

## user #1: controller confusion

first person puts on headset, starts looking around - good sign. sees floating menu, points at it with controller ray... nothing happens.

turns out never explained you need to pull trigger to click. in my head "point and click" was obvious. to them pointing was entire interaction.

after explaining trigger they started clicking everything rapidly, spawning cubes and spheres everywhere. apparently spawn cooldown wasn't aggressive enough. within 30 seconds scene was chaos.

## user #2: hand tracking optimist

second person immediately asks if they can use hand tracking instead of controllers. sure i say, it's supported.

ha. 

spent five minutes trying to get hand tracking to recognize their gestures while they waved at headset. when it finally worked grab detection was maybe 50% reliable. they got frustrated quickly and asked for controllers back.

## user #3: feature hunter

third person got basic interactions working quickly. spawned objects, grabbed them, moved them around. great!

then started asking questions:
- "can i change colors?"
- "how do i delete objects?"
- "can i save my scene?"
- "can i share this?"

all reasonable questions. all features i hadn't implemented because was focused on core AI integration.

## the AI disappointment

when we got to main feature - taking pictures and generating 3D models - things got really humbling.

first picture was coffee mug. perfect test case i thought. simple object, clear shape, should work great.

generated mesh looked like melted candle. recognizably mug-shaped but barely. took 40 seconds to generate while they stood there waiting.

"is it supposed to look like that?" they asked.

no. no it is not.

## what actually worked

not everything was disaster. few things people genuinely liked:

- passthrough integration felt "natural" and "cool"
- once they understood spawning system people enjoyed creating little scenes
- floating menu following gaze was intuitive  
- when AI generation actually worked the "wow factor" was real

## lessons learned

users don't read your mind. what seems obvious to developer isn't obvious to first-time user.

need better onboarding, clearer feedback, more forgiving interaction systems. also need to manage expectations about AI generation quality and speed.

but most importantly: user testing early and often. better to find these issues now than after spending months polishing features nobody can figure out how to use.

humbling but necessary reality check.