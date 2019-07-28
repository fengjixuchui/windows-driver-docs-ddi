---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE
title: EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE (wdfchildlist.h)
description: A driver's EvtChildListIdentificationDescriptionCompare event callback function compares one child identification description with another.
old-location: wdf\evtchildlistidentificationdescriptioncompare.htm
tech.root: wdf
ms.assetid: b807f9f8-588f-4303-be97-a9fd4cff2bbd
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_58ed75b3-f129-4cfb-8d36-577b1cb8ffa0.xml, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE callback, EvtChildListIdentificationDescriptionCompare, EvtChildListIdentificationDescriptionCompare callback function, kmdf.evtchildlistidentificationdescriptioncompare, wdf.evtchildlistidentificationdescriptioncompare, wdfchildlist/EvtChildListIdentificationDescriptionCompare
ms.topic: callback
f1_keywords:
 - "wdfchildlist/EvtChildListIdentificationDescriptionCompare"
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfChildlist.h
api_name:
- EvtChildListIdentificationDescriptionCompare
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtChildListIdentificationDescriptionCompare</i> event callback function compares one child identification description with another.


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


### -param FirstIdentificationDescription [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the one child identification description.


### -param SecondIdentificationDescription [in]

A pointer to a WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure that identifies another child identification description.


## -returns



The <i>EvtChildListIdentificationDescriptionCompare</i> callback function must return <b>TRUE</b> if the two child identification descriptions match. Otherwise, this function must return <b>FALSE</b>.




## -remarks



If a bus driver is using <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListIdentificationDescriptionCompare</i> callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>. The driver can also register a second, special-case <i>EvtChildListIdentificationDescriptionCompare</i> callback function when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>.

The framework compares two identification descriptions when it must determine if both descriptions identify the same device.

The <i>EvtChildListIdentificationDescriptionCompare</i> callback function must compare the contents of two identification descriptions and return <b>TRUE</b> if they match. A driver must supply this callback function if the framework cannot call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcomparememory">RtlCompareMemory</a> to compare the identification descriptions. (The framework cannot call <b>RtlCompareMemory</b> if the descriptions contain pointers to additional memory.)

If your driver does not provide an <i>EvtChildListIdentificationDescriptionCompare</i> callback function, the framework compares identification descriptions by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcomparememory">RtlCompareMemory</a>.

The following steps describe a possible scenario:

<ol>
<li>
The driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a> to obtain the address description that is associated with the framework's copy of an identification description, which is stored in a child list.

</li>
<li>
The framework traverses the child list. To determine if a child's identification description matches the one that the driver specified when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a>, the framework calls either the <i>EvtChildListIdentificationDescriptionCompare</i> callback function (if it exists) or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcomparememory">RtlCompareMemory</a>.

</li>
<li>
If the two identification descriptions match (and the comparison returns <b>TRUE</b>), the framework stops traversing the list.

</li>
<li>
The framework copies the address description into memory that the driver supplied when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a>.

</li>
</ol>
The framework can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcomparememory">RtlCompareMemory</a> to compare identification descriptions, if each description consists of a single structure with a predetermined size that is specified by the <b>IdentificationDescriptionSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure. However, sometimes the description must also contain additional information that is stored in dynamically allocated memory. In this case, you will typically define a description structure so that a member points to the dynamically allocated memory, and your driver must provide an <i>EvtChildListIdentificationDescriptionCompare</i> callback function. 

This callback function determines if two identification descriptions represent the same device. The callback function might not have to compare all of the structure members to make that determination. For example, suppose that an identification description contains a serial number and a set of hardware identifiers, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _PDO_IDENTIFICATION_DESCRIPTION {
  WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER Header;
  ULONG DeviceSerialNumber;
  ULONG CchHardwareIds;
  PWCHAR HardwareIds;
} PDO_IDENTIFICATION_DESCRIPTION, *PPDO_IDENTIFICATION_DESCRIPTION;</pre>
</td>
</tr>
</table></span></div>
In this case, the <i>EvtChildListIdentificationDescriptionCompare</i> callback function probably has to compare only the <b>DeviceSerialNumber</b> members to determine if two descriptions represent the same device.

If your driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a> to traverse a device list, you can provide an additional <i>EvtChildListIdentificationDescriptionCompare</i> callback function that the framework uses when looking for the next description to retrieve. The framework looks for child devices that match driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ne-wdfchildlist-_wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a>-typed flags. If a driver provides a special <i>EvtChildListIdentificationDescriptionCompare</i> callback function, the framework uses the callback function to refine the search. If the driver does not supply a special <i>EvtChildListIdentificationDescriptionCompare</i> callback function, the framework does <i>not</i> call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcomparememory">RtlCompareMemory</a>--it simply returns each child device that matches the specified flags. 

The only <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/">framework child-list object method</a> that a driver's <i>EvtChildListIdentificationDescriptionCompare</i> callback function can call is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistgetdevice">WdfChildListGetDevice</a>.

The framework acquires an internal child-list object lock before calling the <i>EvtChildListIdentificationDescriptionCompare</i><i>EvtChildListIdentificationDescriptionCompare</i> callback function. The callback function must only perform operations that are related to the compare operation, such as calling framework memory object methods and accessing object context space. It must not call methods that access other drivers.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

To define an <i>EvtChildListIdentificationDescriptionCompare</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtChildListIdentificationDescriptionCompare</i> callback function that is named <i>MyChildListIdentificationDescriptionCompare</i>, use the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE  MyChildListIdentificationDescriptionCompare;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
_Use_decl_annotations_
BOOLEAN
 MyChildListIdentificationDescriptionCompare (
 WDFCHILDLIST  ChildList,
    PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER  FirstIdentificationDescription,
    PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER  SecondIdentificationDescription
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE</b> function type is defined in the WdfChildlist.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcomparememory">RtlCompareMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ne-wdfchildlist-_wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistgetdevice">WdfChildListGetDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>
 

 

