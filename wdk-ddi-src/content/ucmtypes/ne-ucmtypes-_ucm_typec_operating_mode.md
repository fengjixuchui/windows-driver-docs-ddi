---
UID: NE:ucmtypes._UCM_TYPEC_OPERATING_MODE
title: _UCM_TYPEC_OPERATING_MODE (ucmtypes.h)
description: Defines operating modes of a USB Type-C connector.
old-location: buses\ucm_type_c_operating_mode.htm
tech.root: usbref
ms.assetid: B64849A6-DDB1-4BD1-B4B6-1E38DE9237E5
ms.date: 05/07/2018
ms.keywords: UCM_TYPEC_OPERATING_MODE, UCM_TYPEC_OPERATING_MODE enumeration [Buses], UcmTypeCOperatingModeDfp, UcmTypeCOperatingModeDrp, UcmTypeCOperatingModeInvalid, UcmTypeCOperatingModeUfp, _UCM_TYPEC_OPERATING_MODE, buses.ucm_type_c_operating_mode, ucmtypes/UCM_TYPEC_OPERATING_MODE, ucmtypes/UcmTypeCOperatingModeDfp, ucmtypes/UcmTypeCOperatingModeDrp, ucmtypes/UcmTypeCOperatingModeInvalid, ucmtypes/UcmTypeCOperatingModeUfp
ms.topic: enum
f1_keywords:
 - "ucmtypes/UCM_TYPEC_OPERATING_MODE"
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
- Ucmtypes.h
api_name:
- UCM_TYPEC_OPERATING_MODE
product:
- Windows
targetos: Windows
req.typenames: UCM_TYPEC_OPERATING_MODE
---

# _UCM_TYPEC_OPERATING_MODE enumeration


## -description


Defines operating modes of a USB Type-C connector.


## -enum-fields




### -field UcmTypeCOperatingModeInvalid

Indicates the operating mode is invalid.


### -field UcmTypeCOperatingModeDfp

Indicates the operating mode is set to downstream-facing port.


### -field UcmTypeCOperatingModeUfp

Indicates the operating mode is set to upstream-facing port.


### -field UcmTypeCOperatingModeDrp

Indicates the operating mode is set to dual-role port. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmmanager/nf-ucmmanager-ucm_connector_typec_config_init">UCM_CONNECTOR_TYPEC_CONFIG_INIT</a>
 

 

