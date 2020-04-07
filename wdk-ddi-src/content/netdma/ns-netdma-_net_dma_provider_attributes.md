---
UID: NS:netdma._NET_DMA_PROVIDER_ATTRIBUTES
title: _NET_DMA_PROVIDER_ATTRIBUTES (netdma.h)
description: The NET_DMA_PROVIDER_ATTRIBUTES structure specifies the configuration attributes for a NetDMA provider.
old-location: netvista\net_dma_provider_attributes.htm
tech.root: netvista
ms.assetid: 7b5a7e9e-b10b-4c94-80b1-172cd9f0c9ca
ms.date: 05/02/2018
keywords: ["_NET_DMA_PROVIDER_ATTRIBUTES structure"]
ms.keywords: "*PNET_DMA_PROVIDER_ATTRIBUTES, NET_DMA_PROVIDER_ATTRIBUTES, NET_DMA_PROVIDER_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNET_DMA_PROVIDER_ATTRIBUTES, PNET_DMA_PROVIDER_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NET_DMA_PROVIDER_ATTRIBUTES, netdma/NET_DMA_PROVIDER_ATTRIBUTES, netdma/PNET_DMA_PROVIDER_ATTRIBUTES, netdma_ref_a00d6e7c-6712-49c9-9c64-d200e96074c5.xml, netvista.net_dma_provider_attributes"
f1_keywords:
 - "netdma/NET_DMA_PROVIDER_ATTRIBUTES"
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 2.0 drivers in Windows Server 2008. Supported for NetDMA 1.1   drivers in Windows Server 2008. Supported for NetDMA 1.0 drivers in Windows Server 2008 and Windows   Vista.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- netdma.h
api_name:
- NET_DMA_PROVIDER_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_ATTRIBUTES, *PNET_DMA_PROVIDER_ATTRIBUTES
---

# _NET_DMA_PROVIDER_ATTRIBUTES structure


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The NET_DMA_PROVIDER_ATTRIBUTES structure specifies the configuration attributes for a NetDMA
  provider.


## -struct-fields




### -field MajorHwVersion

The major version number of the DMA provider hardware.


### -field MinorHwVersion

The minor version number of the DMA provider hardware.


### -field Size

The size, in bytes, of this NET_DMA_PROVIDER_ATTRIBUTES structure. Set this member to 
     sizeof(NET_DMA_PROVIDER_ATTRIBUTES).


### -field Flags

Reserved for DMA provider attributes flags. Set this member to zero.


### -field VendorId

A vendor identifier (ID) that uniquely identifies the vendor that created the DMA engine. This
     vendor ID is specified in the device's PCI configuration space. For more information about the vendor
     ID, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI
     Devices</a>.


### -field DmaChannelCount

The number of DMA channels that the DMA provider supports. This number can differ from the 
     <b>MaxDmaChannelCount</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_characteristics">
     NET_DMA_PROVIDER_CHARACTERISTICS</a> structure that defines the maximum number of DMA channels that
     this type of DMA provider can support.


### -field MaximumTransferSize

The maximum DMA transfer size, in bytes, that the DMA provider can support. This value can must be
     4 KB or greater.


### -field MaximumAddressSpace

The largest physical address that the DMA engine can support.


## -remarks



To start a DMA provider, the DMA provider driver supplies a NET_DMA_PROVIDER_ATTRIBUTES structure at
    the 
    <i>ProviderAttributes</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstart">NetDmaProviderStart</a> function.

A DMA provider driver initializes a DMA engine and starts a DMA provider while handling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> IRP.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_characteristics">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstart">NetDmaProviderStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstop">NetDmaProviderStop</a>
 

 

