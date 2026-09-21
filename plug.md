---
permalink: /plagins/subpage/
---

# Cavalry Coordinate System Guide

This document explains the coordinate system used in Cavalry's SkSL shaders and filters.

### Fragment Coordinate System

**Coordinate Origin and Axes:**
- **Origin**: `(0, 0)` is at the **bottom-left** corner of the image
- **X-axis**: Increases from left to right (0 to resolution.x)
- **Y-axis**: Increases from bottom to top (0 to resolution.y) 
- **Coordinate Range**: `fragCoord` values are in **pixel coordinates** (0 to resolution.x/y)

**Direct Coordinate Usage:**
- `childShader.eval(coord)` works directly with pixel coordinates
- **No normalization needed** - pass pixel coordinates directly
- Coordinate system is **consistent between passes** in multi-pass filters

**Out-of-Bounds Sampling:**
- Do not use bounds checking for texture sampling
- Out-of-bounds coordinates are handled gracefully
- Bounds checking `eval` calls will likely prevent effects from working properly

### Multi-Pass Coordinate Consistency

**Between Passes:**
- Each pass receives `coord` in the same pixel coordinate system
- `childShader.eval(coord)` returns identical results across passes
- No coordinate transformations needed between passes

**Coordinate Arithmetic:**
- Use **direct coordinate arithmetic**
- Example: `childShader.eval(fragCoord + vector * offset)`
- This approach works reliably across all coordinate ranges