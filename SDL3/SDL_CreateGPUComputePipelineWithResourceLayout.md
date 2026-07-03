# SDL_CreateGPUComputePipelineWithResourceLayout

Creates a pipeline object to be used in a compute workflow using resource layout facts.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
SDL_GPUComputePipeline * SDL_CreateGPUComputePipelineWithResourceLayout(
    SDL_GPUDevice *device,
    const SDL_GPUComputePipelineWithResourceLayoutCreateInfo *createinfo);
```

## Function Parameters

|                                                                                                                  |                |                                                                  |
| ---------------------------------------------------------------------------------------------------------------- | -------------- | ---------------------------------------------------------------- |
| [SDL_GPUDevice](SDL_GPUDevice) *                                                                                 | **device**     | a GPU Context.                                                   |
| const [SDL_GPUComputePipelineWithResourceLayoutCreateInfo](SDL_GPUComputePipelineWithResourceLayoutCreateInfo) * | **createinfo** | a struct describing the state of the compute pipeline to create. |

## Return Value

([SDL_GPUComputePipeline](SDL_GPUComputePipeline) *) Returns a compute
pipeline object on success, or NULL on failure; call
[SDL_GetError](SDL_GetError)() for more information.

## Remarks

The resource layout supplies the compute pipeline resource counts and
optional per-slot layout facts.

There are optional properties that can be provided through `props`. These
are the supported properties:

- [`SDL_PROP_GPU_COMPUTEPIPELINE_CREATE_NAME_STRING`](SDL_PROP_GPU_COMPUTEPIPELINE_CREATE_NAME_STRING):
  a name that can be displayed in debugging tools.

## Version

This function is available since SDL 3.6.0.

## See Also

- [SDL_BindGPUComputePipeline](SDL_BindGPUComputePipeline)
- [SDL_CreateGPUComputePipeline](SDL_CreateGPUComputePipeline)
- [SDL_ReleaseGPUComputePipeline](SDL_ReleaseGPUComputePipeline)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryGPU](CategoryGPU)
