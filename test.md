---
title: PAGE TITLE
description: front matter description tag
permalink: /multipass/
categories: CATEGORY-1 CATEGORY-2
tags: aaa ccc
xyz: testxyz
---

# Test Page

{% include plugin-install.md file_name="Path Visualizer Deformer.zip" %}

{% include script-install.md file_name="Swap Color.zip" %}


## Entry Point

[foo](coordinate-system.md)
[foo](sub-test/suubb.md)
[foo](plug.md)

***

### inst TAG

{{ site.inst }}

### Automatic Uniforms

{% for page in site.pages %}
- [{{ page.name }}]({{ page.url | absolute_url }})
{% endfor %}

Cavalry automatically provides certain uniforms to your shaders. They're only available if you declare them:

#### Resolution

The `resolution` uniform contains the layer size in pixels:

```glsl
uniform float2 resolution;
```

#### Rect Centre (Filters only)

The `rectCentre` uniform contains the centre point of the draw rectangle; if your filter is not working correctly in a Duplicator, it's likely you need to account for this value (the Duplicator offsets the draw rectangles):

```glsl
uniform float2 rectCentre;
```

To properly handle coordinate transformations when the rect centre is not at origin, subtract `rectCentre` from your fragment coordinates:

```glsl
float2 normalizedCoord = fragCoord - rectCentre;
```

### Padding

When generating effects that expand the area of a layer, you can use the setup.js script to connect your radius/amount Attribute to a "padding" Attribute. An Attribute Expression can also be set for multiples (e.g. blurRadius * sigma), this value will then be used to increase the layer bounds.

Setting `autoPadding` to true on the layer will ask Cavalry to automatically detect a "radius" or "amount" Attribute. These can be double2 or doubles. Cavalry will then directly apply these values as the amount to expand the bounding box in each direction. For simple cases when the amount/radius is measured in pixels, this is an easy automated route. For more complex situations, use the above method of connecting to the "padding" Attribute and using an Attribute Expression to run whatever logic you need.

### Shader Inputs

Filters can use shaders as inputs to control their behaviour.  for details.

### Multi-pass

Multi-pass Shaders and Filters are supported, see for details.

## Loop Constraints

* **Fixed loop bounds only**: SkSL requires constant expressions for loop initialisation and bounds.
* **Maximum 127 iterations**: Use `for (int i = -63; i <= 63; i++)` and `break` to skip iterations.
* **No uniform-based loops**: You cannot use `for (int i = 0; i < uniformValue; i++)` — unrolling is mandatory.

## Missing Functions

SkSL lacks many standard functions and operators:

* ❌ `abs(int)`: Use `int absI = i < 0 ? -i : i;`
* ❌ `min(int)`, `max(int)`: Use ternary expressions (`a < b ? a : b`)
* ❌ `%` (mod operator): Use a float version manually
* ❌ `atan2`, `dFdx`, `dFdy`: Not available

## Alternatives

Techniques like derivative estimation can be used instead of dFdx and dFdy:

```glsl
float dx = sample(img, uv + float2(1.0/resolution.x, 0)).r - 
           sample(img, uv - float2(1.0/resolution.x, 0)).r;
float dy = sample(img, uv + float2(0, 1.0/resolution.y)).r - 
           sample(img, uv - float2(0, 1.0/resolution.y)).r;
```

Supersampling can also be used if anti-aliasing is required.

Here's an example of Adaptive Super-Sampling with improved edge detection for dark colors:

## Color Range

* **Cavalry uses 0–255**: Color values in your definitions are 8-bit.
* **SkSL uses 0–1**: Cavalry automatically converts values before sending to shaders.
* **Write SkSL using normalized (0–1) values**: No manual conversion needed.

## Data Types & Uniforms

* Uniforms must be `float` — no `int`, `bool`, or `enum` types allowed.
* Enums, flags, and ints are passed as `float` and must be cast in the shader to the type you require (`int(x)`).
* User-defined `struct`s cannot be used as uniforms.
* All GLSL reserved words are reserved in SkSL too (e.g., `sample`, `mod`, `input`).

## Texture Sampling

* Use `inputShader.eval(coord)` for explicit sampling.
* Manual mip control (`textureLod`) is not supported.

## Math Notes

* `fract(x)` is available and can simulate `mod` for floats:

  ```glsl
  float modf(float a, float b) { return a - b * floor(a / b); }
  ```
* Use `sign(x)` for polarity detection.

## Shader Complexity

* SkSL shaders are compiled to bytecode — keep shaders small and simple.
* Avoid nested conditionals and complex loops.
* Limit to one `for` loop per function when possible.

## Naming and Compatibility

* Reserved names: avoid GLSL and SkSL keywords (e.g., `sample`, `input`, `mod`).
* SkSL prefers `half` over `float` for performance — use `half` unless higher precision is needed.

## Utility Snippets

```glsl
int absI(int x) { return x < 0 ? -x : x; }
int minI(int a, int b) { return a < b ? a : b; }
int maxI(int a, int b) { return a > b ? a : b; }
float modf(float a, float b) { return a - b * floor(a / b); }
```
