# Generation

Create new images from a text prompt or from an existing image.

> 📷 **Image — `generation.png`:** The Generation tab with a prompt entered and a generated result
> in the preview.

## Text-to-Image

Generate an image from a prompt alone.

* **Requires:** a prompt.
* **Tips:** describe subject, style, and framing; mention *"transparent background"* or *"game
  asset"* when you need clean cutouts.

## Image-to-Image

Generate a new image guided by a **source image** plus a prompt — good for variations, restyles, and
"same thing, different look".

* **Requires:** a source image **and** a prompt.
* The source sets composition/subject; the prompt drives the change. Provider options such as
  **Creativity** control how far the result may drift from the source (model-dependent).

## Choosing a model

Pick a model in the side panel. Image Studio adds **Stability AI** and **Replicate** models on top of
the base AI DevKit library; provider-specific controls appear only when the selected model supports
them. See [Extra Providers](../providers/README.md).

## From code

```csharp
using Glitch9.AI;

// Text-to-Image (base AI DevKit)
Texture2D img = await "a rusty sci-fi door, game asset".GENImage().ExecuteAsync();

// Image-to-Image (base AI DevKit) — pass the source as a reference image
Texture2D variant = await "repaint it clean and futuristic"
    .GENImage(referenceImage: sourceTexture)
    .ExecuteAsync();
```

> Text-to-Image and Inpaint ship in the **base** AI DevKit package. The other operations in this
> guide are added by the Image Studio add-on. See [Image Studio API](../scripting/README.md).
