---
UID: NF:hidpi.HidP_UnsetUsages
title: HidP_UnsetUsages function (hidpi.h)
description: The HidP_UnsetUsages routine sets specified HID control button usages OFF (zero) in a HID report.
old-location: hid\hidp_unsetusages.htm
tech.root: hid
ms.assetid: 55dcd9f3-6903-4718-98c2-ee42ee1026e3
ms.date: 04/30/2018
keywords: ["HidP_UnsetUsages function"]
ms.keywords: HidP_UnsetUsages, HidP_UnsetUsages routine [Human Input Devices], hid.hidp_unsetusages, hidfunc_7ffa6677-1a45-4e19-8001-116fbeacf097.xml, hidpi/HidP_UnsetUsages
f1_keywords:
 - "hidpi/HidP_UnsetUsages"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hidparse.lib
- Hidparse.dll
api_name:
- HidP_UnsetUsages
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_UnsetUsages function


## -description


The <b>HidP_UnsetUsages</b> routine sets specified HID control button <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">usages</a> OFF (zero) in a HID report.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that indicates the type of report located at <i>Report</i>.


### -param UsagePage [in]

Specifies the usage page of the usages specified by <i>UsageList</i>.


### -param LinkCollection [in, optional]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/link-collections">link collection</a> that contains the usages. If <i>LinkCollection</i> is nonzero, the routine only sets the usages, if they exist, in this link collection. If <i>LinkCollection</i> is zero, the routine sets the first usage for each usage it finds in the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> associated with <i>PreparsedData</i>.


### -param UsageList [in, out]

Pointer to the array of usages to set to OFF.


### -param UsageLength [in, out]

Specifies, on input, the number of usages in <i>UsageList</i>. See the Remarks section for information about the output value.


### -param PreparsedData [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a> of the top-level collection associated with the report located at <i>Report</i>.


### -param Report [in]

Pointer to a report.


### -param ReportLength [in]

Specifies the size, in bytes, of the report located at <i>Report</i>, which must be equal to the report length for the specified report type that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a> returns in a collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.


## -returns



<b>HidP_UnsetUsages</b> returns HIDP_STATUS_SUCCESS if it successfully sets to OFF all the usages in <i>UsageList</i>.

<b>HidP_UnsetUsages </b>returns one of the following status values if one of the input parameters is not valid:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>
</td>
<td width="60%">
The preparsed data specified by <i>PreparsedData</i> is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The report length is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_REPORT_TYPE</b></dt>
</dl>
</td>
<td width="60%">
The report type is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_REPORT_DOES_NOT_EXIST</b></dt>
</dl>
</td>
<td width="60%">
The collection does not contain a report of the specified type.

</td>
</tr>
</table>
 

<b>HidP_UnsetUsages</b> returns one of the following status values if it was not able to set to OFF one of the usages in <i>UsageList</i>:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUTTON_NOT_PRESSED</b></dt>
</dl>
</td>
<td width="60%">

A usage is already set to OFF.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INCOMPATIBLE_REPORT_ID</b></dt>
</dl>
</td>
<td width="60%">

A usage is not contained in the specified report, but is contained in another report of the specified type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_USAGE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">


The routine did not find a usage in any report of the specified type.

</td>
</tr>
</table>
 




## -remarks



<b>HidP_UnsetUsages</b> sets <i>UsageLength</i> as follows:



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_SetButtons</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setdata">HidP_SetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusages">HidP_SetUsages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hdpi-h-macros">HidP_UnsetButtons</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

