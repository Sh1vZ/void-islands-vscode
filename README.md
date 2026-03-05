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
# Void Islands Theme

**Void Islands Theme** is a high-contrast dark VS Code color theme with cool neon accents for readability in low-light environments.

## Features

- Deep pitch-black editor and workbench backgrounds
- Clear syntax groups for comments, keywords, strings, functions, and types
- Designed for long coding sessions with minimal glare

## Installation

### From a `.vsix` package

1. Build/package the extension:
   ```bash
   npx @vscode/vsce package
   ```
2. In VS Code, open the Command Palette (`Ctrl/Cmd+Shift+P`)
3. Run **Extensions: Install from VSIX...**
4. Select the generated `.vsix` file

### Development mode

1. Clone this repository
2. Open it in VS Code
3. Press `F5` to launch an Extension Development Host
4. In the new window, open Command Palette and run **Preferences: Color Theme**
5. Select **Pitchblack Island**

## Usage

- Open Command Palette (`Ctrl/Cmd+Shift+P`)
- Run **Preferences: Color Theme**
- Choose **Pitchblack Island**

## Preview

Add screenshots under `images/` and reference them here, for example:

```md
![Editor preview](images/pitchblack-island-preview.png)
```

