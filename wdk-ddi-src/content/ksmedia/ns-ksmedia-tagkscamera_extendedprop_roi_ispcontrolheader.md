---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
title: tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER (ksmedia.h)
description: This structure contains the header information for ROI ISP controls.
old-location: stream\kscamera_extendedprop_roi_ispcontrolheader.htm
tech.root: stream
ms.assetid: F57B0E44-A6A1-4C43-83EE-8DF4A605C0D0
ms.date: 04/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, stream.kscamera_extendedprop_roi_ispcontrolheader, tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER"
req.header: ksmedia.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ksmedia.h
api_name:
- KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, *PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
---

# tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER structure


## -description


This structure contains the header information for ROI ISP controls.


## -struct-fields




### -field Size

The sum of this structure size, all <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-tagkscamera_extendedprop_roi_ispcontrol">KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL</a> structures, and all KSCAMERA_EXTENDEDPROP_ROI_RECTINFO structures that follow


### -field ControlCount

The number of ISP controls. If this value is 0, the ROI control will remove all ROIs previously configured. This effectively clears up all ROIs configured and resets the driver to the default ROI.


### -field Reserved

Reserved for future use.

