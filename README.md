---
description: Generate, edit, and clean up image assets directly inside the Unity Editor.
---

# AI Image Studio

**AI Image Studio** brings a full AI image generation and editing workflow into Unity. Instead of
switching between external AI tools, image editors, background removers, and Unity import steps, you
create, edit, clean up, and save image assets in one place — and the results land straight in your
project folder.

It's built on **[AI DevKit](https://assetstore.unity.com/packages/tools/generative-ai/ai-dev-kit-pro-281225)**
and reuses its Unified API, API keys, and model library — adding a dedicated editor window, extra
providers, new request types, and Scene View / Project window shortcuts. **The AI DevKit core is
included in the package**, so you don't need to install AI DevKit separately.

> 📷 **Image — `hero.png`:** The AI Image Studio window with a generated image in the preview, the
> operation tabs visible, and the side panel showing prompt + settings.

## Two ways to use it

* **In the editor** — the [AI Image Studio window](studio-window/README.md) plus one-click
  [Scene View](editor-tools/scene-view-overlay.md) and
  [Project window](editor-tools/project-window-actions.md) actions.
* **From code** — the [Unified API](scripting/README.md): fluent request extensions like
  `GENUpscale`, `GENOutpaint`, and `GENBackgroundRemoval` that follow the same
  `SetModel(...).ExecuteAsync()` pattern as AI DevKit.

## What you can do

| Category | Operations |
|---|---|
| **Generate** | Text-to-Image, Image-to-Image |
| **Edit** | Inpaint, Outpaint, Recolor Object, Replace Object, Erase |
| **Guided generate** | Sketch, Structure, Style Guide, Style Transfer |
| **Utilities** | Upscale, Remove Background, Replace Background & Relight |

## Use it for

Character concepts, item icons, UI graphics, backgrounds, sprites, transparent cutout assets,
prototype textures, marketing mockups, and placeholder art.

## Requirements

* Unity 6 (6000.x)
* An AI provider + API key (see [Providers & API Keys](setup/providers.md))

> The **AI DevKit core is bundled** with AI Image Studio — no separate AI DevKit install required.

## Next steps

* New here? Start with the [Quick Start](getting-started/quick-start.md).
* Want the mental model first? Read [Core Concepts](getting-started/core-concepts.md).
