---
UID: NF:poscx.PosCxPutPendingEventMemory
title: PosCxPutPendingEventMemory function (poscx.h)
description: PosCxPutPendingEventMemory tries to delegate a memory object containing the event data to a waiting caller. If the target caller does not have a read request waiting, the new event is added to the designated event queue (control or data).
old-location: pos\poscxputpendingeventmemory.htm
tech.root: pos
ms.assetid: DF9CA4A8-4B2A-4DED-9514-422AC5E0940D
ms.date: 02/23/2018
keywords: ["PosCxPutPendingEventMemory function"]
ms.keywords: PosCxPutPendingEventMemory, PosCxPutPendingEventMemory function, pos.poscxputpendingeventmemory, poscx/PosCxPutPendingEventMemory
req.header: poscx.h
req.include-header: Poscx.h
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
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
f1_keywords:
 - PosCxPutPendingEventMemory
 - poscx/PosCxPutPendingEventMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxPutPendingEventMemory
---

# PosCxPutPendingEventMemory function


## -description

PosCxPutPendingEventMemory tries to delegate a memory object containing the 
      event data to a waiting caller. 
      If the target caller does not have a read request waiting, the new event is added to 
      the designated event queue (control or data).

## -parameters

### -param device 

[in]
A handle to a framework device object that represents the device.

### -param deviceInterfaceTag 

[in]
The device interface associated with the event.  By default, only
          file objects that have the same tag will receive this event.

### -param eventMemory 

[in]
The new event data memory object that contains both the point-of-service event header 
          and the data. PosCx will take over ownership of this passed in memory object.

### -param eventAttr 

[in]
The event attributes.

## -returns

Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The event was created and delegated to a waiting caller,
          or the event was discarded because there is no device owner.
</td>
</tr>
<tr>
<td><b>STATUS_PENDING</b></td>
<td>The event was queued because no caller is currently waiting.</td>
</tr>
<tr>
<td><b>STATUS_DEVICE_NOT_READY</b></td>
<td>The PosCx library was not successfully initialized.</td>
</tr>
<tr>
<td>Other errors</td>
<td>Other appropriate failure error codes.</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_attributes">POS_CX_EVENT_ATTRIBUTES</a>

