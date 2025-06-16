---
title: Giving My Voice a Role  
slug: voice-console-integration  
publishDate: 10 June 2025  
description: Implementing local voice transcription and an in-game console on Meta Quest 3  
---

# Giving My Voice a Role

After getting basic interactions up and running in my VR project, I wanted to add voice capabilities. Specifically, I aimed to transcribe my speech in real-time and display it within the VR environment. Additionally, I sought a straightforward in-game console to log messages without removing the headset.

## Implementing Local Voice Transcription

To achieve on-device speech-to-text functionality, I integrated OpenAI's Whisper model into Unity using the [whisper.unity](https://github.com/saurabhchalke/whisper-meta-quest) package. This setup allows for local transcription on the Meta Quest 3 without relying on internet connectivity.

### Setup Steps:

1. **Integrate Whisper.unity**: Added the `whisper.unity` package to my Unity project via the Package Manager using the Git URL:  
   `https://github.com/Macoron/whisper.unity.git?path=/Packages/com.whisper.unity`.

2. **Model Placement**: Downloaded the Whisper tiny model and placed it in the `StreamingAssets` folder to ensure it's included in the build.

3. **Microphone Input**: Utilized Unity's `Microphone` API to capture audio input from the Quest 3's built-in microphone.

4. **Transcription Display**: Created a UI text element anchored at the bottom of the VR interface to display the transcribed text in real-time.

This configuration provided a responsive and immersive way to visualize spoken words within the VR environment.

## Adding an In-Game Console for Logging

For debugging purposes, I implemented a basic in-game console to display log messages directly within the VR scene.

### Implementation Details:

- **Console UI**: Designed a simple UI panel using Unity's UI system, positioned it within the VR space for easy visibility.

- **Log Capture**: Subscribed to Unity's `Application.logMessageReceived` event to capture log messages and display them in the console panel.

- **Performance Considerations**: Ensured that the console only appears in development builds to avoid performance overhead in production.

This setup allowed me to monitor logs without removing the headset, streamlining the development and debugging process.

## Conclusion

Integrating local voice transcription and an in-game console enhanced the interactivity and debuggability of my VR project on the Meta Quest 3. Utilizing the `whisper.unity` package enabled efficient on-device speech recognition, while the in-game console provided immediate feedback during development.
