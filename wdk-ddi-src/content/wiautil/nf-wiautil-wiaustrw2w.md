---
UID: NF:wiautil.wiauStrW2W
title: wiauStrW2W function (wiautil.h)
description: The wiauStrW2W function copies a Unicode string to another Unicode string.
old-location: image\wiaustrw2w.htm
tech.root: image
ms.assetid: 84f6d47f-bd14-4df4-b4fa-e58412daba6f
ms.date: 05/03/2018
keywords: ["wiauStrW2W function"]
ms.keywords: image.wiaustrw2w, wiauFncs_4778241e-19d0-40e1-ae24-e58e950ba540.xml, wiauStrW2W, wiauStrW2W function [Imaging Devices], wiautil/wiauStrW2W
f1_keywords:
 - "wiautil/wiauStrW2W"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wiautil.h
api_name:
- wiauStrW2W
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauStrW2W function


## -description


The <b>wiauStrW2W</b> function copies a Unicode string to another Unicode string.


## -parameters




### -param pwszSrc [in]

Points to the Unicode string to be copied.


### -param pwszDst [out]

Pointer to a memory location that receives the copied string.


### -param iSize

Specifies the size, in bytes, of the buffer pointed to by <i>pwszDst</i>.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaustrc2c">wiauStrC2C</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaustrc2w">wiauStrC2W</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaustrw2c">wiauStrW2C</a>
 

 

