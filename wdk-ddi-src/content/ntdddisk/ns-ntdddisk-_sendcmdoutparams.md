---
UID: NS:ntdddisk._SENDCMDOUTPARAMS
title: _SENDCMDOUTPARAMS (ntdddisk.h)
description: The SENDCMDOUTPARAMS structure is used in conjunction with the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.
old-location: storage\sendcmdoutparams.htm
tech.root: storage
ms.assetid: e9fb6d5c-258c-46eb-ba3a-3f10008fdf68
ms.date: 03/29/2018
keywords: ["SENDCMDOUTPARAMS structure"]
ms.keywords: "*LPSENDCMDOUTPARAMS, *PSENDCMDOUTPARAMS, LPSENDCMDOUTPARAMS, LPSENDCMDOUTPARAMS structure pointer [Storage Devices], PSENDCMDOUTPARAMS, PSENDCMDOUTPARAMS structure pointer [Storage Devices], SENDCMDOUTPARAMS, SENDCMDOUTPARAMS structure [Storage Devices], _SENDCMDOUTPARAMS, ntdddisk/LPSENDCMDOUTPARAMS, ntdddisk/PSENDCMDOUTPARAMS, ntdddisk/SENDCMDOUTPARAMS, storage.sendcmdoutparams, structs-IDE_d1a70016-0e77-465a-9368-665975369bdc.xml"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
req.typenames: SENDCMDOUTPARAMS, *PSENDCMDOUTPARAMS, *LPSENDCMDOUTPARAMS
f1_keywords:
 - _SENDCMDOUTPARAMS
 - ntdddisk/_SENDCMDOUTPARAMS
 - PSENDCMDOUTPARAMS
 - ntdddisk/PSENDCMDOUTPARAMS
 - SENDCMDOUTPARAMS
 - ntdddisk/SENDCMDOUTPARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - SENDCMDOUTPARAMS
---

# _SENDCMDOUTPARAMS structure


## -description

The SENDCMDOUTPARAMS structure is used in conjunction with the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566206(v=vs.85)">SMART_SEND_DRIVE_COMMAND</a> request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.

## -struct-fields

### -field cBufferSize

Contains the size in bytes of the buffer pointed to by <b>bBuffer</b>.

### -field DriverStatus

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_driverstatus">DRIVERSTATUS</a> structure that indicates the driver status.

### -field bBuffer

Pointer to a buffer in which to store the data read from the drive.

## -remarks

The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566206(v=vs.85)">SMART_SEND_DRIVE_COMMAND</a> is used to send SMART commands to a device. 

The SENDCMDOUTPARAMS structure is also used with the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566204(v=vs.85)">SMART_RCV_DRIVE_DATA</a> request.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_sendcmdinparams">SENDCMDINPARAMS</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566204(v=vs.85)">SMART_RCV_DRIVE_DATA</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566206(v=vs.85)">SMART_SEND_DRIVE_COMMAND</a>

