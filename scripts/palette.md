---
title: Palette
description: Palette script for Cavalry
permalink: /scripts/palette/
---

# Palette

> Version 1.2.0
> Supports Cavalry 2.8.0 and later.
> **[Free Download](https://github.com/yevgenymakarov/yevgenymakarov.github.io/releases/download/v1/Palette.zip "Download the zip file")**
{: .py-3 .bg-gray .rounded-2 }

A mini color palette, synchronized with the Scene Palette.

<img width="600" alt="Palette" src="../images/palette.png">

## User Manual

**Add a color swatch**

- Drag a color swatch from the Color window or from the Color attribute in the Attribute Editor into the script window. To replace an existing color of a swatch, hold down the <kbd>Option/Alt</kbd> key while dragging a swatch.

**Apply a swatch**

- Drag a color swatch directly onto a Shape in the Viewport to set its Fill Color; or drag a color swatch onto a Color attribute in the Attribute Editor.
- With a Shape selected, click a swatch to set a selected Shape's Fill color; hold down the <kbd>Shift</kbd> key to set a selected Shape's Stroke color. Hold down the <kbd>Option/Alt</kbd> key to connect the Scene swatch to the color attribute.
- With a Color attribute selected in the Attribute Editor, click a swatch to set the color; hold down the <kbd>Option/Alt</kbd> key to connect the Scene swatch to the attribute.

### Context menu items

**Copy Hex Color Value** - Copy the swatch's hex color value to the clipboard.

**Paste Color** - Paste a hex color or color name from the clipboard.

**Delete** - Remove the swatch from the palette.

**Import File...** - Search for hex color codes in a text file.

**Load from Library** - List of the Library and Project palettes to load colors from.

**Load from Clipboard** - Read hex colors from the clipboard.

Colors will be appended to the existing ones; hold down the <kbd>Option/Alt</kbd> key to replace all the color swatches; hold down the <kbd>Shift</kbd> key to change the colors while preserving swatch connections.

**Clear** - Remove all swatches from the palette.

{% include script-install.md file_name="Palette.zip" %}

## Whay's New

Synchronization with the Scene Palette.

## See Also

- [More Cavalry scripts...](../scripts.md)
