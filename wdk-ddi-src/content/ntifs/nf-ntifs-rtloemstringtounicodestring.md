---
UID: NF:ntifs.RtlOemStringToUnicodeString
title: RtlOemStringToUnicodeString function (ntifs.h)
description: The RtlOemStringToUnicodeString routine translates a given source string into a null-terminated Unicode string using the current system OEM code page.
old-location: ifsk\rtloemstringtounicodestring.htm
tech.root: ifsk
ms.assetid: 0420718f-3d0f-4f15-85ec-c2cdfa930023
ms.date: 04/16/2018
ms.keywords: RtlOemStringToUnicodeString, RtlOemStringToUnicodeString routine [Installable File System Drivers], ifsk.rtloemstringtounicodestring, ntifs/RtlOemStringToUnicodeString, rtlref_6b1f3210-6b02-4f20-9887-b7efd0090b7f.xml
ms.topic: function
f1_keywords:
 - "ntifs/RtlOemStringToUnicodeString"
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
- RtlOemStringToUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlOemStringToUnicodeString function


## -description


The <b>RtlOemStringToUnicodeString</b> routine translates a given source string into a null-terminated Unicode string using the current system OEM code page. 


## -parameters




### -param DestinationString

Pointer to a caller-allocated buffer to receive the translated string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the null-terminated Unicode string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlOemStringToUnicodeString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly. 


### -param SourceString [in]

Pointer to the OEM string to be translated to Unicode. 


### -param AllocateDestinationString [in]

Set to <b>TRUE</b> if <b>RtlOemStringToUnicodeString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeUnicodeString</b>. 


## -returns



<b>RtlOemStringToUnicodeString</b> returns STATUS_SUCCESS if it returns a translated string at <i>DestinationString</i>. Otherwise, no storage was allocated and no conversion was done. 




## -remarks



<b>RtlOemStringToUnicodeString</b> translates the given source string using the OEM code page that was installed as the current system code page at system boot time. 

This routine does not modify the source string. It returns a NULL-terminated Unicode string. 

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff558741(v=vs.85)">OEM_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtloemstringtocountedunicodestring">RtlOemStringToCountedUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtloemstringtounicodesize">RtlOemStringToUnicodeSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtloemtounicoden">RtlOemToUnicodeN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlunicodestringtooemstring">RtlUnicodeStringToOemString</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

