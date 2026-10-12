---
title: Swap Color
description: Swap Color script for Cavalry
permalink: /scripts/swap-color/
---

# Swap Color

> Version 1.1.0
> Supports Cavalry 2.6.0 and later.
> **[Buy Now](https://app.lava.top/products/aa840626-24ba-4f96-81fa-8748a5433554 "Go to the store")**
{: .py-3 .bg-gray .rounded-2 }

This script allows you to search the Scene for a specific color and replace it with another one.

<img width="600" alt="Swap Color" src="../images/swap-color.png">

## User Manual

**Find** - Set the color to replace.

**Replace** - Set the color to replace with.

**Fill** - Replace the Fill color in such layers as Shapes, "Sub-Mesh", "Fill", "Color Material Override", and "Apply Text Material".

**Stroke** - Replace the Stroke color in such layers as Shapes, "Sub-Mesh", "Stroke", "Stroke Duplicator", and "Apply Text Material".

**Background Color** - Replace the Composition's Background color.

**Array** - Replace colors in arrays, this includes "Color Array", "Multi-Point Gradient Shader", and JavaScript or SkSL layer dynamic attributes.

**Gradient** - Replace colors in gradients, includes Stroke gradient, "Gradient Shader", "Gradient Map", "Color Blend", "Index to Color", and "Number Range to Color".

**Null** - Replace the Custom Color of viewport drawable Layers, such as "Null", "Camera Guide", "Falloff", Forge Dynamics Fields, and Particle Emitters and Modifiers.

*If none of the above options are selected, the color will be replaced in all found color attributes.*

**Hidden Layers** - Search and replace color in Layers that are hidden or inactive.

**Third Party Plugins** - Search and replace color in Layers from third party developers. The attribute type restriction above may not work for these layers.

**Active Composition** - Restrict the scope of the search to the Layers in the active Composition.

**Selected Layers** - Restrict the scope of the search to the selected Layers.

*If neither Active Composition nor Selected Layers is selected, all layers in the Scene will be searched.*

**Max. Deviation** - The maximum value by which the color value (each RGBA separately) can differ from the specified Find color to still be considered equal.

**Alpha** - If this option is unchecked, the Alpha of the color is ignored, and search and replace is performed by RGB values only.

**Use Color Swatch** - Create a color swatch in the Scene palette and make a connection to the replaced attributes.

**Replace** - Search and replace color. Hold down <kbd>Option/Alt</kbd> to select the matching Layers without changing the color. Only the layers that are in the active Composition will be selected.

### Context menu items

**Replace Color** - Search and replace color.

**Find & Select Layers** - Select the matching Layers without replacing the color.

**Invert Colors** - Invert colors in the Layers. All found colors will be inverted regardless of the Find option.

**Swap Find and Replace Colors** - Swap the colors in the Find and Replace fields.

**Set Find from Clipboard** - Paste a color (Hex, W3C color name) from the clipboard into the Find field.

**Set Replace from Clipboard** - Paste a color (Hex, W3C color name) from the clipboard into the Replace field.

**Show/Hide Options** - Allows you to hide options.

### Drag and drop

Drag and drop a color swatch into the script window to set it to the Find color. Hold <kbd>Shift</kbd> to set it to the Replace color, or drop it directly onto the Replace color swatch.

### Notes

- The script searches and replaces the color in the Layer attributes, it has no effect on pasted SVGs or images.
- The animated color attributes and attributes with an input connection will not be changed.

{% include script-install.md file_name="Swap Color.zip" %}

## Whay's New

Support for Cavalry 2.6.0 and later.

## See Also

- [More Cavalry scripts...](../scripts.md)
