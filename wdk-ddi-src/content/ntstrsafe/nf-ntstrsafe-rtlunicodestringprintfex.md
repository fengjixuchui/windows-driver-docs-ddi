---
UID: NF:ntstrsafe.RtlUnicodeStringPrintfEx
title: RtlUnicodeStringPrintfEx function (ntstrsafe.h)
description: The RtlUnicodeStringPrintfEx function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringprintfex.htm
tech.root: kernel
ms.assetid: 8a08cb8d-d933-4dc6-8bf2-8f435ffc9eb1
ms.date: 04/30/2018
ms.keywords: RtlUnicodeStringPrintfEx, RtlUnicodeStringPrintfEx function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringprintfex, ntstrsafe/RtlUnicodeStringPrintfEx, safestrings_06495952-554e-4e33-8610-dc34b7f1b879.xml
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows XP with Service Pack 1 (SP1).
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
- RtlUnicodeStringPrintfEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringPrintfEx function


## -description


The <b>RtlUnicodeStringPrintfEx</b> function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure.


## -parameters




### -param DestinationString [out]

Optional. A pointer to a <b>UNICODE_STRING</b> structure that receives a formatted string. <b>RtlUnicodeStringPrintfEx</b> creates this string from both the formatting string that <i>pszFormat</i> specifies and the function's argument list. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH. <i>DestinationString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param RemainingString [out, optional]

Optional. If the caller supplies a non-<b>NULL</b> pointer to a <b>UNICODE_STRING</b> structure, <b>RtlUnicodeStringPrintfEx</b> sets this structure's <b>Buffer</b> member to the end of the formatted string, sets the structure's <b>Length</b> member to zero, and sets the structure's <b>MaximumLength</b> member to the number of bytes that are remaining in the destination buffer. <i>RemainingString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param dwFlags [in]

One or more flags and, optionally, a fill byte. The flags are defined as follows:





#### STRSAFE_FILL_BEHIND

If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the last character in the string.



#### STRSAFE_IGNORE_NULLS

If this flag is set, the source or destination pointer, or both, can be <b>NULL</b>. <b>RtlUnicodeStringPrintfEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")), which can be copied. <b>NULL</b> destination buffer pointers cannot receive nonempty strings.



#### STRSAFE_FILL_ON_FAILURE

If this flag is set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer. This operation overwrites any preexisting buffer contents.



#### STRSAFE_NULL_ON_FAILURE

If this flag is set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents.



#### STRSAFE_NO_TRUNCATION

If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.



#### STRSAFE_ZERO_LENGTH_ON_FAILURE

If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the destination string length is set to zero bytes.


### -param pszFormat [in]

A pointer to a null-terminated text string that contains <b>printf</b>-styled formatting directives. This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param param

<p>Optional. A list of arguments that <b>RtlUnicodeStringPrintfEx</b> interprets, based on formatting directives that the <i>pszFormat</i> string specifies.</p>




####### - ...

Optional. A list of arguments that <b>RtlUnicodeStringPrintfEx</b> interprets, based on formatting directives that the <i>pszFormat</i> string specifies.


## -returns



<b>RtlUnicodeStringPrintfEx</b> returns one of the following NTSTATUS values. 

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
This <i>success</i> status means source data was present, and the strings were concatenated without truncation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means that the operation did not complete because of insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the copied string.

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
 

<b>RtlUnicodeStringPrintfEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of a <b>UNICODE_STRING</b> structure are invalid.</li>
<li>An invalid flag is specified in <i>dwFlags</i>.</li>
<li>The destination buffer is already full.</li>
<li>A buffer pointer is <b>NULL</b> and the STRSAFE_IGNORE_NULLS flag is not specified in <i>dwFlags</i>.</li>
<li>The destination buffer pointer is <b>NULL</b>, but the buffer size is not zero.</li>
<li>The destination buffer pointer is <b>NULL</b>, or its length is zero, but a nonzero length source string is present.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.




## -remarks



The <b>RtlUnicodeStringPrintfEx</b> function uses the destination buffer's size to ensure that the string formatting operation does not write past the end of the buffer. By default, the function does <u>not</u> terminate the resultant string with a null character value (that is, with zero). As an option, the caller can use the STRSAFE_FILL_BEHIND flag and a fill byte value of zero to null-terminate a resultant string that does not occupy the entire destination buffer.

<b>RtlUnicodeStringPrintfEx</b> adds to the functionality of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringprintf">RtlUnicodeStringPrintf</a> function by returning a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that identifies the end of the destination string and the number of bytes that are left unused in that string. You can pass flags to <b>RtlUnicodeStringPrintfEx</b> for additional control.

If the format string and the destination string overlap, the behavior of the function is undefined.

The <i>pszFormat</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set in <i>dwFlags</i>. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be <b>NULL</b>. If the <i>DestinationString</i> pointer is <b>NULL</b>, the <i>pszFormat</i> pointer must either be <b>NULL</b> or point to an empty string.

For more information about the safe string functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringprintf">RtlUnicodeStringPrintf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringvprintf">RtlUnicodeStringVPrintf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringvprintfex">RtlUnicodeStringVPrintfEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

