# SDL_GPUShaderTextureSampleType

The sampled texture type used by a shader texture/sampler slot.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef enum SDL_GPUShaderTextureSampleType
{
    SDL_GPU_SHADERTEXTURESAMPLETYPE_FILTERABLE_FLOAT,
    SDL_GPU_SHADERTEXTURESAMPLETYPE_UNFILTERABLE_FLOAT,
    SDL_GPU_SHADERTEXTURESAMPLETYPE_DEPTH,
    SDL_GPU_SHADERTEXTURESAMPLETYPE_SINT,
    SDL_GPU_SHADERTEXTURESAMPLETYPE_UINT,
    SDL_GPU_SHADERTEXTURESAMPLETYPE_MULTISAMPLED_UNFILTERABLE_FLOAT,
    SDL_GPU_SHADERTEXTURESAMPLETYPE_MULTISAMPLED_DEPTH
} SDL_GPUShaderTextureSampleType;
```

## Remarks

This is used by shader resource layout facts to describe the layout of an
existing SDL sampler slot. It does not add new shader resource slots; the
corresponding create-info resource counts still define how many slots
exist.

The MULTISAMPLED_* values describe shader-visible multisampled texture
slots. They require
[SDL_GPU_SHADERSAMPLERTYPE_NONE](SDL_GPU_SHADERSAMPLERTYPE_NONE) layout
facts and 2D textures whose backing texture sample count is greater than 1.

## Version

This enum is available since SDL 3.6.0.

## See Also

- [SDL_GPUSampledTextureSlotDescription](SDL_GPUSampledTextureSlotDescription)

----
[CategoryAPI](CategoryAPI), [CategoryAPIEnum](CategoryAPIEnum), [CategoryGPU](CategoryGPU)
