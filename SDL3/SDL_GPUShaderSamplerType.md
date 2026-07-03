# SDL_GPUShaderSamplerType

The sampler binding type used by a shader texture/sampler slot.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef enum SDL_GPUShaderSamplerType
{
    SDL_GPU_SHADERSAMPLERTYPE_FILTERING,
    SDL_GPU_SHADERSAMPLERTYPE_NONFILTERING,
    SDL_GPU_SHADERSAMPLERTYPE_COMPARISON,
    SDL_GPU_SHADERSAMPLERTYPE_NONE
} SDL_GPUShaderSamplerType;
```

## Remarks

This is used by shader resource layout facts to describe the layout of an
existing SDL sampler slot. Filtering layouts accept filtering or
non-filtering non-comparison sampler objects; non-filtering layouts require
all-nearest non-comparison sampler objects; comparison layouts require
comparison sampler objects. NONE layouts have no paired sampler binding;
callers must bind a texture with a NULL sampler for those slots.

## Version

This enum is available since SDL 3.6.0.

## See Also

- [SDL_GPUSampledTextureSlotDescription](SDL_GPUSampledTextureSlotDescription)

----
[CategoryAPI](CategoryAPI), [CategoryAPIEnum](CategoryAPIEnum), [CategoryGPU](CategoryGPU)
