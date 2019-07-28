---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_INFO
title: tagKSCAMERA_EXTENDEDPROP_ROI_INFO (ksmedia.h)
description: This structure contains information about an ROI.
old-location: stream\kscamera_extendedprop_roi_info.htm
tech.root: stream
ms.assetid: DAE013B7-7715-4B03-99F7-807306736C14
ms.date: 04/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_ROI_INFO, KSCAMERA_EXTENDEDPROP_ROI_INFO, KSCAMERA_EXTENDEDPROP_ROI_INFO structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_ROI_INFO, PKSCAMERA_EXTENDEDPROP_ROI_INFO structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_ROI_INFO, ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_INFO, stream.kscamera_extendedprop_roi_info, tagKSCAMERA_EXTENDEDPROP_ROI_INFO"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSCAMERA_EXTENDEDPROP_ROI_INFO"
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
- KSCAMERA_EXTENDEDPROP_ROI_INFO
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_ROI_INFO, *PKSCAMERA_EXTENDEDPROP_ROI_INFO
---

# tagKSCAMERA_EXTENDEDPROP_ROI_INFO structure


## -description


This structure contains information about an ROI.


## -struct-fields




### -field Region

These are the relative coordinates in Q13 format on the frame that face detection is running.


### -field Flags

These are VIDEOPROCFLAG flags that indicate the op mode for the ISP control. For focus ROI, the default value is 0 representing focus region configuration without initiating a focus.


### -field Weight

This is the weight of the region (0-100).


### -field RegionOfInterestType

If the region is a face, this value is KSCAMERA_EXTENDEDPROP_ROITYPE_FACE. If the region is anything other than face, this value is KSCAMERA_EXTENDEDPROP_ROITYPE_UNKNOWN. For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ne-ksmedia-kscamera_extendedprop_roitype">KSCAMERA_EXTENDEDPROP_ROITYPE</a> enumeration.

