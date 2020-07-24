---
UID: NF:miniport.WRITE_REGISTER_ULONG64
title: WRITE_REGISTER_ULONG64 function (miniport.h)
description: The WRITE_REGISTER_ULONG64 function writes a ULONG64 value to the specified address.
old-location: wdf\write_register_ulong64.htm
tech.root: wdf
ms.assetid: 50C407F2-657F-451F-8A6B-BEEB533D89DE
ms.date: 02/26/2018
keywords: ["WRITE_REGISTER_ULONG64 function"]
ms.keywords: WRITE_REGISTER_ULONG64, WRITE_REGISTER_ULONG64 function, umdf.write_register_ulong64, wdf.write_register_ulong64, wudfddi_hwaccess/WRITE_REGISTER_ULONG64
f1_keywords:
 - "miniport/WRITE_REGISTER_ULONG64"
 - "WRITE_REGISTER_ULONG64"
req.header: miniport.h
req.include-header: Wdm.h, Miniport.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: 64-bit Windows
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver: 1.11
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace:
req.assembly:
req.type-library:
req.lib: NtosKrnl.exe
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi_hwaccess.h
api_name:
- WRITE_REGISTER_ULONG64
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---

# WRITE_REGISTER_ULONG64 function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WRITE_REGISTER_ULONG64</b> function writes a ULONG64 value to the specified address.


## -syntax


```cpp
void WRITE_REGISTER_ULONG64(
  _In_ IWDFDevice3 *pDevice,
  _In_ PULONG64    Register,
  _In_ ULONG       Value
);
```


## -parameters




### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Value [in]

Specifies a ULONG64 value to write to the register.


#### - pDevice [in]

Specifies a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface for the device object of the device to access.


## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.



