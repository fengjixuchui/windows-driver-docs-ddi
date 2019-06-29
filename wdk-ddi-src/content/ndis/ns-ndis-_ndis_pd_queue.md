---
UID: NS:ndis._NDIS_PD_QUEUE
title: _NDIS_PD_QUEUE (ndis.h)
description: This structure represents a provider's receive or transmit queue.
old-location: netvista\ndis_pd_queue.htm
tech.root: netvista
ms.assetid: 5405A9A6-243B-4E80-85D7-46C6FCC8339F
ms.date: 05/02/2018
ms.keywords: NDIS_PD_QUEUE, NDIS_PD_QUEUE structure [Network Drivers Starting with Windows Vista], PNDIS_PD_QUEUE, PNDIS_PD_QUEUE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_QUEUE, ndis/NDIS_PD_QUEUE, ndis/PNDIS_PD_QUEUE, netvista.ndis_pd_queue
ms.topic: struct
req.header: ndis.h
req.include-header: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ndis.h
api_name:
- NDIS_PD_QUEUE
product:
- Windows
targetos: Windows
req.typenames: NDIS_PD_QUEUE
---

# _NDIS_PD_QUEUE structure


## -description


This structure represents a provider's receive or transmit queue


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_QUEUE</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_PD_TRANSMIT_QUEUE</b> or <b>NDIS_OBJECT_TYPE_PD_RECEIVE_QUEUE</b></li>
<li><b>Revision</b> = <b>NDIS_PD_QUEUE_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_QUEUE_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0.


### -field Dispatch

See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_pd_queue_dispatch">NDIS_PD_QUEUE_DISPATCH</a>.


### -field PDPlatformReserved

Reserved for the platform.


### -field PDClientReserved

Reserved for the client.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>
 

 

