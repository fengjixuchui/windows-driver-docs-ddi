---
UID: NS:ksmedia.__unnamed_struct_108
title: KSPROPERTY_TUNER_SCAN_STATUS_S (ksmedia.h)
description: The KSPROPERTY_TUNER_SCAN_STATUS_S structure describes status for a scanning operation.
old-location: stream\ksproperty_tuner_scan_status_s.htm
tech.root: stream
ms.assetid: b09373ef-7b65-46f7-b5b7-a6dcecf0166c
ms.date: 04/30/2019
ms.keywords: "*PKSPROPERTY_TUNER_SCAN_STATUS_S, KSPROPERTY_TUNER_SCAN_STATUS_S, KSPROPERTY_TUNER_SCAN_STATUS_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_SCAN_STATUS_S, PKSPROPERTY_TUNER_SCAN_STATUS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_SCAN_STATUS_S, ksmedia/PKSPROPERTY_TUNER_SCAN_STATUS_S, stream.ksproperty_tuner_scan_status_s, vidcapstruct_70c7d301-6c91-4955-bcaa-67cad29cb15a.xml"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSPROPERTY_TUNER_SCAN_STATUS_S"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
- ksmedia.h
api_name:
- KSPROPERTY_TUNER_SCAN_STATUS_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_SCAN_STATUS_S, *PKSPROPERTY_TUNER_SCAN_STATUS_S
---

# KSPROPERTY_TUNER_SCAN_STATUS_S structure


## -description


The KSPROPERTY_TUNER_SCAN_STATUS_S structure describes status for a scanning operation.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field LockStatus

One of the following values from the <b>TunerLockType</b> enumeration that indicates the lock status of the scanning operation.

<table>
<tr>
<th>Status</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>Tuner_LockType_None</b> (0x00)

</td>
<td>
The tuner is not locked on a signal. The driver can return this value at the end of a scan.

</td>
</tr>
<tr>
<td>
<b>Tuner_LockType_Within_Scan_Sensing_Range</b> (0x01)

</td>
<td>
The signal is nearby; however, the driver cannot report the exact frequency.

</td>
</tr>
<tr>
<td>
<b>Tuner_LockType_Locked</b> (0x02)

</td>
<td>
A fine-tune signal lock was established. The driver can return this value at the end of a scan.

</td>
</tr>
</table>
 


### -field CurrentFrequency

The current locked-in frequency, in Hz, on the tuning device. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksevent-tuner-initiate-scan">KSEVENT_TUNER_INITIATE_SCAN</a>



<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-scan-status">KSPROPERTY_TUNER_SCAN_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-tuner">PROPSETID_TUNER</a>
 

 

