---
UID: NE:wdm._DEVICE_WAKE_DEPTH
title: _DEVICE_WAKE_DEPTH (wdm.h)
description: The DEVICE_WAKE_DEPTH enumeration specifies the deepest device power state from which a device can trigger a wake signal.
old-location: kernel\device_wake_depth.htm
tech.root: kernel
ms.assetid: C8829785-1EB7-4F29-9279-F2FC2A3C0ABD
ms.date: 04/30/2018
keywords: ["DEVICE_WAKE_DEPTH enumeration"]
ms.keywords: "*PDEVICE_WAKE_DEPTH, DEVICE_WAKE_DEPTH, DEVICE_WAKE_DEPTH enumeration [Kernel-Mode Driver Architecture], DeviceWakeDepthD0, DeviceWakeDepthD1, DeviceWakeDepthD2, DeviceWakeDepthD3cold, DeviceWakeDepthD3hot, DeviceWakeDepthMaximum, DeviceWakeDepthNotWakeable, _DEVICE_WAKE_DEPTH, kernel.device_wake_depth, wdm/DEVICE_WAKE_DEPTH, wdm/DeviceWakeDepthD0, wdm/DeviceWakeDepthD1, wdm/DeviceWakeDepthD2, wdm/DeviceWakeDepthD3cold, wdm/DeviceWakeDepthD3hot, wdm/DeviceWakeDepthMaximum, wdm/DeviceWakeDepthNotWakeable"
req.header: wdm.h
req.include-header: Wdm.h
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
req.typenames: DEVICE_WAKE_DEPTH, *PDEVICE_WAKE_DEPTH
f1_keywords:
 - _DEVICE_WAKE_DEPTH
 - wdm/_DEVICE_WAKE_DEPTH
 - PDEVICE_WAKE_DEPTH
 - wdm/PDEVICE_WAKE_DEPTH
 - DEVICE_WAKE_DEPTH
 - wdm/DEVICE_WAKE_DEPTH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - DEVICE_WAKE_DEPTH
---

# _DEVICE_WAKE_DEPTH enumeration


## -description

The <b>DEVICE_WAKE_DEPTH</b> enumeration specifies the deepest device power state from which a device can trigger a wake signal.

## -enum-fields

### -field DeviceWakeDepthNotWakeable

There is no device power state that can trigger a wake signal.

### -field DeviceWakeDepthD0

D0 is the deepest device power state from which the device can trigger a wake signal. For more information, see Remarks.

### -field DeviceWakeDepthD1

D1 is the deepest low-power device power state from which the device can trigger a wake signal.

### -field DeviceWakeDepthD2

D2 is the deepest low-power device power state from which the device can trigger a wake signal.

### -field DeviceWakeDepthD3hot

D3hot is the deepest low-power device power state from which the device can trigger a wake signal.

### -field DeviceWakeDepthD3cold

D3cold is the deepest low-power device power state from which the device can trigger a wake signal.

### -field DeviceWakeDepthMaximum

Reserved for use by the operating system.

## -remarks

The <i>DeepestWakeableDstate</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_idle_wake_info">GetIdleWakeInfo</a> routine is a pointer to a variable of type <b>DEVICE_WAKE_DEPTH</b>.

The drivers for most devices have no reason to arm a wake signal when the device is in D0. These drivers can treat the <b>DeviceWakeDepthD0</b> output value as equivalent to a call to the <i>GetIdleWakeInfo</i> routine that fails and returns an error status.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_idle_wake_info">GetIdleWakeInfo</a>

