---
UID: NF:wdm.RtlUnicodeStringToAnsiString
title: RtlUnicodeStringToAnsiString function (wdm.h)
description: The RtlUnicodeStringToAnsiString routine converts a given Unicode string into an ANSI string.
old-location: kernel\rtlunicodestringtoansistring.htm
tech.root: kernel
ms.assetid: d05b366c-0b09-4a82-8727-e5c39b82bf7f
ms.date: 04/30/2018
keywords: ["RtlUnicodeStringToAnsiString function"]
ms.keywords: RtlUnicodeStringToAnsiString, RtlUnicodeStringToAnsiString routine [Kernel-Mode Driver Architecture], k109_50e549a0-61fa-4a0f-b43f-de2f4c6dba31.xml, kernel.rtlunicodestringtoansistring, wdm/RtlUnicodeStringToAnsiString
f1_keywords:
 - "wdm/RtlUnicodeStringToAnsiString"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlUnicodeStringToAnsiString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringToAnsiString function


## -description


The <b>RtlUnicodeStringToAnsiString</b> routine converts a given Unicode string into an ANSI string.


## -parameters




### -param DestinationString [in, out]

Pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_string">ANSI_STRING</a> structure to hold the converted ANSI string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, the routine allocates a new buffer to hold the string data, and updates the <b>Buffer</b> member of <i>DestinationString</i> to point to the new buffer. Otherwise, the routine uses the currently specified buffer to hold the string. 


### -param SourceString [in]

Pointer to the Unicode source string to be converted to ANSI.


### -param AllocateDestinationString [in]

<b>TRUE</b> if this routine is to allocate the buffer space for the <i>DestinationString</i>. If it does, the buffer must be deallocated by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeansistring">RtlFreeAnsiString</a>.


## -returns



If the conversion succeeds, <b>RtlUnicodeStringToAnsiString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated, and no conversion was done.




## -remarks



The translation is done in accord with the current system-locale information.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_string">ANSI_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodestring">RtlAnsiStringToUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeansistring">RtlFreeAnsiString</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

