---
UID: NS:1394._IRB_REQ_SEND_PHY_PACKET
title: _IRB_REQ_SEND_PHY_PACKET (1394.h)
description: This structure contains the fields necessary to carry out a SendPhyPacket request.
old-location: ieee\irb_req_send_phy_packet.htm
tech.root: IEEE
ms.assetid: 32C96259-3A35-4BD3-96A4-A9F2A5FDAB99
ms.date: 02/15/2018
ms.keywords: 1394/IRB_REQ_SEND_PHY_PACKET, IEEE.irb_req_send_phy_packet, IRB_REQ_SEND_PHY_PACKET, IRB_REQ_SEND_PHY_PACKET structure [Buses], _IRB_REQ_SEND_PHY_PACKET
ms.topic: struct
f1_keywords:
 - "1394/IRB_REQ_SEND_PHY_PACKET"
req.header: 1394.h
req.include-header: 
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
- 1394.h
api_name:
- IRB_REQ_SEND_PHY_PACKET
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_SEND_PHY_PACKET
---

# _IRB_REQ_SEND_PHY_PACKET structure


## -description


This structure contains the fields necessary to carry out a SendPhyPacket request.


## -struct-fields




### -field Flags

Specifies any nondefault settings for this operation. Set to ASYNC_FLAGS_NO_STATUS to always return success from the send PHY packet operation, regardless of whether the send PHY packet succeeds or fails.


### -field GenerationCount

Specifies the bus reset generation as known by the device driver that submits this request. If the specified generation count does not match the actual generation of the bus, this request is returned with a status of STATUS_INVALID_GENERATION.


### -field PhyPacket

Specifies the 64-bit PHY packet that is sent to the 1394 bus.


## -remarks



If successful, the new 1394 bus driver (1394ohci.sys) sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS. If <b>u.SendPhyPacket.GenerationCount</b> does not match the current bus generation count, the new 1394 bus driver sets <b>Irp->IoStatus.Status</b> to STATUS_INVALID_GENERATION



