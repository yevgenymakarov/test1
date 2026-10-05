---
title: Mini Scripts
description: List of small scripts for Cavalry
permalink: /scripts/mini-scripts/
filez: Mini.Scripts.zip
---

# Mini Scripts

Small tools that run without a UI and perform a single action on selected Layers or Attributes.

> **[Free Download]({{ site.xyz }}{{ page.filez }} "Download the zip file")**
{: .py-3 .bg-gray .rounded-2}

## List of Scripts

### Connect Colors to Scene Palette

Connects the Fill and Stroke colors of the selected Shapes to the Scene Palette. For the selected Layers, it finds matching colors or adds new colors to the Scene Palette, and makes connections.

### Connect Multiple Attributes to Selected Layers

Connects multiple selected Attributes to the corresponding Attributes on all selected Layers, for example, Position to Position, Rotation to Rotation, and so on. Select target Layers and select source Attributes in Attribute Editor. Run the script to connect the source Attributes to the target Layers, hold <kbd>Option/Alt</kbd> key to overwrite existing connections.

### Custom Shape from Selection

Creates a Custom Shape with the selected Layers as the Input Shape.

### Points to Path from Selected Layers

Creates a Points to Path and connects the Positions of the selected Layers to the Point Source array.

### Reorder Alphabetically

Rearrange the selected Layers in alphabetical order.

### Reverse Layer Order

Reverse the order of selected Layers in the Scene Window.

### Simple Un-Precompose

For the selected Compositions in the Assets Window, move all Layers from those Compositions to the currently active Composition. It will reconnect the output connections from the Composition, and the Composition will be deleted.

### Solo Selection in Viewport

Add any selected Layers and their child layers to the Quicklist and set the mode to Filter Viewport. A replacement for the built-in "Solo Selection in Viewport" feature, similar to it but with child Layers included.

### Toggle Visibility

Toggle the visibility of the selected Layers. Visible ones become hidden, and hidden ones become visible. Useful for toggling states when comparing layers.

{% include script-install.md file_name="{{ page.filez }}" %}

## See Also

- [More Cavalry plugins...](../scripts.md)
