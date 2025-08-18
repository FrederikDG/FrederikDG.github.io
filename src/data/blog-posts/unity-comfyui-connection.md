---
title: Bridging Unity and ComfyUI - Or How I Learned to Stop Worrying and Love HTTP Requests
slug: unity-comfyui-connection
publishDate: 30 June 2025
description: Getting Unity to talk to ComfyUI for real-time 3D mesh generation from VR screenshots
---

# Bridging Unity and ComfyUI - Or How I Learned to Stop Worrying and Love HTTP Requests

Alright, so I had ComfyUI running locally with that Trellis workflow for image-to-mesh conversion. And I had Unity capturing screenshots from inside VR. But getting them to actually talk to each other? That turned into a bigger project than I expected.

## The Goal

The idea was simple: take a photo in VR, send it to ComfyUI, get a 3D mesh back, drop it into the scene. Real-time object scanning, basically. Sounds straightforward until you actually try to do it.

## ComfyUI's API (Sort Of)

ComfyUI has an API, but it's not exactly REST-friendly. It's built around queuing workflows and checking status, not simple "send image, get mesh" requests. The workflow looks like this:

1. POST your workflow JSON to `/prompt`
2. Get back a prompt ID
3. Poll `/history/{prompt_id}` until it's done
4. Download the output files

Simple enough, except each step can fail in creative ways.

## Unity's HTTP Client (The Painful Part)

Unity's `UnityWebRequest` is... fine. But when you're dealing with multipart uploads, JSON parsing, and file downloads, it gets messy fast. Here's what I ended up building:

```csharp
public class ComfyUIClient : MonoBehaviour
{
    private string apiUrl = "http://localhost:8188";
    
    public async Task<string> GenerateMesh(Texture2D image)
    {
        // Convert texture to byte array
        byte[] imageData = image.EncodeToPNG();
        
        // Upload image first
        string imageId = await UploadImage(imageData);
        
        // Queue the workflow
        string promptId = await QueueWorkflow(imageId);
        
        // Wait for completion
        await WaitForCompletion(promptId);
        
        // Download the mesh
        return await DownloadMesh(promptId);
    }
}
```

The devil is in the implementation of those methods. `UploadImage` needs to handle multipart form data. `QueueWorkflow` requires building the workflow JSON dynamically with the uploaded image ID. `WaitForCompletion` is basically polling hell.

## The Workflow JSON Nightmare

ComfyUI workflows are these massive JSON structures that define every node and connection. To make this work dynamically, I had to:

1. Export my working Trellis workflow as JSON
2. Find the image input node ID 
3. Replace the image filename with the uploaded image ID at runtime

This meant parsing and rebuilding JSON in Unity, which is always fun with C#'s type system.

## File Transfer Headaches

The biggest pain was actually getting files back and forth. ComfyUI expects images in its input folder, but the API upload puts them somewhere else. The output files have generated names that you have to parse from the history response.

I ended up writing a custom file transfer system that:
- Uploads images with predictable names
- Maps ComfyUI's internal file IDs to actual filenames  
- Downloads .obj files and converts them to Unity meshes

## Making It Work in VR

All this HTTP request dance needed to happen without freezing the VR experience. So everything had to be async:

```csharp
public async void OnCameraCapture()
{
    // Capture screenshot
    Texture2D screenshot = CaptureVRView();
    
    // Show loading indicator
    ShowLoadingUI();
    
    try 
    {
        // Send to ComfyUI (this takes 10-30 seconds)
        string meshPath = await comfyClient.GenerateMesh(screenshot);
        
        // Load into Unity
        GameObject mesh = LoadMeshFromFile(meshPath);
        
        // Spawn in VR scene
        SpawnMeshInVR(mesh);
    }
    finally 
    {
        HideLoadingUI();
    }
}
```

The tricky part is keeping the user engaged during that 10-30 second processing time. I added a spinning loading indicator and some feedback text, but it's still a long wait.

## What Actually Works

After about a week of debugging HTTP requests and JSON parsing, I have a system that:
- Takes a VR screenshot
- Sends it to ComfyUI running locally
- Generates a basic 3D mesh
- Imports it back into Unity
- Spawns it in the VR scene

It's not fast, and the mesh quality is hit-or-miss, but it works. Seeing an object you just photographed appear as a 3D model in VR is pretty magical, even when it looks like it was made of clay.

## The Real Lesson

Most of the work here wasn't the fancy AI stuff - it was just getting two different systems to exchange files reliably. Unity wants Texture2D objects, ComfyUI wants PNG files in specific folders, everybody has different ideas about how async operations should work.

Sometimes the most "AI-powered" part of your project is just a really complicated file upload script.