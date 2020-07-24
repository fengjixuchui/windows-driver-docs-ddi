---
UID: NF:ntstrsafe.RtlStringCbCatNW
title: RtlStringCbCatNW function (ntstrsafe.h)
description: The RtlStringCbCatNW and RtlStringCbCatNA functions concatenate two byte-counted strings while limiting the size of the appended string.
old-location: kernel\rtlstringcbcatn.htm
tech.root: kernel
ms.assetid: 60ecabb1-5607-4962-82c6-8081916b507d
ms.date: 04/30/2018
keywords: ["RtlStringCbCatNW function"]
ms.keywords: RtlStringCbCatN, RtlStringCbCatNA, RtlStringCbCatNW, RtlStringCbCatNW function [Kernel-Mode Driver Architecture], kernel.rtlstringcbcatn, ntstrsafe/RtlStringCbCatNA, ntstrsafe/RtlStringCbCatNW, safestrings_3f453d8e-bae5-466f-a55a-2b6a68d5cb57.xml
f1_keywords:
 - "ntstrsafe/RtlStringCbCatNW"
 - "RtlStringCbCatNW"
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbCatNW (Unicode) and RtlStringCbCatNA (ANSI)
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
- RtlStringCbCatNW
- RtlStringCbCatNA
- RtlStringCbCatNW
targetos: Windows
req.typenames: 
---

# RtlStringCbCatNW function


## -description


The <b>RtlStringCbCatNW</b> and <b>RtlStringCbCatNA</b> functions concatenate two byte-counted strings while limiting the size of the appended string. 


## -parameters




### -param pszDest [in, out]

Pointer to a buffer which, on input, contains a null-terminated string to which <i>pszSrc</i> will be concatenated. On output, this is the destination buffer that contains the entire resultant string. The string at <i>pszSrc</i>, up to <i>cbMaxAppend</i> bytes, is added to the end of the string at <i>pszDest</i> and terminated with a null character.


### -param cbDest [in]

The size of the destination buffer, in bytes. The buffer must be large enough to include both strings and the terminating null character.

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). 


### -param pszSrc [in]

Pointer to a null-terminated string. This string will be concatenated to the end of the string that is contained in the buffer at <i>pszDest</i>. 


### -param cbToAppend

<p>The maximum number of bytes to append to the string that is contained in the buffer at <i>pszDest</i>.</p>




## -returns



The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.

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
This <i>success</i> status means source data was present, the strings were concatenated without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the concatenation operation did not complete due to insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

<ul>
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer's length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>RtlStringCbCatNW</b> and <b>RtlStringCbCatNA</b> should be used instead of the following functions: 

<ul>
<li>
<b>strncat</b>

</li>
<li>
<b>wcsncat</b>

</li>
</ul>
The size, in bytes, of the destination buffer is provided to <b>RtlStringCbCatNW</b> and <b>RtlStringCbCatNA</b> to ensure that they do not write past the end of the buffer.

Use <b>RtlStringCbCatNW</b> to handle Unicode strings and <b>RtlStringCbCatNA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table

<table>
<tr>
<th>String data type</th>
<th>String literal</th>
<th>Function</th>
</tr>
<tr>
<td>
WCHAR

</td>
<td>
L"string"

</td>
<td>
<b>RtlStringCbCatNW</b>

</td>
</tr>
<tr>
<td>
<b>char</b>

</td>
<td>
"string"

</td>
<td>
<b>RtlStringCbCatNA</b>

</td>
</tr>
</table>
 

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcatnexa">RtlStringCbCatNEx</a>.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcata">RtlStringCbCat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcatnexa">RtlStringCbCatNEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchcatna">RtlStringCchCatN</a>
 

 

