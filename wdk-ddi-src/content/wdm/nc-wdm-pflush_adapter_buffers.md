---
UID: NC:wdm.PFLUSH_ADAPTER_BUFFERS
title: PFLUSH_ADAPTER_BUFFERS (wdm.h)
description: The FlushAdapterBuffers routine flushes any data remaining in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer operation.
old-location: kernel\flushadapterbuffers.htm
tech.root: kernel
ms.assetid: cd6cf9af-c600-465c-b8f3-ca0f972780a5
ms.date: 04/30/2018
keywords: ["PFLUSH_ADAPTER_BUFFERS callback function"]
ms.keywords: FlushAdapterBuffers, FlushAdapterBuffers callback function [Kernel-Mode Driver Architecture], PFLUSH_ADAPTER_BUFFERS, PFLUSH_ADAPTER_BUFFERS callback, kdma_97ac2c04-7f7e-495d-b846-d4f0ea27bdac.xml, kernel.flushadapterbuffers, wdm/FlushAdapterBuffers
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFLUSH_ADAPTER_BUFFERS
 - wdm/PFLUSH_ADAPTER_BUFFERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - FlushAdapterBuffers
---

# PFLUSH_ADAPTER_BUFFERS callback function


## -description

The <b>FlushAdapterBuffers</b> routine flushes any data remaining in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer operation.

## -parameters

### -param DmaAdapter 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure returned by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

### -param Mdl 

[in]
Pointer to the MDL that describes the buffer previously passed in the driver's call to <b>MapTransfer</b>.

### -param MapRegisterBase 

[in]
Specifies the map registers allocated for the DMA operation.  The system passes this value  to the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> routine.

### -param CurrentVa 

[in]
Pointer to the current virtual address in the buffer, described by the <i>Mdl</i>, where the I/O operation occurred. This value must be the same as the initial <i>CurrentVa</i> value passed to <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer">MapTransfer</a>.

### -param Length 

[in]
Specifies the length, in bytes, of the buffer.

### -param WriteToDevice 

[in]
Specifies the direction of the DMA transfer operation: <b>TRUE</b> for a transfer from a buffer in system memory to the driver's device.

## -returns

<b>FlushAdapterBuffers</b> returns <b>TRUE</b> if any data remaining in the DMA controller's or bus-master adapter's internal cache has been successfully flushed into system memory or out to the device.

## -remarks

<b>FlushAdapterBuffers</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>.

To ensure that a DMA transfer is complete, every driver that performs DMA operations must call <b>FlushAdapterBuffers</b> before completing the IRP that requested the DMA transfer and before freeing the map registers.

A driver can get the initial <i>CurrentVa</i> for the start of a packet-based DMA transfer by calling <a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlVirtualAddress</a>. However, the value returned is an index into the <i>Mdl</i>, rather than a valid virtual address. If the driver must split a large transfer request into more than one DMA operation, it must update <i>CurrentVa</i> and <i>Length</i> for each DMA operation.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel">AllocateAdapterChannel</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keflushiobuffers">KeFlushIoBuffers</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer">MapTransfer</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlVirtualAddress</a>