# Settings

Open with `Window > AI Image Studio > Preferences` (Unity Project Settings).

> 📷 **Image — `settings.png`:** The AI Image Studio Preferences page with provider/model fields and
> the Scene View button toggles.

## What you can configure

* **Provider & API key** — shared with AI DevKit core; used for every operation. See
  [Providers & API Keys](../setup/providers.md).
* **Default models** — the models used per operation when you don't override them.
* **Scene View overlay** — show/hide individual overlay buttons (Generate, Edit, Upscale, Apply
  Style, Remove BG). See [Scene View Overlay](scene-view-overlay.md).
* **Save behavior** — default output folder / path used when no project folder is active.

## Related windows

Under the same `Window > AI Image Studio` menu:

* **Project Art Profile** — defines the project style used by *Apply Project Style* and Style
  Transfer.
* **Image Categories** — a registry used to categorize and organize generated images.

## Notes

* Keys are credentials — don't commit them to source control.
* Each operation runs against the configured provider/model and costs money per that provider's
  pricing.
