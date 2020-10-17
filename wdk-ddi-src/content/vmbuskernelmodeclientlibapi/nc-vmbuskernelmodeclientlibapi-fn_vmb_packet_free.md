---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_PACKET_FREE
title: FN_VMB_PACKET_FREE (vmbuskernelmodeclientlibapi.h)
description: The VmbPacketFree function releases a packet allocated by using the VmbPacketAllocate function.
tech.root: netvista
ms.assetid: 9fd81789-09b7-43ac-bcfc-452b1feca9ce
ms.date: 05/22/2018
keywords: ["FN_VMB_PACKET_FREE callback function"]
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
 - FN_VMB_PACKET_FREE
 - vmbuskernelmodeclientlibapi/FN_VMB_PACKET_FREE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_PACKET_FREE
---

# FN_VMB_PACKET_FREE callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketFree</b> function releases a packet allocated by using the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketallocate">VmbPacketAllocate</a> function.

## -parameters

### -param VmbPacket 

 A pointer to an allocated VMBus packet object.

## -prototype

```cpp
//Declaration

FN_VMB_PACKET_FREE FnVmbPacketFree; 

// Definition

VOID FnVmbPacketFree 
(
	__drv_freesMem(Mem)VMBPACKET VmbPacket
)
{...}

```

## -remarks

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketallocate">VmbPacketAllocate</a>