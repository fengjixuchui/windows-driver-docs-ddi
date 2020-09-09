---
UID: NI:lamp.IOCTL_LAMP_SET_EMITTING_LIGHT
title: IOCTL_LAMP_SET_EMITTING_LIGHT (lamp.h)
description: The IOCTL_LAMP_SET_EMITTING_LIGHT control code turns the lamp on or off.
old-location: stream\ioctl_lamp_set_emitting_light.htm
tech.root: stream
ms.assetid: E3B85C82-EC55-4A88-BFCA-91123F8311D1
ms.date: 04/23/2018
keywords: ["IOCTL_LAMP_SET_EMITTING_LIGHT IOCTL"]
ms.keywords: IOCTL_LAMP_SET_EMITTING_LIGHT, IOCTL_LAMP_SET_EMITTING_LIGHT control, IOCTL_LAMP_SET_EMITTING_LIGHT control code [Streaming Media Devices], lamp/IOCTL_LAMP_SET_EMITTING_LIGHT, stream.ioctl_lamp_set_emitting_light
req.header: lamp.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_LAMP_SET_EMITTING_LIGHT
 - lamp/IOCTL_LAMP_SET_EMITTING_LIGHT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - lamp.h
api_name:
 - IOCTL_LAMP_SET_EMITTING_LIGHT
---

# IOCTL_LAMP_SET_EMITTING_LIGHT IOCTL


## -description

The **IOCTL_LAMP_SET_EMITTING_LIGHT** control code turns the lamp on or off.

```cpp
#define IOCTL_LAMP_SET_EMITTING_LIGHT \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0009, METHOD_BUFFERED, FILE_ANY_ACCESS)
```

## -ioctlparameters

### -input-buffer

`Irp->AssociatedIrp.SystemBuffer` points to a buffer of type **BOOLEAN**, with **TRUE** indicating a request to turn the lamp on; **FALSE** otherwise.

### -input-buffer-length

Length of a **BOOLEAN**.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The driver sets `Irp->IoStatus.Status` to **STATUS_SUCCESS** or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a **STATUS_RESOURCE_IN_USE** error via `Irp->IoStatus.Status`.

