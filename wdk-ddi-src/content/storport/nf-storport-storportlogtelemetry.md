---
UID: NF:storport.StorPortLogTelemetry
title: StorPortLogTelemetry function (storport.h)
description: The StorPortLogTelemetry routine logs a miniport telemetry event to help diagnose or collect any useful information.
old-location: storage\storportlogtelemetry.htm
tech.root: storage
ms.assetid: 3B32F31C-3850-43D4-9C6E-40D35B8AF4D4
ms.date: 03/29/2018
keywords: ["StorPortLogTelemetry function"]
ms.keywords: StorPortLogTelemetry, StorPortLogTelemetry routine [Storage Devices], storage.storportlogtelemetry, storport/StorPortLogTelemetry
f1_keywords:
 - "storport/StorPortLogTelemetry"
 - "StorPortLogTelemetry"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
req.irql: Any
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortLogTelemetry
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: 19H1
---

# StorPortLogTelemetry function

## -description

The **StorPortLogTelemetry** routine logs a miniport telemetry event to help diagnose or collect any useful information. The miniport can log eight general purpose name-value pairs and a buffer that has maximum length of 4KB, as well as several event related fields that are defined in structure [STORPORT_TELEMETRY_EVENT](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_storport_telemetry_event).

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param StorAddress [in, optional]

The storage unit device address. This parameter is NULL for adapter devices.

### -param Event [in]

Pointer to the STORPORT_TELEMETRY_EVENT structure that contains the telemetry data payload.

## -returns

**StorPortLogTelemetry** returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
<b>	EventBufferLength</b> is larger than <b>EVENT_BUFFER_MAX_LENGTH</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer to one of the parameters is NULL or the EventBufferLength/EventBuffer in Event structure not matching.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The telemetry event data have been successfully logged.

</td>
</tr>
</table>

## -remarks

If any parameter in Event structure is not named, Event->ParameterNameX == NULL, the routine will set the corresponding parameter value to 0.

If miniport has no payload to fill in Event->EventBuffer, it should set Event->EventBufferLength = 0, as well as Event->EventBuffer = NULL.

## -see-also

[STORPORT_TELEMETRY_EVENT](ns-storport-_storport_telemetry_event.md)

[StorPortLogTelemetryEx](nf-storport-storportlogtelemetryex.md)
