---
title: Storage Slots
description: Storage Slots script for Cavalry
permalink: /scripts/storage-slots/
---

# Storage Slots

> Version 1.1.0
> Supports Cavalry 2.6.0 and later.
> **[Free Download](https://github.com/yevgenymakarov/yevgenymakarov.github.io/releases/download/v1/Storage.Slots.zip "Download the zip file")**
{: .py-3 .bg-gray .rounded-2 }

This script allows you to preserve Layer or Keyframe selection and restore it later.

<img width="600" alt="Storage Slots" src="../images/storage-slots.png">

## User Manual

**Save** - Store the current Layer or Keyframe selection.

**Load** - Restore the saved Layer or Keyframe selection. By default, only the Layers or Keyframes in the active Composition will be selected. Hold <kbd>Shift</kbd> to select all the Layers or Keyframes stored in the slot across all Compositions.

**Add, subtract or intersect selections:**

- Hold down <kbd>Command/Ctrl</kbd> to add the saved selection to the current selection.
- Hold down <kbd>Option/Alt</kbd> to subtract the saved selection from the current selection.
- Hold down <kbd>Command/Ctrl</kbd> + <kbd>Option/Alt</kbd> to intersect with the current selection.

Reorder slots by dragging by the index number; rename slots, add new slots, clear or remove slots via the context menu.

The data (Layer and Keyframe IDs) is stored in the Cavalry's preferences, not in the Scene file.

{% include script-install.md file_name="Storage Slots.zip" %}

## Whay's New

Support for Cavalry 2.6.0 and later.

## See Also

- [More Cavalry scripts...](../scripts.md)
