---
UID: NS:iddcx.IDARG_IN_SET_GAMMARAMP
title: IDARG_IN_SET_GAMMARAMP (iddcx.h)
description: Gives information about the gamma ramp being set.
old-location: display\idarg_in_set_gammaramp.htm
tech.root: display
ms.assetid: 1e14bcaf-1454-4930-a3b8-afc044c4be3f
ms.date: 05/10/2018
keywords: ["IDARG_IN_SET_GAMMARAMP structure"]
ms.keywords: IDARG_IN_SET_GAMMARAMP, IDARG_IN_SET_GAMMARAMP structure [Display Devices], display.idarg_in_set_gammaramp, iddcx/IDARG_IN_SET_GAMMARAMP
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDARG_IN_SET_GAMMARAMP
 - iddcx/IDARG_IN_SET_GAMMARAMP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_SET_GAMMARAMP
---

# IDARG_IN_SET_GAMMARAMP structure


## -description

Gives information about the gamma ramp being set.

## -struct-fields

### -field Type

                     [in] The type of gamma ramp being set.

### -field GammaRampSizeInBytes

                     [in] Size in bytes of the provided gamma ramp data.  Set to zero for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iddcx/ne-iddcx-iddcx_gammaramp_type">IDDCX_GAMMARAMP_TYPE</a>.

### -field pGammaRampData

                     [in] Pointer to gamma ramp data to set.  Set to NULL for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iddcx/ne-iddcx-iddcx_gammaramp_type">IDDCX_GAMMARAMP_TYPE</a>.

