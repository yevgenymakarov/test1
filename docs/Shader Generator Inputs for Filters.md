---
layout: default
permalink: /default/
---

## Using Shaders as Generator Inputs to Filters 2

Filters can accept shaders as generator inputs, allowing you to use noise, gradients, or other shader outputs to control filter behaviour.

A generator input is when the entire input's UI is shown as part of your UI (in this example we place it in a different tab).

## Defining a Shader Input Attribute

In your `definitions.json`, add a shader attribute:

```json
{
    "type": "myFilter",
    "superType": "thirdPartyFilter",
    "attributes": {
        "displacementShader": {
            "type": "shaderData",
            "supportedInputNodeTypes": ["shader", "shaderArray"],
            "subUI": true,
            "defaultSubnodeType": "noiseShader
        }
    }
}
```

- `"type": "shaderData"` - Defines a shader input attribute
- `"supportedInputNodeTypes"` - Specifies which node types can connect (typically `["shader", "shaderArray"]`)
- `"subUI": true` - Creates a sub-node UI for the shader
- `"defaultSubnodeType"` - The shader type automatically created (e.g. `"noiseShader"`, `"gradientShader"`)

## Shader Binding Order in SkSL

Shader uniforms bind by **position**, not by name. The binding order is:
1. Your custom shader inputs (in the order defined in attributes)
2. The input image (automatically added as the last shader)

For multi-pass filters, see [Multipass Shaders and Filters](Multipass%20Shaders%20and%20Filters.md) for additional binding considerations.

```glsl
uniform shader displacementShader;  // Your shader input (first)
uniform shader childShader;         // The input being filtered (last)
uniform float amount;

float4 main(float2 coord) {
    // Sample your shader
    float4 shaderColor = displacementShader.eval(coord);

    // Use shader output to control the filter
    float luminance = dot(shaderColor.rgb, float3(0.299, 0.587, 0.114));
    float offset = (luminance - 0.5) * 2.0 * amount;

    // Sample the input image
    return childShader.eval(coord + float2(offset, offset));
}
```

## UI Configuration

Add the shader to your UI with the `nodeInput` control and organise into tabs:

```json
{
    "UI": {
        "tabs": [
            {
                "id": "filter",
                "attributeOrder": ["amount", "direction"]
            },
            {
                "id": "shader",
                "attributeOrder": ["displacementShader"]
            }
        ],
        "controls": {
            "displacementShader": "nodeInput"
        }
    }
}
```

In `strings.json`, define tab names:

```json
{
    "tabs": {
        "filter": "Filter",
        "shader": "Shader"
    }
}
```

## Working Example

See `noiseDisplacementFilter` in the Example Filters directory for a complete implementation.
