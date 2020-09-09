---
UID: NE:rilapitypes.RILEUTRAMRLPARAMMASK
title: RILEUTRAMRLPARAMMASK (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rileutramrlparammask_2.htm
tech.root: netvista
ms.assetid: 68f194f5-137e-45a3-94b1-71cd20a27ea3
ms.date: 02/26/2018
keywords: ["RILEUTRAMRLPARAMMASK enumeration"]
ms.keywords: RILEUTRAMRLPARAMMASK, RILEUTRAMRLPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_EUTRAMRL_ALL, RIL_PARAM_EUTRAMRL_CELLID, RIL_PARAM_EUTRAMRL_EARFCN, RIL_PARAM_EUTRAMRL_MNC, RIL_PARAM_EUTRAMRL_PHYSCELLID, RIL_PARAM_EUTRAMRL_RSRP, RIL_PARAM_EUTRAMRL_RSRQ, RIL_PARAM_EUTRAMRL_TAC, netvista.rileutramrlparammask_2, rilapitypes/RILEUTRAMRLPARAMMASK, rilapitypes/RIL_PARAM_EUTRAMRL_ALL, rilapitypes/RIL_PARAM_EUTRAMRL_CELLID, rilapitypes/RIL_PARAM_EUTRAMRL_EARFCN, rilapitypes/RIL_PARAM_EUTRAMRL_MNC, rilapitypes/RIL_PARAM_EUTRAMRL_PHYSCELLID, rilapitypes/RIL_PARAM_EUTRAMRL_RSRP, rilapitypes/RIL_PARAM_EUTRAMRL_RSRQ, rilapitypes/RIL_PARAM_EUTRAMRL_TAC
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
targetos: Windows
req.typenames: RILEUTRAMRLPARAMMASK
req.product: Windows 10 or later.
f1_keywords:
 - RILEUTRAMRLPARAMMASK
 - rilapitypes/RILEUTRAMRLPARAMMASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILEUTRAMRLPARAMMASK
---

# RILEUTRAMRLPARAMMASK enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_PARAM_EUTRAMRL_MCC

### -field RIL_PARAM_EUTRAMRL_MNC

### -field RIL_PARAM_EUTRAMRL_CELLID

### -field RIL_PARAM_EUTRAMRL_EARFCN

### -field RIL_PARAM_EUTRAMRL_PHYSCELLID

### -field RIL_PARAM_EUTRAMRL_TAC

### -field RIL_PARAM_EUTRAMRL_RSRP

### -field RIL_PARAM_EUTRAMRL_RSRQ

### -field RIL_PARAM_EUTRAMRL_ALL

## -syntax

```cpp
typedef enum _RILEUTRAMRLPARAMMASK {
  RIL_PARAM_EUTRAMRL_MNC,
  RIL_PARAM_EUTRAMRL_CELLID,
  RIL_PARAM_EUTRAMRL_EARFCN,
  RIL_PARAM_EUTRAMRL_PHYSCELLID,
  RIL_PARAM_EUTRAMRL_TAC,
  RIL_PARAM_EUTRAMRL_RSRP,
  RIL_PARAM_EUTRAMRL_RSRQ,
  RIL_PARAM_EUTRAMRL_ALL
} RILEUTRAMRLPARAMMASK;
```

