---
UID: NS:hbapiwmi._SM_SetPersistentBinding_OUT
title: _SM_SetPersistentBinding_OUT (hbapiwmi.h)
description: The SM_SetPersistentBinding_OUT structure is used to receive output parameters from the SM_SetPersistentBinding method.
old-location: storage\sm_setpersistentbinding_out.htm
tech.root: storage
ms.assetid: 42d451ab-51dc-4b59-b6e9-42e02ec1b500
ms.date: 03/29/2018
keywords: ["_SM_SetPersistentBinding_OUT structure"]
ms.keywords: "*PSM_SetPersistentBinding_OUT, PSM_SetPersistentBinding_OUT, PSM_SetPersistentBinding_OUT structure pointer [Storage Devices], SM_SetPersistentBinding_OUT, SM_SetPersistentBinding_OUT structure [Storage Devices], _SM_SetPersistentBinding_OUT, hbapiwmi/PSM_SetPersistentBinding_OUT, hbapiwmi/SM_SetPersistentBinding_OUT, storage.sm_setpersistentbinding_out, structs-Fibre_efdd2145-a966-477a-a896-71adb1c9a1f0.xml"
f1_keywords:
 - "hbapiwmi/SM_SetPersistentBinding_OUT"
 - "SM_SetPersistentBinding_OUT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- SM_SetPersistentBinding_OUT
targetos: Windows
req.typenames: SM_SetPersistentBinding_OUT, *PSM_SetPersistentBinding_OUT
---

# _SM_SetPersistentBinding_OUT structure


## -description


The SM_SetPersistentBinding_OUT structure is used to receive output parameters from the SM_SetPersistentBinding method.


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.


### -field OutStatusCount

The number of entries.


### -field EntryStatus

The status of each entry.


## -remarks



The WMI tool suite generates a declaration of the SM__SetPersistentBinding_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.



