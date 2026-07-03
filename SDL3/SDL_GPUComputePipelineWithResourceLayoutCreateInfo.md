# SDL_GPUComputePipelineWithResourceLayoutCreateInfo

A structure specifying code and a resource layout for creating a compute pipeline object.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef struct SDL_GPUComputePipelineWithResourceLayoutCreateInfo
{
    size_t code_size; /**< The size in bytes of the compute shader code pointed to. */
    const Uint8 *code; /**< A pointer to compute shader code. */
    const char *entrypoint; /**< A pointer to a null-terminated UTF-8 string specifying the entry point function name for the shader. */
    SDL_GPUShaderFormat format; /**< The format of the compute shader code. */
    const SDL_GPUComputePipelineResourceLayout *resource_layout; /**< The compute pipeline resource layout facts to use for this pipeline. */
    Uint32 threadcount_x; /**< The number of threads in the X dimension. This should match the value in the shader. */
    Uint32 threadcount_y; /**< The number of threads in the Y dimension. This should match the value in the shader. */
    Uint32 threadcount_z; /**< The number of threads in the Z dimension. This should match the value in the shader. */
    SDL_PropertiesID props; /**< A properties ID for extensions. Should be 0 if no extensions are needed. */
} SDL_GPUComputePipelineWithResourceLayoutCreateInfo;
```

## Remarks

The `resource_layout` field supplies the compute pipeline resource counts
and optional per-slot layout facts. SDL validates and copies the
caller-owned layout during
[SDL_CreateGPUComputePipelineWithResourceLayout](SDL_CreateGPUComputePipelineWithResourceLayout)(),
so it only needs to remain valid and unmodified until that function
returns.

There are optional properties that can be provided through `props`. These
are the supported properties:

- [`SDL_PROP_GPU_COMPUTEPIPELINE_CREATE_NAME_STRING`](SDL_PROP_GPU_COMPUTEPIPELINE_CREATE_NAME_STRING):
  a name that can be displayed in debugging tools.

## Version

This struct is available since SDL 3.6.0.

## See Also

- [SDL_CreateGPUComputePipelineWithResourceLayout](SDL_CreateGPUComputePipelineWithResourceLayout)
- [SDL_GPUComputePipelineResourceLayout](SDL_GPUComputePipelineResourceLayout)

----
[CategoryAPI](CategoryAPI), [CategoryAPIStruct](CategoryAPIStruct), [CategoryGPU](CategoryGPU)
