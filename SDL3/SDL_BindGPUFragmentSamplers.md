# SDL_BindGPUFragmentSamplers

Binds sampled textures, and their paired samplers when required, for use on the fragment shader.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
void SDL_BindGPUFragmentSamplers(
    SDL_GPURenderPass *render_pass,
    Uint32 first_slot,
    const SDL_GPUTextureSamplerBinding *texture_sampler_bindings,
    Uint32 num_bindings);
```

## Function Parameters

|                                                                      |                              |                                                  |
| -------------------------------------------------------------------- | ---------------------------- | ------------------------------------------------ |
| [SDL_GPURenderPass](SDL_GPURenderPass) *                             | **render_pass**              | a render pass handle.                            |
| [Uint32](Uint32)                                                     | **first_slot**               | the fragment sampler slot to begin binding from. |
| const [SDL_GPUTextureSamplerBinding](SDL_GPUTextureSamplerBinding) * | **texture_sampler_bindings** | an array of texture/sampler binding structs.     |
| [Uint32](Uint32)                                                     | **num_bindings**             | the number of bindings to bind from the array.   |

## Remarks

The textures must have been created with
[SDL_GPU_TEXTUREUSAGE_SAMPLER](SDL_GPU_TEXTUREUSAGE_SAMPLER). Samplers must
be non-NULL unless the shader resource layout declares the slot with
[SDL_GPU_SHADERSAMPLERTYPE_NONE](SDL_GPU_SHADERSAMPLERTYPE_NONE).

Be sure your shader is set up according to the requirements documented in
[SDL_CreateGPUShader](SDL_CreateGPUShader)().

## Version

This function is available since SDL 3.2.0.

## See Also

- [SDL_CreateGPUShader](SDL_CreateGPUShader)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryGPU](CategoryGPU)
