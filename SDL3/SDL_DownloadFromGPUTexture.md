# SDL_DownloadFromGPUTexture

Copies data from a texture to a transfer buffer on the GPU timeline.

## Header File

Defined in [<SDL3/SDL_gpu.h>](https://github.com/FriedaUCG/SDL/blob/webgpu/include/SDL3/SDL_gpu.h)

## Syntax

```c
void SDL_DownloadFromGPUTexture(
    SDL_GPUCopyPass *copy_pass,
    const SDL_GPUTextureRegion *source,
    const SDL_GPUTextureTransferInfo *destination);
```

## Function Parameters

|                                                                  |                 |                                                                |
| ---------------------------------------------------------------- | --------------- | -------------------------------------------------------------- |
| [SDL_GPUCopyPass](SDL_GPUCopyPass) *                             | **copy_pass**   | a copy pass handle.                                            |
| const [SDL_GPUTextureRegion](SDL_GPUTextureRegion) *             | **source**      | the source texture region.                                     |
| const [SDL_GPUTextureTransferInfo](SDL_GPUTextureTransferInfo) * | **destination** | the destination transfer buffer with image layout information. |

## Remarks

This data is not guaranteed to be copied until the command buffer fence is
signaled.

For compressed texture formats, `source->x` and `source->y` must be aligned
to the format's block width and height. `source->w` and `source->h` must be
multiples of the block width and height unless the region reaches the edge
of the selected mip level.

## Version

This function is available since SDL 3.2.0.

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryGPU](CategoryGPU)
