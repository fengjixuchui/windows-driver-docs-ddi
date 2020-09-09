---
UID: NS:scsiscan._SCSISCAN_INFO
title: _SCSISCAN_INFO (scsiscan.h)
description: The SCSISCAN_INFO structure is used as a parameter to DeviceIoControl (described in the Microsoft Windows SDK documentation), when the specified I/O control code is IOCTL_SCSISCAN_GET_INFO.
old-location: image\scsiscan_info.htm
tech.root: image
ms.assetid: 5fd9b381-c0e3-45bf-9061-da816da5e29f
ms.date: 05/03/2018
keywords: ["SCSISCAN_INFO structure"]
ms.keywords: "*PSCSISCAN_INFO, PSCSISCAN_INFO, PSCSISCAN_INFO structure pointer [Imaging Devices], SCSISCAN_INFO, SCSISCAN_INFO structure [Imaging Devices], _SCSISCAN_INFO, image.scsiscan_info, scsiscan/PSCSISCAN_INFO, scsiscan/SCSISCAN_INFO, stifnc_157af712-4f72-49f3-9da6-b8f750826d3e.xml"
req.header: scsiscan.h
req.include-header: Scsiscan.h
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
req.typenames: SCSISCAN_INFO, *PSCSISCAN_INFO
f1_keywords:
 - _SCSISCAN_INFO
 - scsiscan/_SCSISCAN_INFO
 - PSCSISCAN_INFO
 - scsiscan/PSCSISCAN_INFO
 - SCSISCAN_INFO
 - scsiscan/SCSISCAN_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsiscan.h
api_name:
 - SCSISCAN_INFO
---

# _SCSISCAN_INFO structure


## -description

The SCSISCAN_INFO structure is used as a parameter to [DeviceIoControl](https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol), when the specified I/O control code is [IOCTL_SCSISCAN_GET_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiscan/ni-scsiscan-ioctl_scsiscan_get_info).

## -struct-fields

### -field Size

Size, in bytes, of the SCSISCAN_INFO structure.

### -field Flags

Not used, must be zero.

### -field PortNumber

SCSI adapter number.

### -field PathId

Host SCSI ID.

### -field TargetId

Target SCSI ID.

### -field Lun

Target logical unit number (LUN).

### -field AdapterName

*For internal use only.*

### -field Reserved

*For internal use only.*

