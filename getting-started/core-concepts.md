# Core Concepts

A quick mental model for how AI Image Studio is organized.

## Operations

Everything you do is an **operation** — a single image task. They fall into four groups:

| Group | Operations | Needs |
|---|---|---|
| **Generation** | Text-to-Image, Image-to-Image | Prompt (+ source for I2I) |
| **Editing** | Inpaint, Outpaint, Recolor Object, Replace Object, Erase | Source image (+ mask or target/edit prompts) |
| **Guided generation** | Sketch, Structure, Style Guide, Style Transfer | Source/reference image (+ optional prompt) |
| **Utilities** | Upscale, Remove Background, Replace Background & Relight | Source image |

Each operation validates its own inputs before it will run. See
[Operations & Required Inputs](../reference/operations.md) for the full matrix.

## Inputs

* **Prompt** — text describing what to generate or change.
* **Source image** — the image you are editing or transforming (everything except Text-to-Image).
* **Mask** — a painted region for mask-based operations (Inpaint, Erase).
* **Target + edit prompts** — for maskless object editing (Recolor / Replace Object): one prompt
  finds the object, the other describes the change.
* **Reference image** — a sketch, structure, or style image that guides generation.

## Providers & models

AI Image Studio runs on the same **model library** as AI DevKit and adds two provider families —
**Stability AI** and **Replicate** — as options where compatible. Provider-specific controls (Style
Preset, Inference Steps, Grow Mask, Creativity, …) appear in the editor only when the selected model
and operation support them. See [Extra Providers](../providers/README.md).

## Editor vs. code

You can do the same work two ways, and they share the same engine:

* **Editor** — the [window](../studio-window/README.md) and quick actions, tuned for iteration and
  saving assets into your project.
* **Code** — the [Unified API](../scripting/README.md): `source.GENUpscale().ExecuteAsync()` and
  friends, for automation and runtime workflows.

## Saving

Generated results are **real files** in your project. Generate operations save into the active
folder (or a default path) with an optional **Save As**; edit operations can **overwrite the
original** or **Save As**. After saving, the result can become the source for the next edit. See
[Saving Results](../studio-window/saving.md).

> Because generated images are real assets, they are **not** removed by Unity's Undo. Delete
> unwanted files manually.
