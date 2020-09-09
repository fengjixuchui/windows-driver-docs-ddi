---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_ALLOCATE
title: FN_VMB_PACKET_ALLOCATE (vmbuskernelmodeclientlibapi.h)
description: The VmbPacketAllocate function allocates a packet from the channel's lookaside list.
tech.root: netvista
ms.assetid: de59b2ba-33eb-41f2-a4ce-6be46e88dfd7
ms.date: 05/22/2018
keywords: ["FN_VMB_PACKET_ALLOCATE callback function"]
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - FN_VMB_PACKET_ALLOCATE
 - vmbuskernelmodeclientlibapi/FN_VMB_PACKET_ALLOCATE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_PACKET_ALLOCATE
---

# FN_VMB_PACKET_ALLOCATE callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketAllocate</b> function allocates a packet from the channel's lookaside list.

## -parameters

### -param Channel

A handle for a channel.

## -returns

<b>VmbPacketAllocate</b> returns a pointer to an allocated VMBus packet object or null.

## -prototype

```cpp
//Declaration

FN_VMB_PACKET_ALLOCATE FnVmbPacketAllocate; 

// Definition

VMBPACKET FnVmbPacketAllocate 
(
	VMBCHANNEL Channel
)
{...}

```

## -remarks

The default completion routine of a packet automatically releases the packet.
If the packet is not sent or if the completion routine is changed, the
client should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketfree">VmbPacketFree</a> function to release the packet.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketfree">VmbPacketFree</a>

