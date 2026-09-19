# Multi-Pass Shader/Filter Support

Cavalry supports multi-pass shaders and filters, allowing third-party developers to create complex effects that require multiple rendering passes.

## Overview

Multi-pass rendering allows you to:
- Create effects that require multiple sequential operations (e.g., 2-pass blur, bloom effects)
- Access the result of previous passes as input to subsequent passes

## Usage

### Single-Pass (Backwards Compatible)

The existing single-pass format continues to work:

```json
{
    "type": "myShader",
    "superType": "thirdPartyShader",
    "skslFile": "myShader.sksl",
    ...
}
```

### Multi-Pass

For multi-pass effects, use the `passes` array instead of `skslFile`:

```json
{
    "type": "myMultiPassEffect",
    "superType": "thirdPartyFilter",
    "passes": [
        {
            "skslFile": "pass1.sksl",
            "blendMode": "srcOver"
        },
        {
            "skslFile": "pass2.sksl",
            "blendMode": "multiply"
        }
    ],
    ...
}
```

## Pass Definition

Each pass in the `passes` array can have:

- `skslFile` (required): Path to the SkSL file for this pass
- `uniforms` (optional): Array of attribute names that this pass needs
  - Only these uniforms will be bound to the pass
  - If omitted, all attributes are bound (backwards compatible)
  - Use this to avoid "uniform not found" errors when passes don't need all attributes
- `clearColor` (optional): Clear color [r, g, b, a] for this pass

## How It Works

1. Each pass is rendered sequentially
2. The result of each pass is available as a child shader to the next pass
3. The final pass result becomes the output of the effect
4. All uniform attributes are available to all passes

## Example: 2-Pass Blur

```json
{
    "author": "myCompany",
    "type": "twoPassBlur",
    "superType": "thirdPartyFilter",
    "attributes": {
        "blurRadius": {
            "type": "double",
            "default": 10,
            "min": 0,
            "max": 100
        }
    },
    "passes": [
        {
            "skslFile": "horizontalBlur.sksl",
            "uniforms": ["blurRadius"]
        },
        {
            "skslFile": "verticalBlur.sksl", 
            "uniforms": ["blurRadius"]
        }
    ],
    "triggers": {
        "out": ["blurRadius"]
    },
    "UI": {
        "attributeOrder": ["blurRadius"]
    }
}
```

## Shader Access in SkSL

In your SkSL files, you can access:
- Uniforms defined in attributes (e.g., `uniform float blurRadius;`)
- The automatic `uniform float2 resolution;`
- Child shaders from previous passes

### Shader Binding Order

Shader uniforms bind by **position**, not by name. The binding order is:

1. **shaderData attributes** (in the order defined in your attributes)
2. **childShader** (result from previous pass, or input image for pass 1)
3. **original** (original input image, only for pass 2+)

**Critical:** If your filter has `shaderData` attributes, you must declare them in **every pass** to maintain correct binding order, even if unused in that pass.

```glsl
// Example: Pass 1 of a filter with a shaderData attribute called "noiseShader"
uniform shader noiseShader;   // Must declare even if unused, to maintain binding order
uniform shader childShader;   // The input image (pass 1) or previous pass result
uniform float2 resolution;

float4 main(float2 coord) {
    // noiseShader is declared but not used in this pass
    float4 color = childShader.eval(coord);
    return color;
}
```

### Original Image Access (Filters Only)

For multi-pass **Filter** effects, you can access the original input image in passes 2 and beyond:

```glsl
uniform shader noiseShader;  // Your shaderData attributes first (if any)
uniform shader childShader;  // Result from previous pass
uniform shader original;     // Original input image (pass 2+ only)
uniform float2 resolution;

float4 main(float2 coord) {
    // Sample the processed result from previous pass
    float4 processed = childShader.eval(coord);

    // Sample the original unprocessed image
    float4 orig = original.eval(coord);

    // Use both for advanced effects
    return mix(processed, orig, 0.5);
}
```

**Important Notes:**
- `original` is only available for **pass 2 and beyond** in multi-pass filters
- `original` is always the **last shader uniform** in the binding order
- If you need access to the original image in pass 2+, you must declare `uniform shader original;`
- This feature is **not available** for `Shaders`