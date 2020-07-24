---
UID: NS:d3dkmddi._DXGK_CONTEXTINFO_CAPS
title: _DXGK_CONTEXTINFO_CAPS (d3dkmddi.h)
description: DXGK_CONTEXTINFO_CAPS is used to describe the capabilities supported by a driver.
old-location: display\dxgk_contextinfo_caps.htm
ms.assetid: AC65F790-981F-4B50-BB9E-84F79D8F6C4F
ms.date: 05/10/2018
keywords: ["_DXGK_CONTEXTINFO_CAPS structure"]
ms.keywords: DXGK_CONTEXTINFO_CAPS, DXGK_CONTEXTINFO_CAPS structure [Display Devices], _DXGK_CONTEXTINFO_CAPS, d3dkmddi/DXGK_CONTEXTINFO_CAPS, display.dxgk_contextinfo_caps
f1_keywords:
 - "d3dkmddi/DXGK_CONTEXTINFO_CAPS"
 - "DXGK_CONTEXTINFO_CAPS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- d3dkmddi.h
api_name:
- DXGK_CONTEXTINFO_CAPS
targetos: Windows
tech.root: display
req.typenames: DXGK_CONTEXTINFO_CAPS
---

# _DXGK_CONTEXTINFO_CAPS structure


## -description


<b>DXGK_CONTEXTINFO_CAPS</b> is used to describe  the capabilities supported by a driver.


## -struct-fields




### -field NoPatchingRequired

Indicates that no memory patching is required.


### -field DriverManagesResidency

Indicates that the driver manages memory residency.


### -field UseIoMmu

Indicates that the driver supports IoMmu. 


### -field Reserved

This field is reserved and should not be used.


### -field Value

The consolidated value of the structure.

