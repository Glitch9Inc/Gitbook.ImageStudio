# FAQ

**Is AI Image Studio standalone?**
No — it's an add-on for **AI DevKit**. Install and configure the base package (Lite or higher)
first, then add Image Studio.

**Do I need a new API key?**
No. Image Studio shares provider configuration with the AI DevKit core. Add keys for the extra
providers (Stability AI, Replicate) only if you use their models. See
[Providers & API Keys](../setup/providers.md).

**Which operations does it add?**
Outpaint, Upscale, Remove Background, Recolor Object, Replace Object, Erase, Sketch, Structure,
Style Guide, Style Transfer, and Replace Background & Relight — 11 request types on top of the base
Text-to-Image and Inpaint. See [Request Types](../reference/request-types.md).

**Can I use it from code?**
Yes. Every operation has a fluent extension (`GENUpscale`, `GENOutpaint`, …) that follows the AI
DevKit `SetModel(...).ExecuteAsync()` pattern. See [Image Studio API](../scripting/README.md).

**Where do generated images go?**
Into your project as real assets — the active folder or a default path, with Save As / Overwrite
options. They are **not** part of Unity's Undo; delete unwanted files manually. See
[Saving Results](../studio-window/saving.md).

**Why is the Generate button disabled?**
An input requirement isn't met (missing prompt, source image, mask, or target/edit prompts), or the
selected model can't run that operation. See [Operations & Required Inputs](../reference/operations.md).

**Why don't I see a certain option (Style Preset, Steps, …)?**
Provider-specific options appear only when the selected model and operation support them. See
[Extra Providers](../providers/README.md).

**Does it cost money?**
Yes — each operation calls a provider and is billed per that provider's pricing. Higher resolutions,
more inference steps, and upscales generally cost more.
