---
UID: NI:ntddvdeo.IOCTL_PANEL_SET_BRIGHTNESS_STATE
title: IOCTL_PANEL_SET_BRIGHTNESS_STATE (ntddvdeo.h)
description: Sets the brightness state for the display panel.
ms.assetid: fe3220fd-033f-4510-b615-a49607341280
ms.date: 10/19/2018
keywords: ["IOCTL_PANEL_SET_BRIGHTNESS_STATE IOCTL"]
f1_keywords:
 - "ntddvdeo/IOCTL_PANEL_SET_BRIGHTNESS_STATE"
req.header: ntddvdeo.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql:
req.ddi-compliance:
req.max-support:
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- ntddvdeo.h
api_name:
- IOCTL_PANEL_SET_BRIGHTNESS_STATE
product: 
- Windows
targetos: Windows
tech.root: display
---

# IOCTL_PANEL_SET_BRIGHTNESS_STATE IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description

Sets the brightness state for the display panel.

## -ioctlparameters

### -input-buffer



### -input-buffer-length



### -output-buffer



### -output-buffer-length



### -in-out-buffer



### -inout-buffer-length



### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code.


