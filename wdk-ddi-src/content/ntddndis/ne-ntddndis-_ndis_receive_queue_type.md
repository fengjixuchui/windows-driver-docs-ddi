---
UID: NE:ntddndis._NDIS_RECEIVE_QUEUE_TYPE
title: _NDIS_RECEIVE_QUEUE_TYPE (ntddndis.h)
description: The NDIS_RECEIVE_QUEUE_TYPE enumeration identifies the type of a receive queue.
old-location: netvista\ndis_receive_queue_type.htm
tech.root: netvista
ms.assetid: 8ee28daf-2719-42bc-ab2e-6dcfa7f0e04b
ms.date: 05/02/2018
keywords: ["_NDIS_RECEIVE_QUEUE_TYPE enumeration"]
ms.keywords: "*PNDIS_RECEIVE_QUEUE_TYPE, NDIS_RECEIVE_QUEUE_TYPE, NDIS_RECEIVE_QUEUE_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisReceiveQueueTypeMaximum, NdisReceiveQueueTypeUnspecified, NdisReceiveQueueTypeVMQueue, PNDIS_RECEIVE_QUEUE_TYPE, PNDIS_RECEIVE_QUEUE_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_TYPE, netvista.ndis_receive_queue_type, ntddndis/NDIS_RECEIVE_QUEUE_TYPE, ntddndis/NdisReceiveQueueTypeMaximum, ntddndis/NdisReceiveQueueTypeUnspecified, ntddndis/NdisReceiveQueueTypeVMQueue, ntddndis/PNDIS_RECEIVE_QUEUE_TYPE, virtual_machine_queue_ref_b51e0e9c-353e-40a1-b466-3136db1fcdd9.xml"
f1_keywords:
 - "ntddndis/NDIS_RECEIVE_QUEUE_TYPE"
 - "NDIS_RECEIVE_QUEUE_TYPE"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- Ntddndis.h
api_name:
- NDIS_RECEIVE_QUEUE_TYPE
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_TYPE, *PNDIS_RECEIVE_QUEUE_TYPE
---

# _NDIS_RECEIVE_QUEUE_TYPE enumeration


## -description


The <b>NDIS_RECEIVE_QUEUE_TYPE</b> enumeration identifies the type of a receive queue.


## -enum-fields




### -field NdisReceiveQueueTypeUnspecified

The receive queue type is not specified.


### -field NdisReceiveQueueTypeVMQueue

This value specifies a virtual machine (VM) receive queue.


### -field NdisReceiveQueueTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The NDIS_RECEIVE_QUEUE_TYPE enumeration is used in the 
    <b>QueueType</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_parameters">
    NDIS_RECEIVE_QUEUE_PARAMETERS</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_info">
    NDIS_RECEIVE_QUEUE_INFO</a> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_info">NDIS_RECEIVE_QUEUE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_parameters">NDIS_RECEIVE_QUEUE_PARAMETERS</a>
 

 

