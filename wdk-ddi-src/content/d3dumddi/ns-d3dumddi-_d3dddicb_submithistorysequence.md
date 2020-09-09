---
UID: NS:d3dumddi._D3DDDICB_SUBMITCOMMAND
title: _D3DDDICB_SUBMITCOMMAND (d3dumddi.h)
description: The D3DDDICB_SUBMITCOMMAND structure is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
old-location: display\d3dddicb_submitcommand.htm
tech.root: display
ms.assetid: 53D4890A-D075-4DF7-97E6-A8E8A174866B
ms.date: 05/10/2018
keywords: ["D3DDDICB_SUBMITCOMMAND structure"]
ms.keywords: D3DDDICB_SUBMITCOMMAND, D3DDDICB_SUBMITCOMMAND structure [Display Devices], _D3DDDICB_SUBMITCOMMAND, d3dumddi/D3DDDICB_SUBMITCOMMAND, display.d3dddicb_submitcommand
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: D3DDDICB_SUBMITCOMMAND
f1_keywords:
 - _D3DDDICB_SUBMITCOMMAND
 - d3dumddi/_D3DDDICB_SUBMITCOMMAND
 - D3DDDICB_SUBMITCOMMAND
 - d3dumddi/D3DDDICB_SUBMITCOMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDICB_SUBMITCOMMAND
---

# _D3DDDICB_SUBMITCOMMAND structure


## -description

The **D3DDDICB_SUBMITCOMMAND** structure is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.

## -struct-fields

### -field Commands

GPU virtual address to the commands being submitted to the context for execution. This information is provided to the kernel mode driver during command submission and is also used for debugging purposes.

### -field CommandLength

Specifies the length, in bytes, of the commands being submitted to the GPU. This information is provided to the kernel  mode driver during command submission and is also used for debugging purposes.

### -field Flags

An instance of the [**D3DDDICB_SUBMITCOMMANDFLAGS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_submitcommandflags) structure.

### -field BroadcastContextCount

Specifies the number of context these command should be submitted to. This count must be at least 1.

### -field BroadcastContext

Specifies the handle of the context to execute the specified commands.

### -field pPrivateDriverData

Pointer to driver private data to be passed to the kernel mode driver as part of this submission.

### -field PrivateDriverDataSize

Size of the private driver data information being passed. This size must be smaller than the size requested by the kernel mode driver for submission private driver data.

### -field NumPrimaries

Specifies the number of primaries and swapchain back buffers being written to by the submitted commands. This is equal to the number of allocations in the **WrittenPrimaries** array.

### -field WrittenPrimaries

Arrays of handle to the primaries and swapchain back buffers being written to by the submitted commands.

### -field MarkerLogType

A [**D3DDDI_MARKERLOGTYPE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_markerlogtype) enumeration that indicates the type of marker in the Event Tracing for Windows (ETW) log that the user-mode display driver supports.

### -field RenderCBSequence

A unique identifier for each [*pfnRenderCb*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb) function call. Starts at a value of 1 for contexts associated with single-threaded user-mode DDIs and ranges to a value of 0x80000001 for contexts associated with free-threaded user mode DDIs. The user-mode display driver must increment the value for each *pfnRenderCb* call it makes on any engine.

### -field FirstAPISequenceNumberHigh

Used by the driver to pass the context's API sequence number.

### -field CompletedAPISequenceNumberLow0Size

Used by the driver to pass the context's API sequence number.

### -field CompletedAPISequenceNumberLow1Size

Used by the driver to pass the context's API sequence number.

### -field BegunAPISequenceNumberLow0Size

Used by the driver to pass the context's API sequence number.

### -field BegunAPISequenceNumberLow1Size

Used by the driver to pass the context's API sequence number.

### -field pCompletedAPISequenceNumberLow0

A pointer used by the driver to pass the context's API sequence number.

### -field pCompletedAPISequenceNumberLow1

A pointer used by the driver to pass the context's API sequence number.

### -field pBegunAPISequenceNumberLow0

A pointer used by the driver to pass the context's API sequence number.

### -field pBegunAPISequenceNumberLow1

A pointer used by the driver to pass the context's API sequence number.

### -field Reserved

This member is reserved and should be set to zero.

### -field NumHistoryBuffers

The number of history buffers.

### -field HistoryBufferArray

A pointer to the array of history buffers.

### -field hSyncToken

Used in conjunction with pfnReleaseResource; otherwise, set to 0.

### -field pReserved

Set to null.

## -remarks

The [*pfnSubmitCommandCb*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_submitcommandcb) code path no longer provides an allocation list for the user mode driver to provide a list of allocations that will be read and written to during this command. However, it is necessary to synchronize some writes that would not normally be known without the allocation list. For this, a new small allocation list specifically for surfaces which will be written to and used for displaying content. The **WrittenPrimaries** array should be used to provide such allocations.

Despite the name, **WrittenPrimaries** must contain allocations that are considered *SwapChainBackBuffer* allocations according to the runtime in addition to the primaries. This is exposed to the user mode driver by a new flag in [**D3D10_DDI_RESOURCE_MISC_FLAG**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_resource_misc_flag). The runtime will provide the **D3DWDDM2_0DDI_RESOURCE_MISC_DISPLAYABLE_SURFACE** flag to the user mode driver during calls to create a resource or heap that is created as a *FlipEx swapchain* or *primary*. The driver may use this flag to determine all allocations that should be put in the **WrittenPrimaries** list for Microsoft Direct3D 11. Other runtimes have not changed.

If the driver receives a call to [**CreateResource**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource) that has this flag, the allocation should be added to this list on every [*pfnSubmitCommandCb*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_submitcommandcb) call that writes to the surface.

## -see-also

[**D3D10_DDI_RESOURCE_MISC_FLAG**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_resource_misc_flag)

[*pfnRenderCb*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb)

[*pfnSubmitCommandCb*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_submitcommandcb)

