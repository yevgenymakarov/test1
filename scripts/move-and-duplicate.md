---
title: Move & Duplicate
description: Move & Duplicate script for Cavalry
permalink: /scripts/move-and-duplicate/
---

# Move & Duplicate

> Version 1.1.0
> Supports Cavalry 2.6.0 and later.
> **[Free Download](https://github.com/yevgenymakarov/yevgenymakarov.github.io/releases/download/v1/Move.and.Duplicate.zip "Download the zip file")**
{: .py-3 .bg-gray .rounded-2 }

This script allows you to precisely move selected Shape Layers or Path's Points by a specified angle and distance, with the option for Shapes to create duplicates and apply additional rotation and scale.

<img width="600" alt="Move & Duplicate" src="../images/move-and-duplicate.png">

## User Manual

*This script is context aware depending on whether the Edit Shape Tool is enabled.*

**Horizontal** - Set the horizontal offset, the x-axis.

**Vertical** - Set the vertical offset, the y-axis.

*The Horizontal and Vertical fields change automatically according to changes in the Distance or Angle fields, and vice versa.*

**Distance** - Set the distance of movement.

**Angle** - Set the angle of movement in degrees.

**Rotation** - Apply rotation to the Shapes when moving and/or duplicating.

**Scale** - Apply scale to the Shapes when moving and/or duplicating.

**Duplicate** - Duplicate the selected Layers.

**Number of Copies** - Number of duplicates to create.

**Reset** - Reset all input fields to the default value.

**Apply** - Move and/or duplicate selected Layers; hold down the <kbd>Option/Alt</kbd> key to place duplicate Layers under the original. Move the selected Points; hold down the <kbd>Option/Alt</kbd> key to move Points in the Shape's local space.

### Context menu items

**Move/Duplicate Shapes** - Move and/or duplicate selected Shapes.

**Move Points** - Move selected Points.

**Set Horizontal from Bounding Box** - Set the Horizontal value equal to the width of the bounding box of the selected Shapes or Points.

**Set Vertical from Bounding Box** - Set the Vertical value equal to the height of the bounding box of the selected Shapes or Points.

**Set Angle from Shape's Rotation** - Set the Angle equal to the rotation of the selected Shape.

**Set Angle from Two Points** - Set the Angle based on the angle of the vector between the two selected Points.

**Set Distance from Two Points** - Set the Distance based on the distance between the two selected Points.

{% include script-install.md file_name="Move and Duplicate.zip" %}

## Whay's New

The ability to move Points of an Editable Path has been added.

## See Also

- [More Cavalry scripts...](../scripts.md)
