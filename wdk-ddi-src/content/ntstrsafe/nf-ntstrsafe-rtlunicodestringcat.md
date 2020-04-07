---
UID: NF:ntstrsafe.RtlUnicodeStringCat
title: RtlUnicodeStringCat function (ntstrsafe.h)
description: The RtlUnicodeStringCat function concatenates two strings that are contained in UNICODE_STRING structures.
old-location: kernel\rtlunicodestringcat.htm
tech.root: kernel
ms.assetid: 15b9ff74-5ca7-4459-af02-b6dc7cd201bf
ms.date: 04/30/2018
keywords: ["RtlUnicodeStringCat function"]
ms.keywords: RtlUnicodeStringCat, RtlUnicodeStringCat function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringcat, ntstrsafe/RtlUnicodeStringCat, safestrings_5d3ef5c7-f2cd-4de8-a043-5474c803183c.xml
f1_keywords:
 - "ntstrsafe/RtlUnicodeStringCat"
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
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
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ntstrsafe.lib
- Ntstrsafe.dll
api_name:
- RtlUnicodeStringCat
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringCat function


## -description


The <b>RtlUnicodeStringCat</b> function concatenates two strings that are contained in <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structures.


## -parameters




### -param DestinationString [in, out]

A pointer to a <b>UNICODE_STRING</b> structure. This structure includes a buffer that, on input, contains a destination string to which the source string will be concatenated. On output, this buffer is the destination buffer that contains the entire resultant string. The source string is added to the end of the destination string. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).


### -param SourceString [in]

A pointer to a <b>UNICODE_STRING</b> structure. This structure includes a buffer that contains the source string. This string will be added to the end of the destination string. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).


## -returns



<b>RtlUnicodeStringCat</b> returns one of the following NTSTATUS values. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
This <i>success</i> status means that source data was present, the strings were concatenated without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means that the concatenation operation did not complete because of insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.

</td>
</tr>
</table>
 

<b>RtlUnicodeStringCat</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of a <b>UNICODE_STRING</b> structure are invalid.</li>
<li>The destination buffer is already full.</li>
<li>A buffer pointer is <b>NULL</b>.</li>
<li>The destination buffer's length is zero, but a nonzero length source string is present.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringCat</b> function uses the destination buffer's size to ensure that the concatenation operation does not write past the end of the buffer. The function does <u>not</u> terminate the resultant string with a null character value (that is, with zero).

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcatex">RtlUnicodeStringCatEx</a>.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlunicodestringcatex">RtlUnicodeStringCatEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

