---
UID: NE:ntddrilapitypes.RILADDRESSPARAMMASK
title: RILADDRESSPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILADDRESSPARAMMASK enumeration.
old-location: netvista\riladdressparammask.htm
tech.root: netvista
ms.assetid: 02d77f8f-9327-40e4-b38b-7f1a02abf4b1
ms.date: 02/16/2018
ms.keywords: RILADDRESSPARAMMASK, RILADDRESSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_A_ADDRESS, RIL_PARAM_A_ALL, RIL_PARAM_A_NONE, RIL_PARAM_A_NUMPLAN, RIL_PARAM_A_TYPE, netvista.riladdressparammask, rilapitypes/RILADDRESSPARAMMASK, rilapitypes/RIL_PARAM_A_ADDRESS, rilapitypes/RIL_PARAM_A_ALL, rilapitypes/RIL_PARAM_A_NONE, rilapitypes/RIL_PARAM_A_NUMPLAN, rilapitypes/RIL_PARAM_A_TYPE
ms.topic: enum
f1_keywords:
 - "ntddrilapitypes/RILADDRESSPARAMMASK"
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
- RILADDRESSPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILADDRESSPARAMMASK
---

# RILADDRESSPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILADDRESSPARAMMASK enumeration.


## -syntax


```cpp
enum RILADDRESSPARAMMASK {
  RIL_PARAM_A_NONE     = 0x00000000,
  RIL_PARAM_A_TYPE     = 0x00000001,
  RIL_PARAM_A_NUMPLAN  = 0x00000002,
  RIL_PARAM_A_ADDRESS  = 0x00000004,
  RIL_PARAM_A_ALL      = 0x00000007

};
```


## -enum-fields




### -field RIL_PARAM_A_NONE


### -field RIL_PARAM_A_TYPE


### -field RIL_PARAM_A_NUMPLAN


### -field RIL_PARAM_A_ADDRESS


### -field RIL_PARAM_A_ALL


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>



 

 


