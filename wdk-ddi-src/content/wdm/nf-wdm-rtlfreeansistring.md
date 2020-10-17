---
UID: NF:wdm.RtlFreeAnsiString
title: RtlFreeAnsiString function (wdm.h)
description: The RtlFreeAnsiString routine releases storage that was allocated by RtlUnicodeStringToAnsiString.
old-location: kernel\rtlfreeansistring.htm
tech.root: kernel
ms.assetid: ca46be9e-31f6-4118-8958-4eb2c8450e8c
ms.date: 04/30/2018
keywords: ["RtlFreeAnsiString function"]
ms.keywords: RtlFreeAnsiString, RtlFreeAnsiString routine [Kernel-Mode Driver Architecture], k109_0213924f-caca-4411-b5cc-d93282f01948.xml, kernel.rtlfreeansistring, wdm/RtlFreeAnsiString
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlFreeAnsiString
 - wdm/RtlFreeAnsiString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlFreeAnsiString
---

# RtlFreeAnsiString function


## -description

The <b>RtlFreeAnsiString</b> routine releases storage that was allocated by <b>RtlUnicodeStringToAnsiString</b>.

## -parameters

### -param AnsiString 

[in, out]
Pointer to the ANSI string buffer previously allocated by <b>RtlUnicodeStringToAnsiString</b>.

## -returns

None

## -remarks

This routine does not release the Unicode string buffer passed to <b>RtlUnicodeStringToAnsiString</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlunicodestringtoansistring">RtlUnicodeStringToAnsiString</a>