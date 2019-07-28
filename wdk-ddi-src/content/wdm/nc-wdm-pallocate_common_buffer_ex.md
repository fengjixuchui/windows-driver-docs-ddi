---
UID: NC:wdm.PALLOCATE_COMMON_BUFFER_EX
title: PALLOCATE_COMMON_BUFFER_EX (wdm.h)
description: The AllocateCommonBufferEx routine allocates memory for a common buffer and maps this memory so that it can be accessed both by the processor and by a device that performs DMA operations.
old-location: kernel\allocatecommonbufferex.htm
tech.root: kernel
ms.assetid: F7456BD7-689C-4534-B6F0-028A5359A2E9
ms.date: 04/30/2018
ms.keywords: AllocateCommonBufferEx, AllocateCommonBufferEx callback function [Kernel-Mode Driver Architecture], PALLOCATE_COMMON_BUFFER_EX, PALLOCATE_COMMON_BUFFER_EX callback, kernel.allocatecommonbufferex, wdm/AllocateCommonBufferEx
ms.topic: callback
f1_keywords:
 - "wdm/AllocateCommonBufferEx"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- AllocateCommonBufferEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PALLOCATE_COMMON_BUFFER_EX callback function


## -description


The <b>AllocateCommonBufferEx</b> routine allocates memory for a common buffer and maps this memory so that it can be accessed both by the processor and by a device that performs DMA operations.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine.


### -param MaximumAddress [in, optional]

A pointer to a variable that contains the maximum logical address for the common buffer. This parameter indicates that the buffer should be allocated from memory below this address. This parameter is optional and can be specified as NULL to indicate that there is no maximum address.


### -param Length [in]

The size, in bytes, of the common buffer that is to be allocated for the DMA operation.


### -param LogicalAddress [out]

A pointer to a variable into which this routine writes the logical address that the device can use to access the common buffer. The DMA device should use this logical address instead of the physical address that is returned by a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmgetphysicaladdress">MmGetPhysicalAddress</a>.


### -param CacheEnabled [in]

Whether the routine must enable or disable cached memory in the common buffer that is to be allocated. If TRUE, caching is enabled. If FALSE, it is disabled. If the hardware platform does not enforce cache coherency for DMA operations, then pass FALSE. For information about this parameter on ARM or ARM 64-based processors target computers, see Remarks.


### -param PreferredNode [in]

The preferred NUMA node from which the memory is to be allocated. If N is the number of NUMA nodes in a multiprocessor system, <i>PreferredNode</i> is a number in the range 0 to N–1. For a one-processor system or a non-NUMA multiprocessor system, set <i>PreferredNode</i> to zero.


## -returns



<b>AllocateCommonBufferEx</b> returns the virtual address of the memory allocated for the common buffer. If the buffer  cannot be allocated, NULL is returned.




## -remarks



<b>AllocateCommonBufferEx</b>
           is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
          <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the Version member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>AllocateCommonBufferEx</b> is an extended version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pallocate_common_buffer">AllocateCommonBuffer</a> routine. The following list summarizes the features that are available only in the extended version:

<ul>
<li>The caller can specify a maximum logical address for the common buffer that is to be allocated.</li>
<li>The caller can specify a preferred NUMA node in which the common buffer is to be allocated.</li>
</ul>
On computers with ARM or ARM 64-based processors, cache settings in the system ACPI have a higher precedence than the <i>CacheEnabled</i> parameter value passed by the driver. If the <b>ACPI _CCA</b>  method indicates that the device is not cache coherent, the operating system disables caching even if the driver allocates cached memory with <i>CacheEnabled</i> set to TRUE.

On computers with ARM or ARM 64-based processors, the operating system allocates an uncached common buffer as Device Memory. For more information about the buffer, see sections A3.5.1, and A3.5.6 from the <a href="https://go.microsoft.com/fwlink/p/?linkid=853904">ARMv7 Architecture Reference Manual</a>.  

The processor does not permit misaligned access to Device Memory. Your driver must always access data from the common buffer by using naturally-aligned operations. Most kernel routines do not accept Device Memory as input parameters. For example, a network driver cannot pass Device Memory into <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismindicatereceivenetbufferlists">NdisMIndicateReceiveNetBufferLists</a>. If your driver needs to pass data from a DMA common buffer to a kernel routine, either allocate the buffer with <i>CacheEnabled</i> set to TRUE or copy the data from the uncached common buffer into a temporary pool allocation.

For more information about DMA operations that use a common buffer, see the following topics:

<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-common-buffers">Using Common Buffers</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-buffer-bus-master-dma">Using Common-Buffer Bus-Master DMA</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-buffer-system-dma">Using Common-Buffer System DMA</a>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pallocate_common_buffer">AllocateCommonBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmgetphysicaladdress">MmGetPhysicalAddress</a>
 

 

