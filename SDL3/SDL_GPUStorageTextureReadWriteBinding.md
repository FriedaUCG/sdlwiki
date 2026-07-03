# SDL_GPUStorageTextureReadWriteBinding

A structure specifying parameters related to binding textures in a compute pass.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef struct SDL_GPUStorageTextureReadWriteBinding
{
    SDL_GPUTexture *texture;  /**< The texture to bind. Must have been created with SDL_GPU_TEXTUREUSAGE_COMPUTE_STORAGE_WRITE or SDL_GPU_TEXTUREUSAGE_COMPUTE_STORAGE_SIMULTANEOUS_READ_WRITE. */
    Uint32 mip_level;         /**< The mip level index to bind. */
    Uint32 layer;             /**< The layer index to bind. For 2D-array textures this binds one selected layer as a 2D storage texture. For 3D storage textures this must be 0; the whole selected mip level is bound. */
    bool cycle;               /**< true cycles the texture if it is already bound. */
    Uint8 padding1;
    Uint8 padding2;
    Uint8 padding3;
} SDL_GPUStorageTextureReadWriteBinding;
```

## Version

This struct is available since SDL 3.2.0.

## See Also

- [SDL_BeginGPUComputePass](SDL_BeginGPUComputePass)

----
[CategoryAPI](CategoryAPI), [CategoryAPIStruct](CategoryAPIStruct), [CategoryGPU](CategoryGPU)
