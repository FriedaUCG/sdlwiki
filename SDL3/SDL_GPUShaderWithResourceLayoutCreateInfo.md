# SDL_GPUShaderWithResourceLayoutCreateInfo

A structure specifying code and a resource layout for creating a shader object.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef struct SDL_GPUShaderWithResourceLayoutCreateInfo
{
    size_t code_size; /**< The size in bytes of the code pointed to. */
    const Uint8 *code; /**< A pointer to shader code. */
    const char *entrypoint; /**< A pointer to a null-terminated UTF-8 string specifying the entry point function name for the shader. */
    SDL_GPUShaderFormat format; /**< The format of the shader code. */
    const SDL_GPUShaderResourceLayout *resource_layout; /**< The shader resource layout facts to use for this shader. */
    SDL_PropertiesID props; /**< A properties ID for extensions. Should be 0 if no extensions are needed. */
} SDL_GPUShaderWithResourceLayoutCreateInfo;
```

## Remarks

The `resource_layout` field supplies the shader resource counts, stage, and
optional per-slot layout facts. SDL validates and copies the caller-owned
layout during
[SDL_CreateGPUShaderWithResourceLayout](SDL_CreateGPUShaderWithResourceLayout)(),
so it only needs to remain valid and unmodified until that function
returns.

There are optional properties that can be provided through `props`. These
are the supported properties:

- [`SDL_PROP_GPU_SHADER_CREATE_NAME_STRING`](SDL_PROP_GPU_SHADER_CREATE_NAME_STRING):
  a name that can be displayed in debugging tools.

## Version

This struct is available since SDL 3.6.0.

## See Also

- [SDL_CreateGPUShaderWithResourceLayout](SDL_CreateGPUShaderWithResourceLayout)
- [SDL_GPUShaderResourceLayout](SDL_GPUShaderResourceLayout)

----
[CategoryAPI](CategoryAPI), [CategoryAPIStruct](CategoryAPIStruct), [CategoryGPU](CategoryGPU)
