---
UID: NF:ntddk.RtlCompareString
title: RtlCompareString function (ntddk.h)
description: The RtlCompareString routine compares two counted strings.
old-location: kernel\rtlcomparestring.htm
tech.root: kernel
ms.assetid: 59d023d4-a2b4-4183-9572-cb48621c76fb
ms.date: 04/30/2018
keywords: ["RtlCompareString function"]
ms.keywords: RtlCompareString, RtlCompareString routine [Kernel-Mode Driver Architecture], k109_a794007b-a40a-4081-8302-f7426c4ceaef.xml, kernel.rtlcomparestring, ntddk/RtlCompareString
f1_keywords:
 - "ntddk/RtlCompareString"
 - "RtlCompareString"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlCompareString
targetos: Windows
req.typenames: 
---

# RtlCompareString function


## -description


The <b>RtlCompareString</b> routine compares two counted strings. 


## -parameters




### -param String1 [in]

Pointer to the first string.


### -param String2 [in]

Pointer to the second string.


### -param CaseInSensitive [in]

If <b>TRUE</b>, case should be ignored when doing the comparison.


## -returns



<b>RtlCompareString</b> returns a signed value that gives the results of the comparison:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Zero</b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> equals <i>String2</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>< Zero</b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> is less than <i>String2</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>> Zero </b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> is greater than <i>String2</i>.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcompareunicodestring">RtlCompareUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlequalstring">RtlEqualString</a>
 

 

