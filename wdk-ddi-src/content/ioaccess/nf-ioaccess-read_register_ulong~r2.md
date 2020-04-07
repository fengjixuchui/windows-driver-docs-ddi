---
UID: NF:ioaccess.READ_REGISTER_ULONG~r2
title: READ_REGISTER_ULONG function (ioaccess.h)
description: The READ_REGISTER_ULONG routine reads a ULONG value from the specified register address.
old-location: kernel\read_register_ulong.htm
tech.root: kernel
ms.assetid: a462734c-cac6-4de0-95c1-810766ef1644
ms.date: 03/01/2018
keywords: ["READ_REGISTER_ULONG function"]
ms.keywords: READ_REGISTER_ULONG, READ_REGISTER_ULONG routine [Kernel-Mode Driver Architecture], k103_c2da9866-18ac-438b-aa32-991d1bda139f.xml, kernel.read_register_ulong, wdm/READ_REGISTER_ULONG
f1_keywords:
 - "ioaccess/READ_REGISTER_ULONG"
req.header: ioaccess.h
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
- READ_REGISTER_ULONG
product:
- Windows
targetos: Windows
req.typenames: IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS, IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS
---

# READ_REGISTER_ULONG function


## -description


The <b>READ_REGISTER_ULONG</b> routine reads a ULONG value from the specified register address.


## -syntax


```cpp
ULONG READ_REGISTER_ULONG(
  _In_ PULONG Register
);
```


## -parameters




### -param Register [in]

Pointer to the register address, which must be a mapped range in memory space.


## -returns



<b>READ_REGISTER_ULONG</b> returns the ULONG value read from the specified register address.




## -remarks



Callers of <b>READ_REGISTER_ULONG</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.



