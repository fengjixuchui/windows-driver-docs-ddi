---
UID: NS:ucxroothub._ROOTHUB_30PORT_INFO
title: _ROOTHUB_30PORT_INFO (ucxroothub.h)
description: Provides information about a USB 3.0 root hub port. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function.
old-location: buses\_roothub_30port_info.htm
tech.root: usbref
ms.assetid: 5C39C0EB-AC7F-44E5-95EB-9F067DBE0801
ms.date: 05/07/2018
ms.keywords: "*PROOTHUB_30PORT_INFO, P_ROOTHUB_30PORT_INFO, P_ROOTHUB_30PORT_INFO structure pointer [Buses], ROOTHUB_30PORT_INFO, ROOTHUB_30PORT_INFO structure [Buses], _ROOTHUB_30PORT_INFO, buses._roothub_30port_info, ucxroothub/P_ROOTHUB_30PORT_INFO, ucxroothub/_ROOTHUB_30PORT_INFO"
ms.topic: struct
f1_keywords:
 - "ucxroothub/ROOTHUB_30PORT_INFO"
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- ucxroothub.h
api_name:
- ROOTHUB_30PORT_INFO
product:
- Windows
targetos: Windows
req.typenames: ROOTHUB_30PORT_INFO, *PROOTHUB_30PORT_INFO
---

# _ROOTHUB_30PORT_INFO structure


## -description


Provides information about a USB 3.0 root hub port. This structure is passed by UCX in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxroothub/nc-ucxroothub-evt_ucx_roothub_get_30port_info">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a> callback function.


## -struct-fields




### -field PortNumber

The USB 3.0 port number connected to the root hub.


### -field MinorRevision

Revision number.


### -field HubDepth

The hub depth limit.


### -field Removable

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxroothub/ne-ucxroothub-_tristate">TRISTATE</a> value that indicates if the port is removable. 


### -field DebugCapable

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxroothub/ne-ucxroothub-_tristate">TRISTATE</a> value that indicates if the port is debug capable. 

