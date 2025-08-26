---
title: Giving My Voice a Role  
slug: voice-console-integration  
publishDate: 14 June 2025  
description: Implementing local voice transcription and an in-game console on Meta Quest 3  
---

# Adding Voice and Debug Console

after basic interactions were working wanted to add voice capabilities. specifically transcribe speech in real-time and display it in VR. also wanted simple in-game console to see debug messages without removing headset.

## local voice transcription

integrated OpenAI's Whisper model using whisper.unity package for on-device speech-to-text. works locally on quest 3 without internet dependency.

### setup process:

1. added whisper.unity package via git URL in package manager
2. downloaded whisper tiny model, placed in StreamingAssets folder  
3. used Unity's Microphone API for audio input from quest's built-in mic
4. created UI text element at bottom of VR interface for real-time display

responsive setup that made spoken words visible in VR environment.

## in-game console for debugging

built basic console to display log messages directly in VR scene.

simple UI panel using Unity's UI system, positioned in VR space for visibility. subscribed to Unity's `Application.logMessageReceived` event to capture and display log messages in console panel.

ensured console only appears in development builds to avoid performance overhead in production.

## results

voice transcription and console enhanced interactivity and debuggability significantly. whisper.unity handled speech recognition efficiently on-device while console provided immediate feedback during development.

both features streamlined VR development process by reducing need to remove headset for debugging or text input.