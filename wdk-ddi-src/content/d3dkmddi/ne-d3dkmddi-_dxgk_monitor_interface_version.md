---
UID: NE:d3dkmddi._DXGK_MONITOR_INTERFACE_VERSION
title: _DXGK_MONITOR_INTERFACE_VERSION (d3dkmddi.h)
description: Indicates a particular version of the Monitor interface.
old-location: display\dxgk_monitor_interface_version.htm
ms.assetid: 76af0d70-f9bb-4768-9bfd-f2aaeb212db0
ms.date: 05/10/2018
ms.keywords: DXGK_MONITOR_INTERFACE_VERSION, DXGK_MONITOR_INTERFACE_VERSION enumeration [Display Devices], DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED, DXGK_MONITOR_INTERFACE_VERSION_V1, DXGK_MONITOR_INTERFACE_VERSION_V2, DmEnums_4ec3a10c-c04f-431b-851d-908a5ff972a1.xml, _DXGK_MONITOR_INTERFACE_VERSION, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION_V1, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION_V2, display.dxgk_monitor_interface_version
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dkmddi.h
api_name:
- DXGK_MONITOR_INTERFACE_VERSION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MONITOR_INTERFACE_VERSION
---

# _DXGK_MONITOR_INTERFACE_VERSION enumeration


## -description


The <b>DXGK_MONITOR_INTERFACE_VERSION</b> enumeration indicates a particular version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Monitor interface</a>.


## -enum-fields




### -field DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED

Indicates that a variable of type DXGK_MONITOR_INTERFACE_VERSION has not yet been assigned a meaningful value.


### -field DXGK_MONITOR_INTERFACE_VERSION_V1

Indicates version 1, available in Windows Vista and later versions of the Windows operating systems.


### -field DXGK_MONITOR_INTERFACE_VERSION_V2


      Indicates version 2, available in Windows 7 and later versions of the Windows operating systems.
     


## -remarks



The <b>Version</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface">DXGK_MONITOR_INTERFACE</a> structure is a value from the <b>DXGK_MONITOR_INTERFACE_VERSION</b> enumeration.



