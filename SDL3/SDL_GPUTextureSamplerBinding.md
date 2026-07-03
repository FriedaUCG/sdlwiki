# SDL_GPUTextureSamplerBinding

A structure specifying parameters in a sampler binding call.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef struct SDL_GPUTextureSamplerBinding
{
    SDL_GPUTexture *texture;  /**< The texture to bind. Must have been created with SDL_GPU_TEXTUREUSAGE_SAMPLER. */
    SDL_GPUSampler *sampler;  /**< The sampler to bind. Must be NULL only for layout-declared SDL_GPU_SHADERSAMPLERTYPE_NONE slots. */
} SDL_GPUTextureSamplerBinding;
```

## Version

This struct is available since SDL 3.2.0.

## See Also

- [SDL_BindGPUVertexSamplers](SDL_BindGPUVertexSamplers)
- [SDL_BindGPUFragmentSamplers](SDL_BindGPUFragmentSamplers)
- [SDL_GPUTexture](SDL_GPUTexture)
- [SDL_GPUSampler](SDL_GPUSampler)

----
[CategoryAPI](CategoryAPI), [CategoryAPIStruct](CategoryAPIStruct), [CategoryGPU](CategoryGPU)
