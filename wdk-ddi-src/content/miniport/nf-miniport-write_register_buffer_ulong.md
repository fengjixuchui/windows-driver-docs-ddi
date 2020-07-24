---
UID: NF:miniport.WRITE_REGISTER_BUFFER_ULONG
title: WRITE_REGISTER_BUFFER_ULONG function (miniport.h)
description: The WRITE_REGISTER_BUFFER_ULONG routine writes a number of ULONG values from a buffer to the specified register.
old-location: kernel\write_register_buffer_ulong.htm
tech.root: kernel
ms.assetid: dae9cc3d-b793-4f2a-99a6-1f77af396110
ms.date: 04/30/2018
keywords: ["WRITE_REGISTER_BUFFER_ULONG function"]
ms.keywords: WRITE_REGISTER_BUFFER_ULONG, WRITE_REGISTER_BUFFER_ULONG routine [Kernel-Mode Driver Architecture], k103_9ef495b2-fe86-484a-bec2-5390df6ee246.xml, kernel.write_register_buffer_ulong, wdm/WRITE_REGISTER_BUFFER_ULONG
f1_keywords:
 - "miniport/WRITE_REGISTER_BUFFER_ULONG"
 - "WRITE_REGISTER_BUFFER_ULONG"
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h, Wudfwdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- WRITE_REGISTER_BUFFER_ULONG
targetos: Windows
req.typenames: 
---

# WRITE_REGISTER_BUFFER_ULONG function


## -description


The <b>WRITE_REGISTER_BUFFER_ULONG</b> routine writes a number of ULONG values from a buffer to the specified register.


## -parameters




### -param Register [in]

Pointer to the register, which must be a mapped range in memory space.


### -param Buffer [in]

Pointer to a buffer from which an array of ULONG values is to be written.


### -param Count [in]

Specifies the number of ULONG values to be written to the register. 


## -remarks



The size of the buffer must be large enough to contain at least the specified number of ULONG values.

Callers of <b>WRITE_REGISTER_BUFFER_ULONG</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Register</i> is resident, mapped device memory.



