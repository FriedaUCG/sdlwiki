# SDL_GPUTextureSupportsFormat

Determines whether a texture format is supported for a given type and usage.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
bool SDL_GPUTextureSupportsFormat(
    SDL_GPUDevice *device,
    SDL_GPUTextureFormat format,
    SDL_GPUTextureType type,
    SDL_GPUTextureUsageFlags usage);
```

## Function Parameters

|                                                      |            |                                            |
| ---------------------------------------------------- | ---------- | ------------------------------------------ |
| [SDL_GPUDevice](SDL_GPUDevice) *                     | **device** | a GPU context.                             |
| [SDL_GPUTextureFormat](SDL_GPUTextureFormat)         | **format** | the texture format to check.               |
| [SDL_GPUTextureType](SDL_GPUTextureType)             | **type**   | the type of texture (2D, 3D, Cube).        |
| [SDL_GPUTextureUsageFlags](SDL_GPUTextureUsageFlags) | **usage**  | a bitmask of all usage scenarios to check. |

## Return Value

(bool) Returns whether the texture format is supported for this type and
usage.

## Remarks

This is a texture creation and usage capability query. A true result for
[SDL_GPU_TEXTUREUSAGE_SAMPLER](SDL_GPU_TEXTUREUSAGE_SAMPLER) means the
texture can be created for sampled texture usage, but some shader layouts
may still require explicit shader resource layout facts and compatible
sampler state. Signed and unsigned integer sampled textures require
explicit SINT/UINT samplerless layout facts and must be bound with a NULL
sampler; paired sampler layouts are rejected.

This function is not an exact preflight for shader resource layouts,
resource bindings, graphics or compute pipelines, or runtime object state;
final creation remains authoritative.

## Version

This function is available since SDL 3.2.0.

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryGPU](CategoryGPU)
