---
UID: NE:rilapitypes.RILUICCLOCKSTATEPARAMMASK
title: RILUICCLOCKSTATEPARAMMASK (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclockstateparammask_2.htm
tech.root: netvista
ms.assetid: 88bdeb85-1ce8-43df-8cf1-4563d90a46ad
ms.date: 02/26/2018
keywords: ["RILUICCLOCKSTATEPARAMMASK enumeration"]
ms.keywords: RILUICCLOCKSTATEPARAMMASK, RILUICCLOCKSTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UICCLOCKSTATE_ALL, RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT, RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT, netvista.riluicclockstateparammask_2, rilapitypes/RILUICCLOCKSTATEPARAMMASK, rilapitypes/RIL_PARAM_UICCLOCKSTATE_ALL, rilapitypes/RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, rilapitypes/RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT, rilapitypes/RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT
f1_keywords:
 - "rilapitypes/RILUICCLOCKSTATEPARAMMASK"
 - "RILUICCLOCKSTATEPARAMMASK"
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
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
- RILUICCLOCKSTATEPARAMMASK
targetos: Windows
req.typenames: RILUICCLOCKSTATEPARAMMASK
req.product: Windows 10 or later.
---

# RILUICCLOCKSTATEPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef enum _RILUICCLOCKSTATEPARAMMASK {
  RIL_PARAM_UICCLOCKSTATE_LOCKSTATE,
  RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT,
  RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT,
  RIL_PARAM_UICCLOCKSTATE_ALL
} RILUICCLOCKSTATEPARAMMASK;
```


## -enum-fields




### -field RIL_PARAM_UICCLOCKSTATE_UICCLOCK


### -field RIL_PARAM_UICCLOCKSTATE_LOCKSTATE


### -field RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT


### -field RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT


### -field RIL_PARAM_UICCLOCKSTATE_ALL

