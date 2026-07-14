# Providers & API Keys

Every AI Image Studio operation calls an AI provider, so you need a provider selected and a valid
API key.

## Where to configure

`Window > AI Image Studio > Preferences` (Unity Project Settings).

> 📷 **Image — `provider-settings.png`:** The AI Image Studio Preferences page with the provider +
> API key + model fields.

AI Image Studio **shares provider configuration with the AI DevKit core**, so keys you already set
for the base package are reused here.

## What to set

* **AI provider & API key** — the base image providers, plus the add-on's **Stability AI** and
  **Replicate** integrations. See [Extra Providers](../providers/README.md).
* **Default models** — the model used per operation when you don't override it (in the window or via
  `SetModel(...)` in code).

## Notes

* Without a valid key, operations are disabled or report an error.
* Keys are credentials — don't commit them to source control or share project settings that embed
  them.
* Each operation costs money per the provider's pricing (higher resolutions, more inference steps,
  and upscales generally cost more).

## Related

* [Settings](../editor-tools/settings.md) — all Image Studio preferences.
* [Troubleshooting](../support/troubleshooting.md) — key/model errors.
