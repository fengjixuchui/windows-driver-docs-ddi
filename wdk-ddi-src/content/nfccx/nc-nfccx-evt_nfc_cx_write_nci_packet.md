---
UID: NC:nfccx.EVT_NFC_CX_WRITE_NCI_PACKET
title: EVT_NFC_CX_WRITE_NCI_PACKET (nfccx.h)
description: Called by the NFC CX to send a write packet to the client driver.
old-location: nfpdrivers\evtnfccxwritencipacket.htm
tech.root: nfpdrivers
ms.assetid: B734439A-E345-44CC-8FD0-8E38A718A773
ms.date: 02/15/2018
keywords: ["EVT_NFC_CX_WRITE_NCI_PACKET callback function"]
ms.keywords: EVT_NFC_CX_WRITE_NCI_PACKET, EVT_NFC_CX_WRITE_NCI_PACKET callback, EvtNfcCxWriteNciPacket, EvtNfcCxWriteNciPacket callback function [Near-Field Proximity Drivers], nfccx/EvtNfcCxWriteNciPacket, nfpdrivers.evtnfccxwritencipacket
f1_keywords:
 - "nfccx/EvtNfcCxWriteNciPacket"
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: Requires same
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- nfccx.h
api_name:
- EvtNfcCxWriteNciPacket
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_NFC_CX_WRITE_NCI_PACKET callback function


## -description


Called by the NFC CX to send a write packet to the client driver. The request code must match IOCTL_NFCCX_WRITE_PACKET. 


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Request [in]

A handle to a framework request object.


## -remarks



The client driver should not make any blocking calls when handling this function call. Any I/O processing must be handled on a separate thread or work-item (that is, the client driver should immediately return STATUS_PENDING and on completion invoke the completion handler).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

