---
UID: NF:ntifs.RtlOemStringToCountedUnicodeString
title: RtlOemStringToCountedUnicodeString function (ntifs.h)
description: The RtlOemStringToCountedUnicodeString routine translates the specified source string into a Unicode string using the current system OEM code page.
old-location: ifsk\rtloemstringtocountedunicodestring.htm
tech.root: ifsk
ms.assetid: bf36d51f-3e22-489b-a597-652f39242a30
ms.date: 04/16/2018
keywords: ["RtlOemStringToCountedUnicodeString function"]
ms.keywords: RtlOemStringToCountedUnicodeString, RtlOemStringToCountedUnicodeString routine [Installable File System Drivers], ifsk.rtloemstringtocountedunicodestring, ntifs/RtlOemStringToCountedUnicodeString, rtlref_f67c05d0-0a01-44a7-9718-b3f0ef83b8f0.xml
f1_keywords:
 - "ntifs/RtlOemStringToCountedUnicodeString"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlOemStringToCountedUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlOemStringToCountedUnicodeString function


## -description


The <b>RtlOemStringToCountedUnicodeString</b> routine translates the specified source string into a Unicode string using the current system OEM code page. 


## -parameters




### -param DestinationString

Pointer to a caller-allocated buffer to receive the translated Unicode string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the Unicode data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlOemStringToCountedUnicodeString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly. 


### -param SourceString [in]

Pointer to the OEM string to be translated into Unicode. 


### -param AllocateDestinationString [in]

Set to <b>TRUE</b> if <b>RtlOemStringToCountedUnicodeString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeUnicodeString</b>. 


## -returns



If the operation succeeds, <b>RtlOemStringToCountedUnicodeString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated and no conversion was done. 




## -remarks



<b>RtlOemStringToCountedUnicodeString</b> returns a translated string that does not include NULL terminator. It translates the given source string using the OEM code page that was installed as the current system code page at boot time. 

<b>RtlOemStringToCountedUnicodeString</b> does not modify the source string. 

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff558741(v=vs.85)">OEM_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtocountedunicodesize">RtlOemStringToCountedUnicodeSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtocountedunicodestring">RtlOemStringToCountedUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemtounicoden">RtlOemToUnicodeN</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

