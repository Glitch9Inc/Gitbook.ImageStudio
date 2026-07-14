# Image Studio API

Every operation in AI Image Studio is available from code as a **fluent request extension**, using
the same pattern as the base AI DevKit Unified API:

```
source.GENSomething(...).SetModel(...).ExecuteAsync()
```

The extensions live in the `Glitch9.AI` namespace and hang off `Texture2D`, `Sprite`,
`File<Texture2D>`, and `ImageInput`. Each returns a **request object** you can configure further
before awaiting `ExecuteAsync()`, which resolves to a `Texture2D`.

```csharp
using Glitch9.AI;
```

## Utilities

```csharp
// Upscale (no prompt)
Texture2D bigger = await source.GENUpscale().ExecuteAsync();

// Remove background → transparent cutout
Texture2D cutout = await source.GENBackgroundRemoval().ExecuteAsync();
```

## Editing

```csharp
// Outpaint — extend the image; instruction steers the new area
Texture2D wider = await source.GENOutpaint("extend the alley to the left").ExecuteAsync();

// Erase a region (mask-based)
Texture2D erased = await source.GENErase("remove the wires").ExecuteAsync();

// Maskless object edits
Texture2D recolored = await source.GENSearchAndRecolor("the car").ExecuteAsync();
Texture2D replaced  = await source.GENSearchAndReplace("the wooden crate").ExecuteAsync();
```

## Guided generation

```csharp
Texture2D fromSketch    = await sketch.GENSketch("a knight in armor").ExecuteAsync();
Texture2D fromStructure = await control.GENStructure("cyberpunk street").ExecuteAsync();
Texture2D styled        = await source.GENStyleGuide().ExecuteAsync();          // prompt optional
Texture2D transferred   = await source.GENStyleTransfer("watercolor").ExecuteAsync();
```

## Method reference

| Extension | Source overloads | Instruction arg | Request type |
|---|---|---|---|
| `GENUpscale()` | Texture2D, Sprite, File\<Texture2D>, ImageInput | — | `UpscaleRequest` |
| `GENBackgroundRemoval()` | Texture2D, Sprite, File\<Texture2D>, ImageInput | optional | `BackgroundRemovalRequest` |
| `GENOutpaint(instruction)` | Texture2D, Sprite, File\<Texture2D>, ImageInput | required* | `ImageOutpaintRequest` |
| `GENErase(instruction)` | Texture2D, Sprite, File\<Texture2D>, ImageInput | required* | `EraseObjectRequest` |
| `GENSearchAndRecolor(instruction)` | Texture2D, Sprite, File\<Texture2D>, ImageInput | required* | `SearchAndRecolorRequest` |
| `GENSearchAndReplace(instruction)` | Texture2D, Sprite, File\<Texture2D>, ImageInput | required* | `SearchAndReplaceRequest` |
| `GENSketch(instruction)` | Texture2D, Sprite, File\<Texture2D>, ImageInput | optional | `ImageSketchRequest` |
| `GENStructure(instruction)` | Texture2D, Sprite, File\<Texture2D>, ImageInput | optional | `ImageStructureRequest` |
| `GENStyleGuide(instruction)` | Texture2D, Sprite, File\<Texture2D>, ImageInput | optional | `StyleGuideRequest` |
| `GENStyleTransfer(instruction)` | Texture2D, Sprite, File\<Texture2D>, ImageInput | required* | `StyleTransferRequest` |

\* The `ImageInput` overload takes no instruction argument — set the prompt/options on the returned
request object instead.

> **Text-to-Image** and **Inpaint** come from the base AI DevKit package (`GENImage`,
> `GENInpaint`). **Replace Background & Relight** is exposed via
> `RequestType.ImageReplaceBgAndRelight`. See [Request Types](../reference/request-types.md).

## Choosing a provider/model

```csharp
Texture2D result = await source
    .GENUpscale()
    .SetModel(/* a Stability or Replicate model id */)
    .ExecuteAsync();
```

If you don't call `SetModel`, the default model configured in
[Settings](../editor-tools/settings.md) is used. Provider-specific options are set on the request
object where supported — see [Extra Providers](../providers/README.md).
