# SDL_GPUStorageTextureSlotDescription

A structure specifying shader resource layout facts for one storage texture slot.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef struct SDL_GPUStorageTextureSlotDescription
{
    SDL_GPUTextureType texture_type;        /**< The texture type used by the storage texture binding. */
    SDL_GPUTextureFormat format;            /**< The texture format used by the storage texture binding. */
    SDL_GPUStorageTextureAccess access;     /**< The storage access used by the storage texture binding. */
} SDL_GPUStorageTextureSlotDescription;
```

## Remarks

Each entry describes one SDL storage texture slot counted by the shader or
compute-pipeline create-info storage texture count for that resource group.

## Version

This struct is available since SDL 3.6.0.

## See Also

- [SDL_GPUShaderResourceLayout](SDL_GPUShaderResourceLayout)
- [SDL_GPUComputePipelineResourceLayout](SDL_GPUComputePipelineResourceLayout)

----
[CategoryAPI](CategoryAPI), [CategoryAPIStruct](CategoryAPIStruct), [CategoryGPU](CategoryGPU)
