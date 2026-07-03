# SDL_CreateGPUComputePipeline

Creates a pipeline object to be used in a compute workflow.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
SDL_GPUComputePipeline * SDL_CreateGPUComputePipeline(
    SDL_GPUDevice *device,
    const SDL_GPUComputePipelineCreateInfo *createinfo);
```

## Function Parameters

|                                                                              |                |                                                                  |
| ---------------------------------------------------------------------------- | -------------- | ---------------------------------------------------------------- |
| [SDL_GPUDevice](SDL_GPUDevice) *                                             | **device**     | a GPU Context.                                                   |
| const [SDL_GPUComputePipelineCreateInfo](SDL_GPUComputePipelineCreateInfo) * | **createinfo** | a struct describing the state of the compute pipeline to create. |

## Return Value

([SDL_GPUComputePipeline](SDL_GPUComputePipeline) *) Returns a compute
pipeline object on success, or NULL on failure; call
[SDL_GetError](SDL_GetError)() for more information.

## Remarks

Shader resource bindings must be authored to follow a particular order
depending on the shader format.

For SPIR-V shaders, use the following resource sets:

- 0: Sampled textures, followed by read-only storage textures, followed by
  read-only storage buffers
- 1: Read-write storage textures, followed by read-write storage buffers
- 2: Uniform buffers

For DXBC and DXIL shaders, use the following register order:

- (t[n], space0): Sampled textures, followed by read-only storage textures,
  followed by read-only storage buffers
- (u[n], space1): Read-write storage textures, followed by read-write
  storage buffers
- (b[n], space2): Uniform buffers

For MSL/metallib, use the following order:

- [[buffer]]: Uniform buffers, followed by read-only storage buffers,
  followed by read-write storage buffers
- [[texture]]: Sampled textures, followed by read-only storage textures,
  followed by read-write storage textures

For WGSL with the WebGPU backend, shaders must follow SDL's default WebGPU
binding convention and supported resource subset. Use the following
resource groups:

- Group 0: Sampled texture/sampler pairs first, followed by read-only
  storage textures, followed by read-only storage buffers. Sampled texture
  slot N uses bindings 2*N and 2*N+1. Read-only storage texture slot N uses
  binding num_samplers*2+N. Read-only storage buffer slot N uses binding
  num_samplers*2+num_readonly_storage_textures+N.
- Group 1: Read-write storage textures, followed by read-write storage
  buffers. Storage texture slot N uses binding N; read-write storage buffer
  slot N uses binding num_readwrite_storage_textures+N. Storage texture
  slots use write-only layout access by default; explicit layout facts can
  declare write-only or read-write access for supported formats.
- Group 2: Uniform buffers at binding N.

With the default resource layout, WebGPU compute storage textures are
`texture_storage_2d<rgba8unorm, read>` resources created with
[`SDL_GPU_TEXTUREUSAGE_COMPUTE_STORAGE_READ`](SDL_GPU_TEXTUREUSAGE_COMPUTE_STORAGE_READ)
alone and `texture_storage_2d<rgba8unorm, write>` resources created with
[`SDL_GPU_TEXTUREUSAGE_COMPUTE_STORAGE_WRITE`](SDL_GPU_TEXTUREUSAGE_COMPUTE_STORAGE_WRITE)
alone. An
[SDL_GPUComputePipelineResourceLayout](SDL_GPUComputePipelineResourceLayout)
can declare read-only 2D, 2D-array, and 3D `rgba8unorm`, `rgba8snorm`,
`rgba16float`, `rg32float`, `rgba32float`, `rgba8uint`, `rgba16uint`,
`r32uint`, `rgba8sint`, `rgba16sint`, `r32sint`, or `r32float` storage
texture slots. Read-write storage texture layout facts can declare
shader-visible 2D or 3D storage texture slots with write-only access for
the same format set, and read-write access for the same format set except
`rgba8snorm` and `rg32float`. Selected mip/layer backing subresources are
controlled by
[SDL_GPUStorageTextureReadWriteBinding](SDL_GPUStorageTextureReadWriteBinding)
and backend format support; 2D-array write bindings select one layer as a
2D storage texture, while 3D read-write storage texture bindings select a
whole mip level and must use layer 0. WGSL shaders using read-only or
read-write storage texture access must declare `requires
readonly_and_readwrite_storage_textures;`. Resource layout facts can also
declare selected non-default sampled texture and sampler layout while
preserving SDL's group/binding ordering.

There are optional properties that can be provided through `props`. These
are the supported properties:

- [`SDL_PROP_GPU_COMPUTEPIPELINE_CREATE_NAME_STRING`](SDL_PROP_GPU_COMPUTEPIPELINE_CREATE_NAME_STRING):
  a name that can be displayed in debugging tools.

Non-default resource layout facts are supplied through
[SDL_CreateGPUComputePipelineWithResourceLayout](SDL_CreateGPUComputePipelineWithResourceLayout)().

## Version

This function is available since SDL 3.2.0.

## See Also

- [SDL_BindGPUComputePipeline](SDL_BindGPUComputePipeline)
- [SDL_ReleaseGPUComputePipeline](SDL_ReleaseGPUComputePipeline)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryGPU](CategoryGPU)
