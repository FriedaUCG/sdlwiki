# SDL_GPUStorageTextureAccess

The storage access used by a shader storage texture slot.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef enum SDL_GPUStorageTextureAccess
{
    SDL_GPU_STORAGETEXTUREACCESS_READ_ONLY,
    SDL_GPU_STORAGETEXTUREACCESS_WRITE_ONLY,
    SDL_GPU_STORAGETEXTUREACCESS_READ_WRITE
} SDL_GPUStorageTextureAccess;
```

## Remarks

This is used by shader resource layout facts to describe the layout of an
existing SDL storage texture slot.

## Version

This enum is available since SDL 3.6.0.

## See Also

- [SDL_GPUStorageTextureSlotDescription](SDL_GPUStorageTextureSlotDescription)

----
[CategoryAPI](CategoryAPI), [CategoryAPIEnum](CategoryAPIEnum), [CategoryGPU](CategoryGPU)
