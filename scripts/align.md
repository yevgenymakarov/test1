---
title: Align
description: Align script for Cavalry
permalink: /scripts/align/
---

# Align

> Version 1.1.1
> Supports Cavalry 2.6.0 and later.
> **[Free Download](https://github.com/yevgenymakarov/yevgenymakarov.github.io/releases/download/v1/Align.zip "Download the zip file")**
{: .py-3 .bg-gray .rounded-2 }

This script allows you to align and distribute Shapes, Groups, or drawable Layers (e.g. Null, Falloff).

<img width="600" alt="Align" src="../images/align.png">

## User Manual

**Align**

Align Shapes to the the last selected Layer. Hold down the <kbd>Option/Alt</kbd> key to align Shapes across the Composition.

*This script is context aware depending on whether the Edit Shape Tool is enabled.*

Align Path's Points to the bounding box of all selected Points. Hold down the <kbd>Option/Alt</kbd> key to align Points to the Composition. Hold down the <kbd>Shift</kbd> key to align the Point's handles as well as the Points.

**Distribute**

Distribute with equal spacing between Shapes. Hold down the <kbd>Option/Alt</kbd> key to distribute Shapes across the Composition.

### Context menu items

**Align to Key** - Align Shapes to the last selected Layer.

**Align to Selection** - Align to the bounding box of all selected Shapes.

**Align to Composition** - Align to the edges of the Composition.

**Align to Points** - Align to the selected Points of an Editable Shape.
  
- **Left** - Horizontally align the left edges
- **Center** - Horizontally align the center
- **Right** - Horizontally align the right edges
- **Top** - Vertically align the top edges
- **Middle** - Vertically align the center
- **Bottom** - Vertically align the bottom edges

**Horizontal Distribution**

- **Left** - Horizontally distribute the left edges of the Shapes
- **Center** - Horizontally distribute the center of the Shapes
- **Right** - Horizontally distribute the right edges of the Shapes
- **Auto Spacing** - Distribute with equal spacing between Shapes
- **Spacing...** - Distribute with a specified spacing between Shapes

**Vertical Distribution**

- **Top** - Vertically distribute the top edges of the Shapes
- **Middle** - Vertically distribute the center of the Shapes
- **Bottom** - Vertically distribute the bottom edges of the Shapes
- **Auto Spacing** - Distribute with equal spacing between Shapes
- **Spacing...** - Distribute with a specified spacing between Shapes

{% include script-install.md file_name="Align.zip" %}

## Whay's New

An option for distribution with a specified spacing.

## See Also

- [More Cavalry scripts...](../scripts.md)
