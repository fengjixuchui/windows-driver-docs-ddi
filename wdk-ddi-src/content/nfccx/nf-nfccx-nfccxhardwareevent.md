---
UID: NF:nfccx.NfcCxHardwareEvent
title: NfcCxHardwareEvent function (nfccx.h)
description: Called by the client driver when a hardware event occurs like D0Entry and D0Exit callbacks to start or stop the device. For drivers that require firmware download on initialization or boot-up, it is recommended to move this call to a separate work item. However, the client driver is responsible for the following.
old-location: nfpdrivers\_nfccxhardwareevent.htm
tech.root: nfpdrivers
ms.assetid: 5D108897-93D9-4C67-9138-86C608AD8C4C
ms.date: 02/15/2018
keywords: ["NfcCxHardwareEvent function"]
ms.keywords: NfcCxHardwareEvent, NfcCxHardwareEvent method [Near-Field Proximity Drivers], nfccx/NfcCxHardwareEvent, nfpdrivers._nfccxhardwareevent
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
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
req.lib: Nfccxstub.lib
req.dll: NfcCx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - NfcCxHardwareEvent
 - nfccx/NfcCxHardwareEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NfcCx.dll
api_name:
 - NfcCxHardwareEvent
---

# NfcCxHardwareEvent function


## -description

Called by the client driver when a hardware event occurs like D0Entry and D0Exit callbacks to start or stop the device. For drivers that require firmware download on initialization or boot-up, it is recommended to move this call to a separate work item. However, the client driver is responsible for the following:
<ul>
<li>The client driver should take an idle power reference before queueing the work item. The reference needs to be dropped when the work item completes. This ensures idle power management doesnt cause the driver to go into D3 while the work-item is running.</li>
<li>The client driver should synchronize the work item with other device callbacks. This is typically achieved by AutomaticSerialization option in <a href="/windows-hardware/drivers/ddi/wdfworkitem/ns-wdfworkitem-_wdf_workitem_config">WDF_WORKITEM_CONFIG</a> and have the parent of the WDFWORKITEM be the WDFDEVICE or by having the work item callback explicitly taking the device lock i.e. <a href="/previous-versions/ff548721(v=vs.85)">WdfObjectAcquireLock</a> on the WDFDEVICE.</li>
<li>If the hardware event call fails from a work-item, the client driver should either restart or unlock the driver to prevent it from being in a bad state. This can be achieved using the Restart or Unload option.</li>
</ul>

## -parameters

### -param Device

A handle to a framework device object.

### -param HardwareEvent

A pointer to an <a href="/windows-hardware/drivers/ddi/nfccx/ns-nfccx-_nfc_cx_hardware_event">NFC_CX_HARDWARE_EVENT</a> structure.

## -returns

If the operation succeeds, the function returns STATUS_SUCCESS.

## -see-also

<a href="/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="/windows-hardware/drivers/nfc/">Near field communication (NFC) design guide</a>