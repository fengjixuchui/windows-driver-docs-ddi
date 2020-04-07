---
UID: NI:ntddvdeo.IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES
title: IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES (ntddvdeo.h)
description: Queries the brightness ranges for a display panel.
ms.assetid: 2fb0a064-2c67-46e0-baa9-d03394614d87
ms.date: 10/19/2018
keywords: ["IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES IOCTL"]
f1_keywords:
 - "ntddvdeo/IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES"
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
- IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES
product: 
- Windows
targetos: Windows
tech.root: display
---

# IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description

Queries the brightness ranges for a display panel.

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


