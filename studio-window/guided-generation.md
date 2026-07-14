# Guided Generation

Generate new images that follow a **reference image** — its lines, its structure, or its style.

> 📷 **Image — `guided-generation.png`:** The Guided Generation tab with a sketch reference on the
> left and the generated result on the right.

All guided operations take a source/reference image; the prompt is usually optional and used to add
detail or direction.

## Sketch

Use a sketch or contour image as guidance — the result follows your line art.

* **Input:** a sketch/contour image (+ optional prompt).

## Structure

Use a structure / control image so the result keeps the same layout and composition.

* **Input:** a structure image (+ optional prompt).

## Style Guide

Use a **style reference** image to steer the look of a freshly generated image.

* **Input:** a style reference image (+ optional prompt).

## Style Transfer

Transfer the style characteristics of a reference onto your **source** image.

* **Input:** a source image and a style reference.

## From code

```csharp
using Glitch9.AI;

Texture2D fromSketch    = await sketch.GENSketch("a knight in armor").ExecuteAsync();
Texture2D fromStructure = await control.GENStructure("cyberpunk street").ExecuteAsync();
Texture2D styled        = await source.GENStyleGuide().ExecuteAsync();
Texture2D transferred   = await source.GENStyleTransfer("watercolor").ExecuteAsync();
```

The prompt argument is optional for Sketch / Structure / Style Guide. Full API:
[Image Studio API](../scripting/README.md).

> **Tip:** the project-wide style used by *Apply Project Style* (Scene View / Project window) is
> configured in the **Project Art Profile** window (`Window > AI Image Studio > Project Art Profile`).
