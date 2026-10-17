---
title: Attribute Tools
description: Attribute Tools script for Cavalry
permalink: /scripts/attribute-tools/
---

# Attribute Tools

> Version 1.1.1
> Supports Cavalry 2.6.0 and later.
> **[Buy Now](https://app.lava.top/products/dfe09a60-fa4f-4587-a228-a240c9460e83 "Go to the store")**
{: .py-3 .bg-gray .rounded-2 }

This script contains various tools for working with Attributes and connections.

<img width="600" alt="Set Pivot" src="../images/attribute-tools.png">

## User Manual

**Swap Attribute Values** - Swap attribute values, input connections, and animation curves between two selected Control Rows (attributes); or for Control Rows with multiple fields (e.g. Position X and Y, or Size W and H), swap the X and Y child attributes.

- If exactly two attributes are selected, it swaps the values between these attributes. Hold <kbd>Option/Alt</kbd> to swap X/Y values within each attribute.
- If one attribute or more than two attributes are selected, it swaps the X/Y values within each attribute.

*For example, you can select two animated attributes in the Scene Window to swap animations. Or, in the Attribute Editor, select the Deformers (or Filters) attributes on the two Layers to swap the lists between the Layers.*

**Control with Null's Position** - Create Nulls and connect the Null's Positions to the selected attributes. Supported for the `double2` and `double3` attribute types. Hold <kbd>Option/Alt</kbd> to use the square shape, or hold <kbd>Shift</kbd> for the circle shape.

**Control with Composition's Time** - Create and connect the Frame Behaviour to the selected attributes. Hold <kbd>Option/Alt</kbd> to connect the Composition's Time directly.

**Add the "Invert" Attribute Expression** - For the selected attributes, add an attribute expression to invert the value. E.g. `-value` or `255 - value` depending on the attribute type. Hold <kbd>Option/Alt</kbd> to also invert the values of selected attributes that do not have input connections.

**Delete Animation and All Connections** - Disconnect all input and output connections and delete animation for the selected attributes. Hold <kbd>Option/Alt</kbd> to delete all connections and animation for the selected Layers.

**Delete Attribute Expressions** - Delete all attribute expressions for the selected attributes. Hold <kbd>Option/Alt</kbd> to delete all attribute expressions for the selected Layers.

**Copy Attribute Connections** - Copy the input connections from the last selected attribute to all selected attributes of the same type. For lists such as Deformers or Filters, hold down the <kbd>Shift</kbd> key to add to existing connections rather than replace the list.

*This option also allows you to copy keyframe animations.*

Hold <kbd>Option/Alt</kbd> to Copy Attribute Reference (remember selected attribute as a reference).
Hold <kbd>Option/Alt</kbd> + <kbd>Cmd/Ctrl</kbd> to Connect Referenced Attribute (create connections from the reference attribute).

### Context menu items

**Swap X/Y Values:**

- **Swap X/Y Values** - Swap the X and Y child attributes within each selected Control Row.
- **Swap Two Attributes Values** - If two Control Rows are selected, swap values, input connections, and animation curves between two selected attributes.

**Copy Attribute Reference:**

- **Copy Attribute Reference** - For a single selected attribute, remember this attribute and Layer as a reference.
- **X, Y, Z, W** - Remember one of the child attributes, e.g. R, G, B, or A.

**Connect Referenced Attribute:**

- **Connect Referenced Attribute** - For selected attributes, create connections from the reference attribute.
- **X, Y, Z, W** - Connect only to one of the child attributes, e.g. R, G, B, or A.

**Copy Input Connections** - Copy the input connections from the last selected Attribute to all selected Attributes of the same type. For lists such as Deformers or Filters, hold down the <kbd>Shift</kbd> key to add to existing connections rather than replace the list.

*This option also allows you to copy keyframe animations.*

**Control with Null:**

- **Control with Null** - Create Nulls and connect the Null's Positions to the selected attributes.
- **Cross, Circle, Square** - Create Nulls with the Shape option set to Cross, Circle, or Square.

**Control with Frame Behaviour:**

- **Control with Frame Behaviour** - Create and connect the Frame Behaviour to the selected attributes.
- **Connect Composition's Time** - Connect the Composition's Time attribute directly.
- **X, Y, Z, W** - Connect only to one of the child attributes, e.g. R, G, B, or A.

**Add Invert Expression:**

- **Add Invert Expression** - For the selected attributes, add an attribute expression to invert the value.
- **Invert Values** - This option also inverts the values of selected attributes that do not have input connections.
- **X, Y, Z, W** - Connect only to one of the child attributes, e.g. R, G, B, or A.

**Delete Animation:**

- **Selected Attributes** - Disconnect all input and output connections and delete animation for the selected attributes.
- **Clear All for Selected Layers** - Delete all connections and animation for the selected Layers.

**Delete Attribute Expressions:**

- **Selected Attributes** - Delete all attribute expressions for the selected attributes.
- **Clear All for Selected Layers** - Delete all attribute expressions for the selected Layers.

**Find Layers with Equal Attribute** - With the attribute or attributes selected in the Attribute Editor, this option will search all Layers in the active Composition, and select Layers that have the identical attributes and their values are equal to the selected ones. Hold down the <kbd>Option/Alt</kbd> key to select only Layers of the same type.

*For example, you can find all Layers with the same stroke Width or Font Size.*

{% include script-install.md file_name="Attribute Tools.zip" %}

## Whay's New

Added a button for the Copy Attribute Connections feature.
Shortcut scripts, for use with hotkeys.

## See Also

- [More Cavalry scripts...](../scripts.md)
