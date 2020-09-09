---
UID: NF:netdma.NetDmaDeregisterProvider
title: NetDmaDeregisterProvider function (netdma.h)
description: The NetDmaDeregisterProvider function deregisters a DMA provider.
old-location: netvista\netdmaderegisterprovider.htm
tech.root: netvista
ms.assetid: 8832adbc-c2ab-4742-94a0-4e33d03eaaf1
ms.date: 05/02/2018
keywords: ["NetDmaDeregisterProvider function"]
ms.keywords: NetDmaDeregisterProvider, NetDmaDeregisterProvider function [Network Drivers Starting with Windows Vista], netdma/NetDmaDeregisterProvider, netdma_ref_0fac8a7e-7721-4854-8d0e-6926243ff2ea.xml, netvista.netdmaderegisterprovider
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NetDMA 1.0 drivers in Windows Vista.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NetDmaDeregisterProvider
 - netdma/NetDmaDeregisterProvider
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - netdma.h
api_name:
 - NetDmaDeregisterProvider
---

# NetDmaDeregisterProvider function


## -description

<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaDeregisterProvider</b> function deregisters a DMA provider.

## -parameters

### -param NetDmaProviderHandle 

[in]
A handle that identifies a DMA provider. The DMA provider driver received this handle from the
     NetDMA interface in a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">
     NetDmaRegisterProvider</a> function.

## -returns

None

## -remarks

DMA provider drivers call the 
    <b>NetDmaDeregisterProvider</b> function to deregister a DMA provider that was previously registered by
    calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">
    NetDmaRegisterProvider</a> function.

The DMA provider driver must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstop">NetDmaProviderStop</a> function before it
    deregisters a DMA provider. The DMA provider driver calls 
    <b>NetDmaProviderStop</b> to notify the NetDMA interface that a previously started DMA provider is no
    longer available.

A DMA provider driver typically calls the 
    <b>NetDmaDeregisterProvider</b> function in the context of processing the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a> IRP for the DMA
    provider.

Call 
    <b>NetDmaDeregisterProvider</b> at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstop">NetDmaProviderStop</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">NetDmaRegisterProvider</a>

