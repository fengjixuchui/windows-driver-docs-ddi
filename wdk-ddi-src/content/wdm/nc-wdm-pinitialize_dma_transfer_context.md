---
UID: NC:wdm.PINITIALIZE_DMA_TRANSFER_CONTEXT
title: PINITIALIZE_DMA_TRANSFER_CONTEXT (wdm.h)
description: The InitializeDmaTransferContext routine initializes an opaque DMA transfer context that is used to track pending allocations of DMA resources.
old-location: kernel\initializedmatransfercontext.htm
tech.root: kernel
ms.assetid: 5E9D08FD-1F81-462F-90AA-7C4BFFB5F864
ms.date: 04/30/2018
keywords: ["PINITIALIZE_DMA_TRANSFER_CONTEXT callback function"]
ms.keywords: InitializeDmaTransferContext, InitializeDmaTransferContext callback function [Kernel-Mode Driver Architecture], PINITIALIZE_DMA_TRANSFER_CONTEXT, PINITIALIZE_DMA_TRANSFER_CONTEXT callback, kernel.initializedmatransfercontext, wdm/InitializeDmaTransferContext
f1_keywords:
 - "wdm/InitializeDmaTransferContext"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- InitializeDmaTransferContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# PINITIALIZE_DMA_TRANSFER_CONTEXT callback function


## -description


The <b>InitializeDmaTransferContext</b> routine initializes an opaque DMA transfer context that is used to track pending allocations of DMA resources.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine.


### -param DmaTransferContext [out]

A pointer to a caller-allocated buffer into which <b>InitializeDmaTransferContext</b> writes the initial values for the DMA transfer context.  This context is opaque to the caller. The caller must allocate a buffer that is large enough to contain the DMA transfer context. The size, in bytes, of this context is specified by the <b>DMA_TRANSFER_CONTEXT_SIZE_V1</b> constant in the Wdm.h header file.


## -returns



<b>InitializeDmaTransferContext</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETERS</b></dt>
</dl>
</td>
<td width="60%">
This routine failed due to invalid parameter values passed by the caller.

</td>
</tr>
</table>
 




## -remarks



<b>InitializeDmaTransferContext</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

An initialized DMA transfer context must be supplied as a parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a> routine. Each of these routines writes information about the requested DMA resource allocation to the DMA transfer context. This information is opaque to the caller. To cancel a pending allocation request, the caller must supply the DMA transfer context for the request to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcancel_adapter_channel">CancelAdapterChannel</a> routine.

The DMA transfer context that is supplied to <b>AllocateAdapterChannelEx</b>, <b>GetScatterGatherListEx</b>, or <b>BuildScatterGatherListEx</b> must be unique across all adapter allocation requests.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list_ex">BuildScatterGatherListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcancel_adapter_channel">CancelAdapterChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>
 

 

