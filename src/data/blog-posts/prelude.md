---
title: Prelude 🚀
slug: prelude
publishDate: 07 january 2025
description: Kicking off research into educational AI-driven VR experiences.
---

## Diving into VR: First Steps and Key Decisions

I’ve spent some time dabbling and experimenting with VR in the past, and now I’m ready to scale up and create something more complex—specifically, an AI-driven VR experience that’s educational and genuinely helpful for users. Over the next few weeks, I’ll be wrestling with some essential questions about hardware, software, and AI design. My goal is to document each decision, the reasoning behind it, and the lessons I learn along the way.

### Choosing Hardware: Meta Quest 3 vs. Apple Vision Pro

- **Meta Quest 3**  
  - User-friendly and beginner-friendly.  
  - Wide adoption, large community, plenty of tutorials and assets.  
  - Development with Unity aligns with my current skill set.  
  - I already have one at home, which makes prototyping and testing easier.

- **Apple Vision Pro**  
  - Advanced mixed reality capabilities—seamlessly blending virtual and real environments.  
  - Access to Apple’s latest SDKs and frameworks for spatial computing.  
  - Steeper learning curve if you’re not already immersed in Apple’s development ecosystem.  

In the early weeks, I need to decide where to focus my limited time. The Meta Quest 3 feels like a sensible starting point because I can hit the ground running in Unity. Once I have a basic VR prototype running on Quest 3, I can revisit the Vision Pro’s strengths for a future iteration.


![Meta Quest 3 VR Headset vs Apple Vision Pro](https://framerusercontent.com/images/ISw3cywNyl5JrPxg0rUizyYpYKg.png)



### Unity vs. Apple SDKs

Since most Meta Quest applications are built with Unity, I can leverage what I already know—C# scripting, Unity’s asset pipeline, and the existing libraries for VR interactions. If I were to switch to Vision Pro right away, I would need to learn Swift, Xcode, and Apple’s RealityKit/ARKit frameworks. Both paths are valuable, but I want to avoid reinventing my workflow in these first weeks. My plan is to build a simple Unity project for Quest 3, then experiment with Vision Pro once I’m comfortable.

### AI Implementation: Assistant vs. Immersive Environment

There are two main directions I’m considering for AI:

1. **Personal Assistant Experience**  
   - The AI acts like a guide: answering questions, directing users based on their individual needs, and offering contextual tips.  
   - Example: A user asks “How do I solve this physics problem?” and the virtual assistant guides them step by step through the solution.  
   - Pros: More straightforward to prototype—chat UI or voice commands can come later.  
   - Cons: Less “immersive” in the sense of exploring a fully AI-driven world.

2. **Expansive, Immersive World**  
   - Create a virtual environment where AI agents control NPCs, interactive objects, or adaptive scenarios.  
   - Example: Users navigate a virtual biology lab, and AI adapts experiments or challenges based on their performance.  
   - Pros: Higher potential for engagement and “wow” factor.  
   - Cons: Significantly more complex to design, especially in the early weeks.

For the sake of getting something working, I’ll start with a simple “assistant” prototype—maybe a floating panel in VR that listens for voice or button input and provides feedback. Once that foundation is solid, I can iterate toward a more immersive setting.

### Resources for Getting Started

I’ve already found two YouTube channels that break down the initial steps really well. I’ll spend the next few days soaking in these tutorials:

- **Valem Tutorials (Meta Quest 3 focus)**  
  [Getting Started with Meta Quest 3 in Unity](https://www.youtube.com/watch?v=HhtTtvBF5bI&list=PLpEoiloH-4eP-OKItF8XNJ8y8e1asOJud&ab_channel=ValemTutorials)  
  Valem covers everything from setting up the Unity project to basic VR interactions on Quest 3.

- **Dilmer Valecillos (Apple Vision Pro focus)**  
  [Introduction to Apple Vision Pro Development](https://www.youtube.com/watch?v=SDpQ1ooAla8&list=PLQMQNmwN3Fvwx18OKmvgk5itrqhyqblB1&index=1&ab_channel=DilmerValecillos)  
  Dilmer walks through Xcode setup, RealityKit basics, and mixed reality principles.

There’s also a shorter primer that bridges some of the concepts between these two platforms:  
[Bridging VR Platforms](https://youtu.be/kbBYcVrGZus)  

I’ll take notes on how their workflows differ—particularly the asset pipelines, input handling, and performance considerations.

<!-- <iframe
  width="560"
  height="315"
  src="https://www.youtube.com/embed/dQw4w9WgXcQ"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen
></iframe> -->

### My Early-Stage Plan

1. **Set Up a Basic Unity VR Project for Meta Quest 3**  
   - Install the latest Oculus Integration package.  
   - Create a simple scene: a plane, some basic interactable objects, and a teleport system.  
   - Verify headset tracking, hand controllers, and basic interactions (grab, point, teleport).

2. **Prototype a Simple AI Assistant in VR**  
   - Implement a UI canvas that appears in world space when the user presses a button.  
   - Connect a basic AI API (e.g., an open-source natural language model or a simple rule-based system).  
   - Allow users to type or speak a question and get a text/voice response inside the VR scene.

3. **Document Every Step**  
   - Take screenshots and short screen recordings as I go.  
   - Note any challenges—especially around performance, comfort, and user experience in VR.  
   - Reflect on whether a fully immersive world might be possible by the time I’m comfortable with the basics.

4. **Plan for Vision Pro Exploration**  
   - Once the Quest 3 assistant prototype is functional, start a parallel branch for Vision Pro.  
   - Migrate simple interactions to RealityKit to compare performance and development ergonomics.  
   - Test mixed reality use cases—such as combining real-world objects with virtual overlays.

### Looking Ahead

In these first weeks, success for me means having a working Unity build on Meta Quest 3 that can accept simple AI-driven input from a user. I don’t need bells and whistles yet—just a stable foundation. Once the assistant prototype is live, I’ll reassess:

- How well does the AI understand and respond in a headset environment?  
- Are there latency or usability issues that need a rethink?  
- What’s the minimal set of “immersive” features I can add without exploding development time?

By mid-July, I hope to show a friend or mentor a short demo: “Here’s my VR scene, and here’s how the AI answers your questions.” From there, I’ll either double down on enhancing the assistant’s intelligence or start designing that broader immersive world.

Stay tuned for my next update, where I’ll detail the exact Unity setup steps, share code snippets for the AI integration, and reflect on the first set of challenges I tackle. Excited to document this journey and learn as I build!
