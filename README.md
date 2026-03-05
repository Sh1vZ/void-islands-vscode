# Void Islands VS Code Theme Mapping

This repository defines a source-of-truth palette and maps it into VS Code theme keys for consistent UI and syntax rendering.

## Source-of-truth palette

The canonical palette lives in [`palette.json`](./palette.json), including:

- UI primitives: background, foreground, surfaces, accents, warning, error, success.
- Syntax categories: keyword, string, comment, function, type, constant, variable.
- Interaction states: hover, active, selection.

## Theme mapping notes

- The full key mapping is implemented in [`themes/void-islands-color-theme.json`](./themes/void-islands-color-theme.json).
- Contrast/readability is handled by assigning higher-luminance foregrounds to active text and lower-contrast tones to comments/surfaces.
- Hover, active, and selection states are explicitly mapped using dedicated state colors.

## Intentionally approximated mappings

Some platform-specific tokens do not have a strict 1:1 VS Code equivalent. The following are deliberate approximations:

- **Secondary accent** is reused for `editorCursor.foreground`, `textLink.foreground`, and `list.highlightForeground` to preserve navigational emphasis.
- **Surface elevated** is shared between `editorWidget.background`, `quickInput.background`, and `panel.background` where VS Code separates transient overlays by component.
- **Variable** syntax color is used as the default fallback for broad scopes (`variable`, `meta.object-literal`) where upstream platforms may distinguish locals/fields/globals with dedicated tokens.
- **Success** is mapped to `gitDecoration.addedResourceForeground`; when an upstream platform has multiple success shades, VS Code's single decoration channel requires consolidation.
