# Troubleshooting

## The AI Image Studio menu doesn't appear

* Confirm the package imported without compile errors (check the Console). The AI DevKit core is
  bundled, so you don't install it separately.
* The window lives at `Window > AI Image Studio > AI Image Studio`.

## Generate button is disabled

An input requirement isn't met, or the selected model can't run the operation. Check
[Operations & Required Inputs](../reference/operations.md) — e.g. Inpaint/Erase need a painted mask;
Recolor/Replace Object need both a target and an edit prompt.

## "Invalid API key" / model errors

* Set a valid key in `Window > AI Image Studio > Preferences`.
* Make sure the selected model belongs to a provider you've configured.
* See [Providers & API Keys](../setup/providers.md).

## "Texture is not readable"

The source image's import settings block CPU access. Select the texture, enable **Read/Write** in
the importer (or use a source produced by Image Studio), and retry.

## A provider option is missing

Options like **Style Preset**, **Inference Steps**, **Grow Mask**, and **Creativity** are shown only
when the selected model/operation supports them. Switch to a compatible model. See
[Extra Providers](../providers/README.md).

## The result didn't get saved / I can't undo it

Generated images are real project assets and are **not** covered by Unity's Undo. If you chose
**Save As**, check the folder you selected; to remove a result, delete the asset manually. See
[Saving Results](../studio-window/saving.md).

## Scene View buttons are missing

Enable them in Preferences (Scene View section), and make sure the selected GameObject has a
`SpriteRenderer`, `UI.Image`, or `UI.RawImage`. See [Scene View Overlay](../editor-tools/scene-view-overlay.md).

## Still stuck?

Check the base AI DevKit troubleshooting docs, or reach out on the Glitch9 Discord.
