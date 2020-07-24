---
UID: NF:wdfhwaccess.WDF_READ_REGISTER_ULONG64
title: WDF_READ_REGISTER_ULONG64 function (wdfhwaccess.h)
description: The WDF_READ_REGISTER_ULONG64 function reads a ULONG64 value from the specified register address.
old-location: wdf\wdf_read_register_ulong64.htm
tech.root: wdf
ms.assetid: A47BEA59-CBDD-41B5-9CEB-DC354D2BCC72
ms.date: 02/26/2018
keywords: ["WDF_READ_REGISTER_ULONG64 function"]
ms.keywords: WDF_READ_REGISTER_ULONG64, WDF_READ_REGISTER_ULONG64 function, wdf.wdf_read_register_ulong64, wdfhwaccess/WDF_READ_REGISTER_ULONG64
f1_keywords:
 - "wdfhwaccess/WDF_READ_REGISTER_ULONG64"
 - "WDF_READ_REGISTER_ULONG64"
req.header: wdfhwaccess.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
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
- Wdfhwaccess.h
api_name:
- WDF_READ_REGISTER_ULONG64
targetos: Windows
req.typenames: 
---

# WDF_READ_REGISTER_ULONG64 function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_READ_REGISTER_ULONG64</b> function reads a ULONG64 value from the specified register address.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register address, which must be a mapped range in memory space.


## -returns



<b>WDF_READ_REGISTER_ULONG64</b> returns the ULONG64 value that is read from the specified port address.



