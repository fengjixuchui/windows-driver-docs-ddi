---
UID: NE:iddcx.IDDCX_UPDATE_REASON
title: IDDCX_UPDATE_REASON (iddcx.h)
description: Describes why the driver is calling to update the mode list.
old-location: display\iddcx_update_reason.htm
tech.root: display
ms.assetid: e451e4e3-0b8a-4a17-8e4e-2da99d336a39
ms.date: 05/10/2018
keywords: ["IDDCX_UPDATE_REASON enumeration"]
ms.keywords: IDDCX_UPDATE_REASON, IDDCX_UPDATE_REASON enumeration [Display Devices], IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS, IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH, IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH, IDDCX_UPDATE_REASON_OTHER, IDDCX_UPDATE_REASON_POWER_CONSTRAINTS, IDDCX_UPDATE_REASON_UNINITIALIZED, display.iddcx_update_reason, iddcx/IDDCX_UPDATE_REASON, iddcx/IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS, iddcx/IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH, iddcx/IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH, iddcx/IDDCX_UPDATE_REASON_OTHER, iddcx/IDDCX_UPDATE_REASON_POWER_CONSTRAINTS, iddcx/IDDCX_UPDATE_REASON_UNINITIALIZED
f1_keywords:
 - "iddcx/IDDCX_UPDATE_REASON"
 - "IDDCX_UPDATE_REASON"
req.header: iddcx.h
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
- iddcx.h
api_name:
- IDDCX_UPDATE_REASON
targetos: Windows
req.typenames: 
---

# IDDCX_UPDATE_REASON enumeration


## -description



                    Describes why the driver is calling to update the mode list
                


## -enum-fields




### -field IDDCX_UPDATE_REASON_UNINITIALIZED


                        
                    Indicates that an <b>IDDCX_UPDATE_REASON</b> variable has not yet been assigned a meaningful value.


### -field IDDCX_UPDATE_REASON_POWER_CONSTRAINTS


                        The mode list is changing due to changed power constraints on the host system
                    


### -field IDDCX_UPDATE_REASON_HOST_LINK_BANDWIDTH


                        The mode list is changing due to changes in bandwidth between the system and the indirect display device
                    


### -field IDDCX_UPDATE_REASON_DISPLAY_LINK_BANDWIDTH


                        The mode list is changing due to changes in bandwidth between the indirect display device and the monitor
                    


### -field IDDCX_UPDATE_REASON_CONFIGURATION_CONSTRAINTS


                        The mode list is changing due to constraints of the product when in a new configuration
                    


### -field IDDCX_UPDATE_REASON_OTHER


                        The mode list is changing due to another reason not listed above
                    


### -field UINT



