---
UID: NF:wiautil.WIAS_HRESULT
title: WIAS_HRESULT macro (wiautil.h)
description: The WIAS_HRESULT macro writes a diagnostic message to the Wiatrace.log file.
old-location: image\wias_hresult.htm
tech.root: image
ms.assetid: e340eb98-34d4-49e7-92cd-4f57d8b6efb8
ms.date: 05/03/2018
keywords: ["WIAS_HRESULT macro"]
ms.keywords: IWiaLog_3b27b46f-be2e-4fdb-ba65-32fe41c71142.xml, WIAS_HRESULT, WIAS_HRESULT macro [Imaging Devices], image.wias_hresult, wiamdef/WIAS_HRESULT
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
 - WIAS_HRESULT
 - wiautil/WIAS_HRESULT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiamdef.h
api_name:
 - WIAS_HRESULT
---

# WIAS_HRESULT macro (wiautil.h)


## -description

The WIAS_HRESULT macro writes a diagnostic message to the *Wiatrace.log* file.

## -parameters

### -param x

- **hInstance** - Handle to the calling driver.

- **hr** - Specifies the HRESULT value to be printed.

## -remarks

This macro is the recommended way to output HRESULTS on Windows Vista.

## -see-also

[WIAS_ASSERT](../wiamdef/nf-wiamdef-wias_assert.md)

[WIAS_ERROR](../wiamdef/nf-wiamdef-wias_error.md)

[WIAS_TRACE](../wiamdef/nf-wiamdef-wias_trace.md)