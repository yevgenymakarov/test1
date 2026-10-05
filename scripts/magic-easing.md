---
title: Magic Easing
description: Magic Easing script for Cavalry
permalink: /scripts/magic-easing/
---

# Magic Easing

> Version 1.2.0
> Supports Cavalry 2.6.0 and later.
> **[Free Download](https://github.com/yevgenymakarov/yevgenymakarov.github.io/releases/download/v1/Magic.Easing.zip "Download the zip file")**
{: .py-3 .bg-gray .rounded-2}

Cavalry supports all standard Robert Penner's easing functions, but not all of them are available through the default Magic Easing menu. This script allows you to use all the built-in easing available in Cavalry, with the option to convert them into Custom expressions, as well as save and load your own Custom easing presets.

<img width="600" alt="Set-Pivot-Screen" src="https://github.com/user-attachments/assets/07bd7e2f-c78e-44e3-a824-00d301672413" />

## User Manual

**Function** - Set the base easing function.

- Quadratic
- Cubic
- Quartic
- Quintic
- Sine
- Circular
- Exponential
- Back
- Elastic
- Bounce

**Type** - Set the easing type.

- Ease In
- Ease Out
- Ease In & Ease Out

**Expression** - Select and apply the saved preset for Custom expressions.

**Value** - Set a value for an arbitrary variable that can be used in a Custom expression. See the Elastic easing preset as an example.

**Apply** - Apply easing to the selected Keyframes. Hold Shift to quickly switch to the next easing function (or the next Custom expression) in the list. Hold Option/Alt to read easing from selected Keyframes; or to load a Custom expression from the selected Keyframe into the edit field.

**Reset** - Reset the selected Keyframes to linear interpolation.

### Context menu items

**Apply Easing** - Apply easing to the selected Keyframes.

**Convert to Custom Expression** - Convert built-in easing function to a Custom expression.

**Reset to Linear Interpolation** - Reset the selected Keyframes to linear interpolation.

**Save New Expression** - Save the current expression as a new preset.

**Current Expression:**

- **Rename** - Rename the currently selected preset.
- **Update Expression** - Update the expression of the currently selected preset.
- **Move Up/Down** - Rearrange the current preset in the list.
- **Delete** - Delete the current preset.

**Backup Expressions** - Export the saved expressions to a JSON file.

**Restore from Backup File** - Import expressions from a backup file. Add to existing expressions or replace them all.

{% include script-install.md file_name="Magic Easing.zip" %}

## Whay's New

The ability to save and load Custom easing presets. The Elastic easing with adjustable frequency are included.

## See Also

- [More Cavalry plugins...](../scripts.md)
