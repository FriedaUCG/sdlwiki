# SDL_GPUSampleCount

Specifies the sample count of a texture.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef enum SDL_GPUSampleCount
{
    SDL_GPU_SAMPLECOUNT_1,  /**< No multisampling. */
    SDL_GPU_SAMPLECOUNT_2,  /**< MSAA 2x */
    SDL_GPU_SAMPLECOUNT_4,  /**< MSAA 4x */
    SDL_GPU_SAMPLECOUNT_8   /**< MSAA 8x */
} SDL_GPUSampleCount;
```

## Remarks

Used in multisampling. This value primarily applies when the texture is
used as a render target; accepted shader-read paths may also expose
multisampled sampled textures through explicit shader resource layout
facts.

## Version

This enum is available since SDL 3.2.0.

## See Also

- [SDL_CreateGPUTexture](SDL_CreateGPUTexture)
- [SDL_GPUTextureSupportsSampleCount](SDL_GPUTextureSupportsSampleCount)

----
[CategoryAPI](CategoryAPI), [CategoryAPIEnum](CategoryAPIEnum), [CategoryGPU](CategoryGPU)
