---
UID: NS:ntddrilapitypes.RILUICCFILELOCKSTATUS
title: RILUICCFILELOCKSTATUS (ntddrilapitypes.h)
description: This structure represents RILUICCFILELOCKSTATUS.
old-location: netvista\riluiccfilelockstatus.htm
tech.root: netvista
ms.assetid: 348e44f2-4386-4b45-9d68-c996d471578f
ms.date: 02/16/2018
ms.keywords: "*LPRILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS structure [Network Drivers Starting with Windows Vista], netvista.riluiccfilelockstatus, rilapitypes/RILUICCFILELOCKSTATUS"
ms.topic: struct
f1_keywords:
 - "ntddrilapitypes/RILUICCFILELOCKSTATUS"
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
- rilapitypes.h
api_name:
- RILUICCFILELOCKSTATUS
product:
- Windows
targetos: Windows
req.typenames: RILUICCFILELOCKSTATUS, *LPRILUICCFILELOCKSTATUS
---

# RILUICCFILELOCKSTATUS structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILUICCFILELOCKSTATUS.


## -syntax


```cpp
struct RILUICCFILELOCKSTATUS {
  DWORD                                cbSize;
  DWORD                                dwParams;
  RILUICCFILELOCKSTATUSACCESSCONDITION dwAccessCondition;
  BYTE                                 bPinRef[MAXNUM_PINREF];
};
```


## -struct-fields




### -field cbSize

The size of the structure in bytes.


### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-riluiccfilelockstatusparammask.md">RILUICCFILELOCKSTATUSPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwAccessCondition

Specifies the access condition for the file. These values correspond to those specified in ETSI TS 102 221 section 9.5.1. The access condition should be one of <a href="..\rilapitypes\ne-rilapitypes-riluiccfilelockstatusaccesscondition.md">RILUICCFILELOCKSTATUSACCESSCONDITION</a>.


### -field bPinRef

A byte array specifying the application PIN references made by this application (keys for PIN1 and PIN2).


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>



 

 


