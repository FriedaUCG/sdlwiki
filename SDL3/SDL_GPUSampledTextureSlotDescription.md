# SDL_GPUSampledTextureSlotDescription

A structure specifying shader resource layout facts for one sampled texture/sampler slot.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef struct SDL_GPUSampledTextureSlotDescription
{
    SDL_GPUTextureType texture_type;              /**< The texture type used by the sampled texture binding. */
    SDL_GPUShaderTextureSampleType sample_type;   /**< The sample type used by the sampled texture binding. */
    SDL_GPUShaderSamplerType sampler_type;        /**< The sampler binding type used by the paired sampler binding, or SDL_GPU_SHADERSAMPLERTYPE_NONE for samplerless slots. */
} SDL_GPUSampledTextureSlotDescription;
```

## Remarks

Each entry describes SDL sampler slot N counted by the shader or
compute-pipeline create-info `num_samplers` field. Most sampler types
describe a paired sampled texture and sampler binding. For
[SDL_GPU_SHADERSAMPLERTYPE_NONE](SDL_GPU_SHADERSAMPLERTYPE_NONE), the slot
has only a sampled texture binding and no paired sampler binding.

## Version

This struct is available since SDL 3.6.0.

## See Also

- [SDL_GPUShaderResourceLayout](SDL_GPUShaderResourceLayout)
- [SDL_GPUComputePipelineResourceLayout](SDL_GPUComputePipelineResourceLayout)

----
[CategoryAPI](CategoryAPI), [CategoryAPIStruct](CategoryAPIStruct), [CategoryGPU](CategoryGPU)
