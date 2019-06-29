---
UID: NF:ndis.NdisMRegisterScatterGatherDma
title: NdisMRegisterScatterGatherDma function (ndis.h)
description: Bus master miniport drivers call the NdisMRegisterScatterGatherDma function from MiniportInitializeEx to initialize a scatter/gather DMA channel.
old-location: netvista\ndismregisterscattergatherdma.htm
tech.root: netvista
ms.assetid: 90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f
ms.date: 05/02/2018
ms.keywords: NdisMRegisterScatterGatherDma, NdisMRegisterScatterGatherDma function [Network Drivers Starting with Windows Vista], ndis/NdisMRegisterScatterGatherDma, ndis_sgdma_ref_4c89dae9-d6bc-44a5-9b8b-8efcb69ecc75.xml, netvista.ndismregisterscattergatherdma
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Init_RegisterSG, Irql_Gather_DMA_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMRegisterScatterGatherDma
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMRegisterScatterGatherDma function


## -description

> [!CAUTION]
> For ARM and ARM64 processors, we strongly recommend that NDIS driver writers use WDF DMA or WDM DMA instead of NDIS Scatter/Gather DMA. 
>
> For more information about WDF DMA, see [Handling DMA Operations in KMDF Drivers](https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-dma-operations-in-kmdf-drivers).
>
> For more information about WDM DMA, see the DMA-related child topics of [Managing Input/Output for Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-input-output-for-drivers).


Bus master miniport drivers call the 
  <b>NdisMRegisterScatterGatherDma</b> function from 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> to initialize a
  scatter/gather DMA channel.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle that NDIS passed to 
     <i>MiniportInitializeEx</i>.


### -param DmaDescription [in, out]

A pointer to an NDIS_SG_DMA_DESCRIPTION structure. This structure describes the scatter/gather DMA
     properties of the miniport driver. The structure is defined as follows:
     

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _NDIS_SG_DMA_DESCRIPTION {
  NDIS_OBJECT_HEADER  Header;
  ULONG  Flags;
  ULONG  MaximumPhysicalMapping;
  MINIPORT_PROCESS_SG_LIST_HANDLER  ProcessSGListHandler;
  MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE_HANDLER  SharedMemAllocateCompleteHandler;
  ULONG  ScatterGatherListSize;
} NDIS_SG_DMA_DESCRIPTION, *PNDIS_SG_DMA_DESCRIPTION;
 </pre>
</td>
</tr>
</table></span></div>
This structure includes the following members:





#### Header

The 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
       NDIS_SG_DMA_DESCRIPTION structure. Set the 
       <b>Type</b> member of the structure that 
       <b>Header</b> specifies to NDIS_OBJECT_TYPE_SG_DMA_DESCRIPTION, the 
       <b>Revision</b> member to NDIS_SG_DMA_DESCRIPTION_REVISION_1, and the 
       <b>Size</b> member to NDIS_SIZEOF_SG_DMA_DESCRIPTION_REVISION_1.



#### Flags

A set of bit flags that define scatter/gather characteristics. Set this member to the bitwise OR
       of all the required flags. 
       

The NDIS_SG_DMA_64_BIT_ADDRESS flag specifies that the NIC can use 64-bit addressing for DMA
       operations. Otherwise, the NIC uses 32-bit addressing.

Set this member to zero if 64-bit addressing is not required.



#### MaximumPhysicalMapping

The maximum number of bytes that the NIC can transfer in a single DMA operation. NDIS provides
       this value to the hardware abstraction layer (HAL) when allocating a DMA channel, and HAL uses this
       value to determine the maximum number of map registers to reserve for the NIC.



#### ProcessSGListHandler

The 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_process_sg_list">MiniportProcessSGList</a> function
       that NDIS calls when HAL is done building the scatter/gather list.



#### SharedMemAllocateCompleteHandler

The 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_allocate_shared_mem_complete">
       MiniportSharedMemoryAllocateComplete</a> function for miniport drivers that call 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">
       NdisMAllocateSharedMemoryAsyncEx</a>. This field is optional and it should be <b>NULL</b> if the miniport
       driver does not call 
       <b>NdisMAllocateSharedMemoryAsyncEx</b>.



#### ScatterGatherListSize

The size, in bytes, of the memory that is required to hold a scatter/gather list. NDIS sets this
       value before it returns from 
       <b>NdisMRegisterScatterGatherDma</b>. Miniport drivers should use this size to preallocate memory for
       each scatter/gather list.


### -param NdisMiniportDmaHandle [out]

A pointer to a variable that the caller supplies and that NDIS fills with a handle. The handle
     identifies a context area that NDIS uses to manage this DMA resource. The miniport driver passes this
     handle to NDIS in subsequent calls to NDIS that involve this DMA resource.


## -returns



<b>NdisMRegisterScatterGatherDma</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisMRegisterScatterGatherDma</b> successfully allocated resources for bus-master DMA
       operations.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisMRegisterScatterGatherDma</b> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisMRegisterScatterGatherDma</b> failed because the miniport did not specify that it supports NDIS
       6.0 or later versions, or because the miniport driver did not specify that its NIC is a bus-master DMA
       device. A miniport driver specifies its NDIS version when it calls 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">
       NdisMRegisterMiniportDriver</a>. A miniport driver specifies that it supports bus-master DMA
       devices when it calls 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsetminiportattributes">
       NdisMSetMiniportAttributes</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
The current version of NDIS does not support the version specified in the 
       <b>Revision</b> member of the 
       <b>Header</b> structure of 
       <i>DmaDescription</i> .

</td>
</tr>
</table>
 




## -remarks



An NDIS bus-master miniport driver calls 
    <b>NdisMRegisterScatterGatherDma</b> within its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function to
    initialize resources for scatter/gather DMA operations. The 
    <i>DmaDescription</i> parameter that the miniport driver passes to 
    <b>NdisMRegisterScatterGatherDma</b> contains the information that NDIS uses to initialize the
    scatter/gather DMA resources. After 
    <b>NdisMRegisterScatterGatherDma</b> returns, the 
    <b>ScatterGatherListSize</b> member of 
    <i>DmaDescription</i> contains a buffer size that should be sufficient to hold a scatter/gather list.
    Miniport drivers should use this size to preallocate the memory for scatter/gather lists.

The 
    <b>ProcessSGListHandler</b> member in the 
    <i>DmaDescription</i> parameter defines the entry point in the miniport driver for the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_process_sg_list">MiniportProcessSGList</a> function.
    When a miniport driver calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatenetbuffersglist">
    NdisMAllocateNetBufferSGList</a>, NDIS calls HAL to provide the scatter/gather list to the miniport
    driver. HAL calls 
    <i>MiniportProcessSGList</i> after HAL finishes building the scatter/gather list. NDIS can call 
    <i>MiniportProcessSGList</i> outside the context of the call to 
    <b>NdisMAllocateNetBufferSGList</b>.

<b>NdisMRegisterScatterGatherDma</b> returns a pointer to a context area that is opaque to the miniport
    driver. The miniport driver must use this handle in subsequent calls to NDIS scatter/gather DMA
    functions.

Bus-master miniport drivers call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">
    NdisMAllocateSharedMemoryAsyncEx</a> to dynamically allocate shared memory for data transfer
    operations. This call is required when high network traffic causes the miniport driver to run low on the
    shared memory space that the driver allocated during initialization. If 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> returns NDIS_STATUS_PENDING, NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_allocate_shared_mem_complete">
    MiniportSharedMemoryAllocateComplete</a> function to complete the operation at a later time. Miniport
    drivers specify the entry point for the 
    <i>MiniportSharedMemoryAllocateComplete</i> function in the 
    <b>SharedMemAllocateCompleteHandler</b> member of the 
    <i>DmaDescription</i> parameter.

Miniport drivers call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismderegisterscattergatherdma">
    NdisMDeregisterScatterGatherDma</a> function to deallocate the DMA resources that 
    <b>NdisMRegisterScatterGatherDma</b> allocated.




## -see-also


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_process_sg_list">MiniportProcessSGList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_allocate_shared_mem_complete">
   MiniportSharedMemoryAllocateComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-scatter-gather-dma">NDIS Scatter/Gather DMA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatenetbuffersglist">NdisMAllocateNetBufferSGList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">
   NdisMAllocateSharedMemoryAsyncEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismderegisterscattergatherdma">
   NdisMDeregisterScatterGatherDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
