---
UID: NF:miniport.WRITE_REGISTER_UCHAR
title: WRITE_REGISTER_UCHAR function (miniport.h)
description: The WRITE_REGISTER_UCHAR routine writes a byte to the specified address.
old-location: kernel\write_register_uchar.htm
tech.root: kernel
ms.assetid: 2d97d31f-d8c6-45d6-9aee-69397a523bbd
ms.date: 04/30/2018
keywords: ["WRITE_REGISTER_UCHAR function"]
ms.keywords: WRITE_REGISTER_UCHAR, WRITE_REGISTER_UCHAR routine [Kernel-Mode Driver Architecture], k103_052039f1-0f3c-4b4b-9061-ea92046f7167.xml, kernel.write_register_uchar, wdm/WRITE_REGISTER_UCHAR
f1_keywords:
 - "miniport/WRITE_REGISTER_UCHAR"
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h, Wudfwdm.h
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
- WRITE_REGISTER_UCHAR
product:
- Windows
targetos: Windows
req.typenames: 
---

# WRITE_REGISTER_UCHAR function


## -description


The <b>WRITE_REGISTER_UCHAR</b> routine writes a byte to the specified address.


## -parameters




#### - Register [in]

Pointer to the register, which must be a mapped range in memory space.


#### - Value [in]

Specifies a byte to be written to the register. 


## -remarks



Callers of <b>WRITE_REGISTER_UCHAR</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.



