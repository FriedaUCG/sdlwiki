# SDL_GPUShaderResourceLayout

A structure specifying shader resource layout facts.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef struct SDL_GPUShaderResourceLayout
{
    SDL_GPUShaderStage stage; /**< The shader stage this layout applies to. */
    Uint32 num_samplers; /**< The number of sampler/sampled-texture slots defined in the shader. */
    Uint32 num_storage_textures; /**< The number of read-only storage textures defined in the shader. */
    Uint32 num_storage_buffers; /**< The number of read-only storage buffers defined in the shader. */
    Uint32 num_uniform_buffers; /**< The number of uniform buffers defined in the shader. */
    const SDL_GPUSampledTextureSlotDescription *sampled_texture_slots; /**< Optional layout facts for sampler/sampled-texture slots; NULL requests defaults for all sampled texture slots. */
    const SDL_GPUStorageTextureSlotDescription *storage_texture_slots; /**< Optional layout facts for read-only storage texture slots; NULL requests defaults for all storage texture slots. */
} SDL_GPUShaderResourceLayout;
```

## Remarks

The resource counts should match the
[SDL_GPUShaderCreateInfo](SDL_GPUShaderCreateInfo) counts that would be
used for shader creation. The num_storage_textures and num_storage_buffers
fields are read-only graphics storage counts.

Optional layout arrays describe facts that are not represented by the
resource counts. If an array is NULL, SDL uses the default layout for the
corresponding resource class. If an array is non-NULL, it must contain one
entry for every slot counted by the matching resource count field. The
caller-owned layout and arrays only need to remain valid and unmodified
until
[SDL_CreateGPUShaderWithResourceLayout](SDL_CreateGPUShaderWithResourceLayout)()
returns.

Defaults are 2D filterable-float sampled textures with filtering samplers
and 2D
[SDL_GPU_TEXTUREFORMAT_R8G8B8A8_UNORM](SDL_GPU_TEXTUREFORMAT_R8G8B8A8_UNORM)
read-only storage textures.

These layout facts can describe sampled texture type, sample type, sampler
type, and storage texture format, type, and access. Unsupported
combinations are rejected by shader creation. Applications can use
[SDL_GPUTextureSupportsFormat](SDL_GPUTextureSupportsFormat)() and
[SDL_GPUTextureSupportsSampleCount](SDL_GPUTextureSupportsSampleCount)()
for preflight, but texture creation and shader creation remain
authoritative.

Non-filtering sampler layout facts require an all-nearest non-comparison
sampler object when bound. Samplerless layout facts require binding the
texture with a NULL sampler.

## Version

This struct is available since SDL 3.6.0.

## See Also

- [SDL_CreateGPUShaderWithResourceLayout](SDL_CreateGPUShaderWithResourceLayout)

----
[CategoryAPI](CategoryAPI), [CategoryAPIStruct](CategoryAPIStruct), [CategoryGPU](CategoryGPU)
