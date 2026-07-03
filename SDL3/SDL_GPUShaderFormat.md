# SDL_GPUShaderFormat

Specifies the format of shader code.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
typedef Uint32 SDL_GPUShaderFormat;

#define SDL_GPU_SHADERFORMAT_INVALID  0
#define SDL_GPU_SHADERFORMAT_PRIVATE  (1u << 0) /**< Shaders for NDA'd platforms. */
#define SDL_GPU_SHADERFORMAT_SPIRV    (1u << 1) /**< SPIR-V shaders for Vulkan. */
#define SDL_GPU_SHADERFORMAT_DXBC     (1u << 2) /**< DXBC SM5_1 shaders for D3D12. */
#define SDL_GPU_SHADERFORMAT_DXIL     (1u << 3) /**< DXIL SM6_0 shaders for D3D12. */
#define SDL_GPU_SHADERFORMAT_MSL      (1u << 4) /**< MSL shaders for Metal. */
#define SDL_GPU_SHADERFORMAT_METALLIB (1u << 5) /**< Precompiled metallib shaders for Metal. */
#define SDL_GPU_SHADERFORMAT_WGSL     (1u << 6) /**< WGSL shaders for the WebGPU backend. Shaders must follow SDL's documented WebGPU binding convention and supported resource subset. */
```

## Remarks

Each format corresponds to a specific backend that accepts it.

## Version

This datatype is available since SDL 3.2.0.

## See Also

- [SDL_CreateGPUShader](SDL_CreateGPUShader)

----
[CategoryAPI](CategoryAPI), [CategoryAPIDatatype](CategoryAPIDatatype), [CategoryGPU](CategoryGPU)
