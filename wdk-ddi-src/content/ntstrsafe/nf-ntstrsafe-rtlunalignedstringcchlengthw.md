---
UID: NF:ntstrsafe.RtlUnalignedStringCchLengthW
title: RtlUnalignedStringCchLengthW function (ntstrsafe.h)
description: The RtlUnalignedStringCchLengthW function is a version of the RtlStringCchLength function that accepts an unaligned pointer to a string of Unicode characters.
old-location: kernel\rtlunalignedstringcchlength.htm
tech.root: kernel
ms.assetid: 7b9f38f5-7fc9-4670-975d-b7bfeefb2cb8
ms.date: 04/30/2018
ms.keywords: RtlUnalignedStringCchLength, RtlUnalignedStringCchLengthW, RtlUnalignedStringCchLengthW function [Kernel-Mode Driver Architecture], kernel.rtlunalignedstringcchlength, ntstrsafe/RtlUnalignedStringCchLengthW, safestrings_7bfc07f7-2096-4818-a0d5-31767b7342ea.xml
ms.topic: function
f1_keywords:
 - "ntstrsafe/RtlUnalignedStringCchLengthW"
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
- RtlUnalignedStringCchLengthW
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnalignedStringCchLengthW function


## -description


The <b>RtlUnalignedStringCchLengthW</b> function is a version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcchlengtha">RtlStringCchLength</a> function that accepts an unaligned pointer to a string of Unicode characters.


## -parameters




### -param psz [in]

Supplies a pointer to a buffer that contains a null-terminated string whose length <b>RtlUnalignedStringCchLengthW</b> will check. 


### -param cchMax [in]

Supplies the maximum number of characters that are allowed in the buffer that <i>psz</i> points to, including the terminating NULL character. This value cannot exceed NTSTRSAFE_MAX_CCH. 


### -param pcchLength [out, optional]

Optional. If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the length, in characters, of the string that is contained in the buffer that <i>psz</i> points to. The length does not include the string's terminating NULL character.


## -returns



<b>RtlUnalignedStringCchLengthW</b> returns one of the following NTSTATUS values. 

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
This <i>success</i> status means the string that the <i>psz</i> parameter was not <b>NULL</b>, and the length of the string (including the terminating NULL character) was less than or equal to <i>cchMax</i> characters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means the value in <i>psz</i> is <b>NULL</b>, <i>cchMax</i> is larger than NTSTRSAFE_MAX_CCH, or <i>psz</i> is longer than <i>cchMax</i>.

</td>
</tr>
</table>
 

For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnalignedStringCchLengthW</b> function is available for processor architectures, such as Itanium-based and x64-based, that cause alignment exceptions when software attempts to access unaligned data. On those processors, you can use <b>RtlUnalignedStringCchLengthW</b> instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcchlengtha">RtlStringCchLength</a> to avoid alignment exceptions. (For processors that do not cause alignment exceptions, <b>RtlUnalignedStringCchLengthW</b> is equivalent to <b>RtlStringCchLength</b>.)

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlstringcchlengtha">RtlStringCchLength</a>
 

 

