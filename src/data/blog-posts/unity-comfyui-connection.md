---
title: Bridging Unity and ComfyUI
slug: unity-comfyui-connection
publishDate: 30 June 2025
description: HTTP requests, JSON parsing, and async file transfers in VR
---

# Making Unity Talk to ComfyUI

I had ComfyUI running locally with Trellis workflow for image-to-mesh conversion. I had Unity capturing screenshots from VR. Getting them to actually communicate? Bigger project than expected.

## The Goal

Simple concept: take photo in VR, send to ComfyUI, get 3D mesh back, drop into scene. Real-time object scanning basically. Sounds straightforward until you try implementing it.

## ComfyUI's API Structure

ComfyUI has an API but it's not exactly REST-friendly. Built around queuing workflows and status checking, not simple "send image get mesh" requests.

Workflow:

1. POST workflow JSON to `/prompt`
2. Get prompt ID back
3. Poll `/history/{prompt_id}` until completion
4. Download output files

Each step can fail creatively.

## Unity HTTP pain points

Unity's UnityWebRequest handles basic requests fine but multipart uploads, JSON parsing, and file downloads get messy fast. ended up building entire client system:

```csharp
public class ComfyUIClient : MonoBehaviour
{
    private string apiUrl = "http://localhost:8188";

    public async Task<string> GenerateMesh(Texture2D image)
    {
        byte[] imageData = image.EncodeToPNG();
        string imageId = await UploadImage(imageData);
        string promptId = await QueueWorkflow(imageId);
        await WaitForCompletion(promptId);
        return await DownloadMesh(promptId);
    }
}
```

## Workflow JSON Complexity

ComfyUI workflows are massive JSON structures defining every node and connection. Making this work dynamically meant:

- Export working Trellis workflow as JSON
- Locate image input node ID
- Replace image filename with uploaded image ID at runtime

Required parsing and rebuilding JSON in Unity with C#'s type system. Not fun.

## File Transfer Headaches

Biggest pain was file handling. ComfyUI expects images in input folder but API upload uses different location. Output files have generated names parsed from history responses.

Built custom system that uploads images with predictable names, maps ComfyUI internal IDs to filenames, downloads OBJ files and converts to Unity meshes.

## VR Integration Challenges

All HTTP operations needed to happen without freezing VR experience. Everything had to be async with loading indicators and proper error handling.

Tricky part is keeping user engaged during 10-30 second processing time. Added spinning loading indicator and feedback text but still long wait.

## Final Result

After week of debugging HTTP requests and JSON parsing have system that:

- Captures VR screenshots
- Sends to local ComfyUI
- Generates basic 3D mesh
- Imports back to Unity
- Spawns in VR scene

Not fast and mesh quality varies but works. Seeing photographed object appear as 3D model in VR is pretty magical even when it looks like clay sculpture.

## Lesson Learned

Most work wasn't fancy AI stuff - just getting two systems to exchange files reliably. Unity wants Texture2D objects, ComfyUI wants PNG files in specific folders, everyone has different async operation ideas.

Sometimes most "AI-powered" part of project is complicated file upload script.
