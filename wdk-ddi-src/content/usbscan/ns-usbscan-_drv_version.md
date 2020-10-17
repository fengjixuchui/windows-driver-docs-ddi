---
UID: NS:usbscan._DRV_VERSION
title: _DRV_VERSION (usbscan.h)
description: The DRV_VERSION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_VERSION.
old-location: image\drv_version.htm
tech.root: image
ms.assetid: 61b6dbd3-7565-4d63-bcc0-007df9793398
ms.date: 05/03/2018
keywords: ["DRV_VERSION structure"]
ms.keywords: "*PDRV_VERSION, DRV_VERSION, DRV_VERSION structure [Imaging Devices], PDRV_VERSION, PDRV_VERSION structure pointer [Imaging Devices], _DRV_VERSION, image.drv_version, stifnc_99059efa-8e64-49f6-bebe-560d33fca145.xml, usbscan/DRV_VERSION, usbscan/PDRV_VERSION"
req.header: usbscan.h
req.include-header: Usbscan.h
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
req.typenames: DRV_VERSION, *PDRV_VERSION
f1_keywords:
 - _DRV_VERSION
 - usbscan/_DRV_VERSION
 - PDRV_VERSION
 - usbscan/PDRV_VERSION
 - DRV_VERSION
 - usbscan/DRV_VERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbscan.h
api_name:
 - DRV_VERSION
---

# _DRV_VERSION structure


## -description

The DRV_VERSION structure is used as a parameter to <a href="/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="/windows-hardware/drivers/ddi/usbscan/ni-usbscan-ioctl_get_version">IOCTL_GET_VERSION</a>.

## -struct-fields

### -field major

Major version number.

### -field minor

Minor version number.

### -field internal

Internal, vendor-specific version number.