---
UID: NF:hidpi.HidP_GetButtonCaps
title: HidP_GetButtonCaps function (hidpi.h)
description: The HidP_GetButtonCaps routine returns a button capability array that describes all the HID control buttons in a top-level collection for a specified type of HID report.
old-location: hid\hidp_getbuttoncaps.htm
tech.root: hid
ms.assetid: 228b95b0-1087-422f-a995-809743c6103e
ms.date: 04/30/2018
ms.keywords: HidP_GetButtonCaps, HidP_GetButtonCaps routine [Human Input Devices], hid.hidp_getbuttoncaps, hidfunc_57425ae7-03dd-42b7-b9b3-0581569ab442.xml, hidpi/HidP_GetButtonCaps
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hidparse.lib
- Hidparse.dll
api_name:
- HidP_GetButtonCaps
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_GetButtonCaps function


## -description


The <b>HidP_GetButtonCaps</b> routine returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/button-capability-arrays">button capability array</a> that describes all the HID control buttons in a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> for a specified type of HID report.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param ButtonCaps [out]

Pointer to a caller-allocated buffer that the routine uses to return a button capability array for the specified report type.


### -param ButtonCapsLength [in, out]

Specifies the length on input, in array elements, of the buffer provided at <i>ButtonCaps</i>. On output, this parameter is set to the actual number of elements that the routine returns.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.


## -returns



<b>HidP_GetButtonCaps</b> returns one of the following status values:

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
The routine successfully returned the capability data.

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
</table>
 




## -remarks



<b>HidP_GetButtonCaps</b> returns the capability of all buttons in a top level collection for a specified report type. 

<i>ButtonCapsLength</i> should be set to the value of the <b>Number</b><i>Xxx</i><b>ButtonCaps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>, where <i>Xxx</i> specifies the report type.

To obtain a subset of button capabilities, selected by <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">usage</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">usage page</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/link-collections">link collection</a>, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getspecificbuttoncaps">HidP_GetSpecificButtonCaps</a>.

For more information about a collection's capability, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/obtaining-collection-information">Obtaining Collection Information</a>.

See also <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_button_caps">HIDP_BUTTON_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getspecificbuttoncaps">HidP_GetSpecificButtonCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

