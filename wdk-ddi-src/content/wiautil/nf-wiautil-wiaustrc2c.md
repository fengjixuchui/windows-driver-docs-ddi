---
UID: NF:wiautil.wiauStrC2C
title: wiauStrC2C function (wiautil.h)
description: The wiauStrC2C function copies an ANSI character string to another ANSI character string.
old-location: image\wiaustrc2c.htm
tech.root: image
ms.assetid: 7e8cd99a-d1b1-4261-9643-4a84bddfdc01
ms.date: 05/03/2018
keywords: ["wiauStrC2C function"]
ms.keywords: image.wiaustrc2c, wiauFncs_2266a6c9-ed4b-4af8-947a-d634bd9e9912.xml, wiauStrC2C, wiauStrC2C function [Imaging Devices], wiautil/wiauStrC2C
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
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
 - wiauStrC2C
 - wiautil/wiauStrC2C
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiautil.h
api_name:
 - wiauStrC2C
---

# wiauStrC2C function


## -description

The <b>wiauStrC2C</b> function copies an ANSI character string to another ANSI character string.

## -parameters

### -param pszSrc 

[in]
Points to the ANSI string to be copied.

### -param pszDst 

[out]
Pointer to a memory location that receives the copied string

### -param iSize

Specifies the size, in bytes, of the buffer pointed to by <i>pszDst</i>.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaustrc2w">wiauStrC2W</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaustrw2c">wiauStrW2C</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaustrw2w">wiauStrW2W</a>

