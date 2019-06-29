---
UID: NF:hidpi.HidP_GetUsageValueArray
title: HidP_GetUsageValueArray function (hidpi.h)
description: The HidP_GetUsageValueArray routine extracts the data associated with a HID control usage value array from a HID report.
old-location: hid\hidp_getusagevaluearray.htm
tech.root: hid
ms.assetid: afc92692-c665-44a7-b268-d29adc42f5bd
ms.date: 04/30/2018
ms.keywords: HidP_GetUsageValueArray, HidP_GetUsageValueArray routine [Human Input Devices], hid.hidp_getusagevaluearray, hidfunc_4e641f34-d016-4b2f-b472-069334d3e461.xml, hidpi/HidP_GetUsageValueArray
ms.topic: function
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hidparse.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hidparse.lib
- Hidparse.dll
api_name:
- HidP_GetUsageValueArray
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_GetUsageValueArray function


## -description


The <b>HidP_GetUsageValueArray</b> routine extracts the data associated with a HID control <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/value-capability-arrays">usage value array</a> from a HID report.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param UsagePage [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">usage page</a> of the usage value array.


### -param LinkCollection [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/link-collections">link collection</a> that contains the usage value array. If <i>LinkCollection</i> is nonzero, the routine only searches for a usage value array in this link collection; otherwise, if <i>LinkCollection</i> is zero, the routine searches for a usage value array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> associated with <i>PreparsedData</i>.


### -param Usage [in]

Specifies the usage of the usage value array.


### -param UsageValue [in, out]

Pointer to a caller-allocated buffer in which the routine returns the data associated with the usage value array.


### -param UsageValueByteLength [in]

Specifies the length, in bytes, of the buffer at <i>UsageValue</i>.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.


### -param Report [in]

Pointer to a report that contains values.


### -param ReportLength [in]

Specifies the length, in bytes, of the report located at <i>Report</i>.


## -returns



<b>HidP_GetUsageValueArray </b>returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully returned the value's data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_INVALID_REPORT_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The report length is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_INVALID_REPORT_TYPE</b></dt>
</dl>
</td>
<td width="60%">
The specified report type is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_NOT_VALUE_ARRAY</b></dt>
</dl>
</td>
<td width="60%">
The requested usage is not a usage value array.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>UsageValue</i> buffer is too small to hold the requested usage. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>
</td>
<td width="60%">
The collection contains a usage value array on the specified usage page in a report of the specified type, but there are no such usages in the specified report.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>
</td>
<td width="60%">
The preparsed data is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_USAGE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The collection does not contain a usage value array on the specified usage page in any report of the specified report type.

</td>
</tr>
</table>
 




## -remarks



The required size, in bytes, of <i>UsageValueByteLength</i> is determined by multiplying together the <b>BitSize</b> and <b>ReportCount</b> members of the usage value array's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_value_caps">HIDP_VALUE_CAPS</a> structure, and rounding the result up to the nearest byte.

<b>HidP_GetUsageValueArray</b> sets the <i>UsageValue</i> buffer in little-endian order, beginning with the least significant bit of the usage's data. The data is not byte-aligned, and is shifted such that the least significant bit of the data is located at the first bit of the <i>UsageValue</i> buffer.

<b>HidP_GetUsageValueArray</b> is designed to extract all the usage values for a usage whose report count is greater than 1. To extract a usage whose report count is equal to 1, use <b>HidP_GetUsageValue</b>. 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_value_caps">HIDP_VALUE_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_GetButtons</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_GetButtonsEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getscaledusagevalue">HidP_GetScaledUsageValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getusagevalue">HidP_GetUsageValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getusages">HidP_GetUsages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getusagesex">HidP_GetUsagesEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

