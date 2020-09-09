---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
title: IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE (usbfnioctl.h)
description: Do not use.
old-location: buses\ioctl_internal_usbfn_set_power_filter_state.htm
tech.root: usbref
ms.assetid: 2C010516-500A-4CA2-B6FE-20333E7CCC39
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE, IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE control, IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE control code [Buses], buses.ioctl_internal_usbfn_set_power_filter_state, usbfnioctl/IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
req.header: usbfnioctl.h
req.include-header: Usbfnioctl.h
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
 - IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
 - usbfnioctl/IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnioctl.h
api_name:
 - IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
---

# IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE IOCTL


## -description

Do not use.
		ucxc

## -ioctlparameters

### -input-buffer

The input buffer contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ns-usbfnioctl-_usbfn_power_filter_state">USBFN_POWER_FILTER_STATE</a> structure that specifies the device state.

### -input-buffer-length

The size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ns-usbfnioctl-_usbfn_power_filter_state">USBFN_POWER_FILTER_STATE</a> structure.

### -output-buffer

NULL.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

