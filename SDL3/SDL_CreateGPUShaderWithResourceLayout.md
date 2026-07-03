# SDL_CreateGPUShaderWithResourceLayout

Creates a shader to be used when creating a graphics pipeline using resource layout facts.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
SDL_GPUShader * SDL_CreateGPUShaderWithResourceLayout(
    SDL_GPUDevice *device,
    const SDL_GPUShaderWithResourceLayoutCreateInfo *createinfo);
```

## Function Parameters

|                                                                                                |                |                                                        |
| ---------------------------------------------------------------------------------------------- | -------------- | ------------------------------------------------------ |
| [SDL_GPUDevice](SDL_GPUDevice) *                                                               | **device**     | a GPU Context.                                         |
| const [SDL_GPUShaderWithResourceLayoutCreateInfo](SDL_GPUShaderWithResourceLayoutCreateInfo) * | **createinfo** | a struct describing the state of the shader to create. |

## Return Value

([SDL_GPUShader](SDL_GPUShader) *) Returns a shader object on success, or
NULL on failure; call [SDL_GetError](SDL_GetError)() for more information.

## Remarks

The resource layout supplies the shader stage, resource counts, and
optional per-slot layout facts.

There are optional properties that can be provided through `props`. These
are the supported properties:

- [`SDL_PROP_GPU_SHADER_CREATE_NAME_STRING`](SDL_PROP_GPU_SHADER_CREATE_NAME_STRING):
  a name that can be displayed in debugging tools.

## Version

This function is available since SDL 3.6.0.

## See Also

- [SDL_CreateGPUGraphicsPipeline](SDL_CreateGPUGraphicsPipeline)
- [SDL_CreateGPUShader](SDL_CreateGPUShader)
- [SDL_ReleaseGPUShader](SDL_ReleaseGPUShader)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryGPU](CategoryGPU)
