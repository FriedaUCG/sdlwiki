# SDL_GPUComputePipelineResourceLayout

A structure specifying compute pipeline resource layout facts.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef struct SDL_GPUComputePipelineResourceLayout
{
    Uint32 num_samplers; /**< The number of sampler/sampled-texture slots defined in the compute pipeline. */
    Uint32 num_readonly_storage_textures; /**< The number of read-only storage textures defined in the compute pipeline. */
    Uint32 num_readonly_storage_buffers; /**< The number of read-only storage buffers defined in the compute pipeline. */
    Uint32 num_readwrite_storage_textures; /**< The number of read-write storage textures defined in the compute pipeline. */
    Uint32 num_readwrite_storage_buffers; /**< The number of read-write storage buffers defined in the compute pipeline. */
    Uint32 num_uniform_buffers; /**< The number of uniform buffers defined in the compute pipeline. */
    const SDL_GPUSampledTextureSlotDescription *sampled_texture_slots; /**< Optional layout facts for sampler/sampled-texture slots; NULL requests defaults for all sampled texture slots. */
    const SDL_GPUStorageTextureSlotDescription *readonly_storage_texture_slots; /**< Optional layout facts for read-only storage texture slots; NULL requests defaults for all read-only storage texture slots. */
    const SDL_GPUStorageTextureSlotDescription *readwrite_storage_texture_slots; /**< Optional layout facts for read-write storage texture slots; NULL requests defaults for all read-write storage texture slots. */
} SDL_GPUComputePipelineResourceLayout;
```

## Remarks

The resource counts should match the
[SDL_GPUComputePipelineCreateInfo](SDL_GPUComputePipelineCreateInfo) counts
that would be used for compute pipeline creation.

Optional layout arrays describe facts that are not represented by the
resource counts. If an array is NULL, SDL uses the default layout for the
corresponding resource class. If an array is non-NULL, it must contain one
entry for every slot counted by the matching resource count field. The
caller-owned layout and arrays only need to remain valid and unmodified
until
[SDL_CreateGPUComputePipelineWithResourceLayout](SDL_CreateGPUComputePipelineWithResourceLayout)()
returns.

Defaults are 2D filterable-float sampled textures with filtering samplers,
2D
[SDL_GPU_TEXTUREFORMAT_R8G8B8A8_UNORM](SDL_GPU_TEXTUREFORMAT_R8G8B8A8_UNORM)
read-only storage textures for read-only storage texture slots, and 2D
[SDL_GPU_TEXTUREFORMAT_R8G8B8A8_UNORM](SDL_GPU_TEXTUREFORMAT_R8G8B8A8_UNORM)
write-only storage textures for read-write storage texture slots.

These layout facts can describe sampled texture type, sample type, sampler
type, and storage texture format, type, and access. Unsupported
combinations are rejected by compute pipeline creation. Applications can
use [SDL_GPUTextureSupportsFormat](SDL_GPUTextureSupportsFormat)() and
[SDL_GPUTextureSupportsSampleCount](SDL_GPUTextureSupportsSampleCount)()
for preflight, but texture creation and compute pipeline creation remain
authoritative.

Non-filtering sampler layout facts require an all-nearest non-comparison
sampler object when bound. Samplerless layout facts require binding the
texture with a NULL sampler.

## Version

This struct is available since SDL 3.6.0.

## See Also

- [SDL_CreateGPUComputePipelineWithResourceLayout](SDL_CreateGPUComputePipelineWithResourceLayout)

----
[CategoryAPI](CategoryAPI), [CategoryAPIStruct](CategoryAPIStruct), [CategoryGPU](CategoryGPU)
