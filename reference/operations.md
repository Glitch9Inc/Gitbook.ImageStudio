# Operations & Required Inputs

Every operation validates its inputs before it will run. The **Generate** button stays disabled
until the requirements below are met.

| Operation | Group | Prompt | Source image | Mask | Target + edit prompts |
|---|---|:---:|:---:|:---:|:---:|
| Text-to-Image | Generate | ✅ | — | — | — |
| Image-to-Image | Generate | ✅ | ✅ | — | — |
| Inpaint | Edit | ✅ | ✅ | ✅ | — |
| Erase | Edit | — | ✅ | ✅ | — |
| Recolor Object | Edit | — | ✅ | — | ✅ |
| Replace Object | Edit | — | ✅ | — | ✅ |
| Outpaint | Edit | optional | ✅ | — | — |
| Sketch | Guided | optional | ✅ (sketch) | — | — |
| Structure | Guided | optional | ✅ (structure) | — | — |
| Style Guide | Guided | optional | ✅ (style ref) | — | — |
| Style Transfer | Guided | optional | ✅ (+ style ref) | — | — |
| Upscale | Utility | — | ✅ | — | — |
| Remove Background | Utility | — | ✅ | — | — |
| Replace Background & Relight | Utility | optional | ✅ | — | — |

## Rules of thumb

* **Text-to-Image** is the only operation that doesn't need a source image.
* **Inpaint** and **Erase** need a **painted mask** — see
  [Masking & Canvas](../studio-window/masking-and-canvas.md).
* **Recolor / Replace Object** are *maskless*: a **target prompt** finds the object and an **edit
  prompt** describes the change.
* Availability also depends on the selected **provider/model** — an operation a model can't perform
  is not offered. See [Extra Providers](../providers/README.md).
