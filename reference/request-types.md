# Request Types

AI Image Studio adds **11 Unified API request classes** on top of the base package (which ships
`ImageGenerationRequest` and `ImageInpaintingRequest`). Each is created by a `GEN*` extension and
run with `ExecuteAsync()`.

| Request class | Extension | Operation |
|---|---|---|
| `ImageOutpaintRequest` | `GENOutpaint(...)` | Expand an image beyond its bounds and generate the extended area |
| `UpscaleRequest` | `GENUpscale(...)` | Increase resolution with AI upscaling + detail enhancement |
| `BackgroundRemovalRequest` | `GENBackgroundRemoval(...)` | Segment the foreground and remove the background |
| `SearchAndRecolorRequest` | `GENSearchAndRecolor(...)` | Find an object by prompt and recolor/restyle it (maskless) |
| `SearchAndReplaceRequest` | `GENSearchAndReplace(...)` | Find an object by prompt and replace it (maskless) |
| `EraseObjectRequest` | `GENErase(...)` | Remove selected regions/objects |
| `ImageSketchRequest` | `GENSketch(...)` | Use a sketch/contour image as generation guidance |
| `ImageStructureRequest` | `GENStructure(...)` | Use a structure/control image as generation guidance |
| `StyleGuideRequest` | `GENStyleGuide(...)` | Use a style reference image to guide generation |
| `StyleTransferRequest` | `GENStyleTransfer(...)` | Transfer style from a reference onto the source |
| `ReplaceBackgroundAndRelightRequest` | `RequestType.ImageReplaceBgAndRelight` | Replace the background and relight the subject |

## Base package (for reference)

| Request class | Extension | Operation |
|---|---|---|
| `ImageGenerationRequest` | `GENImage(...)` | Text-to-Image / Image-to-Image |
| `ImageInpaintingRequest` | `GENInpaint(...)` | Mask-based inpaint |

## Notes

* Extensions are defined for `Texture2D`, `Sprite`, `File<Texture2D>`, and `ImageInput` sources.
* All requests support `.SetModel(...)` and resolve to a `Texture2D` via `ExecuteAsync()`.
* For usage examples, see the [Image Studio API](../scripting/README.md).
