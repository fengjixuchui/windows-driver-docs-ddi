---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_ROTATION_DATA
title: _DXVAHDDDI_STREAM_STATE_ROTATION_DATA (d3dumddi.h)
description: Describes stream-state data that specifies the clockwise rotation of the display output surface.
old-location: display\dxvahdddi_stream_state_rotation_data.htm
tech.root: display
ms.assetid: 1c874df6-6b47-4501-9eaf-7c07f0172580
ms.date: 05/10/2018
keywords: ["_DXVAHDDDI_STREAM_STATE_ROTATION_DATA structure"]
ms.keywords: DXVAHDDDI_STREAM_STATE_ROTATION_DATA, DXVAHDDDI_STREAM_STATE_ROTATION_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_ROTATION_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_ROTATION_DATA, display.dxvahdddi_stream_state_rotation_data
f1_keywords:
 - "d3dumddi/DXVAHDDDI_STREAM_STATE_ROTATION_DATA"
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dumddi.h
api_name:
- DXVAHDDDI_STREAM_STATE_ROTATION_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_ROTATION_DATA
---

# _DXVAHDDDI_STREAM_STATE_ROTATION_DATA structure


## -description


Describes stream-state data that specifies the clockwise rotation of the display output surface.


## -struct-fields




### -field Enable

A Boolean value that specifies whether the driver should rotate the output surface. The default value is <b>FALSE</b>, which indicates that rotation is disabled.


### -field Rotation

The clockwise degrees of rotation as specified by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_rotation">DXVAHDDDI_ROTATION</a> enumeration value.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_rotation">DXVAHDDDI_ROTATION</a>
 

 

