---
UID: NS:hbapiwmi._SM_RemoveLink_OUT
title: _SM_RemoveLink_OUT (hbapiwmi.h)
description: The SM_RemoveLink_OUT structure is used to receive output parameters from the SM_RemoveLink WMI method.
old-location: storage\sm_removelink_out.htm
tech.root: storage
ms.assetid: f3b82d62-8596-4bb9-b20b-39f232527d7a
ms.date: 03/29/2018
keywords: ["SM_RemoveLink_OUT structure"]
ms.keywords: "*PSM_RemoveLink_OUT, PSM_RemoveLink_OUT, PSM_RemoveLink_OUT structure pointer [Storage Devices], SM_RemoveLink_OUT, SM_RemoveLink_OUT structure [Storage Devices], _SM_RemoveLink_OUT, hbapiwmi/PSM_RemoveLink_OUT, hbapiwmi/SM_RemoveLink_OUT, storage.sm_removelink_out, structs-Fibre_5355f5b8-47ea-4c71-880d-08891533bf29.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
req.typenames: SM_RemoveLink_OUT, *PSM_RemoveLink_OUT
f1_keywords:
 - _SM_RemoveLink_OUT
 - hbapiwmi/_SM_RemoveLink_OUT
 - PSM_RemoveLink_OUT
 - hbapiwmi/PSM_RemoveLink_OUT
 - SM_RemoveLink_OUT
 - hbapiwmi/SM_RemoveLink_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SM_RemoveLink_OUT
---

# _SM_RemoveLink_OUT structure


## -description

The SM_RemoveLink_OUT structure is used to receive output parameters from the SM_RemoveLink WMI method.

## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

## -remarks

The WMI tool suite generates a declaration of the SM_RemoveLink_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.