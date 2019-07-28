---
UID: NF:miniport.READ_REGISTER_USHORT
title: READ_REGISTER_USHORT function (miniport.h)
description: The READ_REGISTER_USHORT routine reads a USHORT value from the specified register address.
old-location: kernel\read_register_ushort.htm
tech.root: kernel
ms.assetid: d1160b0a-9969-44ba-82e7-14048e1554c2
ms.date: 04/30/2018
ms.keywords: READ_REGISTER_USHORT, READ_REGISTER_USHORT routine [Kernel-Mode Driver Architecture], k103_c2fa06bd-05b9-4fbd-b47c-f264d3ed0bd7.xml, kernel.read_register_ushort, wdm/READ_REGISTER_USHORT
ms.topic: function
f1_keywords:
 - "miniport/READ_REGISTER_USHORT"
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
- READ_REGISTER_USHORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# READ_REGISTER_USHORT function


## -description


The <b>READ_REGISTER_USHORT</b> routine reads a USHORT value from the specified register address.


## -parameters




#### - Register [in]

Pointer to the register address, which must be a mapped range in memory space. 


## -returns



<b>READ_REGISTER_USHORT</b> returns the USHORT value read from the specified register address.




## -remarks



Callers of <b>READ_REGISTER_USHORT</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.



