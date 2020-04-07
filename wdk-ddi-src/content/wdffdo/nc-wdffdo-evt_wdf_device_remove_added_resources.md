---
UID: NC:wdffdo.EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES
title: EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES (wdffdo.h)
description: A driver's EvtDeviceRemoveAddedResources event callback function removes hardware resources that the driver's EvtDeviceFilterAddResourceRequirements callback function added.
old-location: wdf\evtdeviceremoveaddedresources.htm
tech.root: wdf
ms.assetid: b18c2b34-db6d-4553-9340-556da1fd7991
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES callback function"]
ms.keywords: DFDeviceObjectFdoPdoRef_c1020fff-8895-4ece-ae27-ef33d3a65de6.xml, EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES, EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES callback, EvtDeviceRemoveAddedResources, EvtDeviceRemoveAddedResources callback function, kmdf.evtdeviceremoveaddedresources, wdf.evtdeviceremoveaddedresources, wdffdo/EvtDeviceRemoveAddedResources
f1_keywords:
 - "wdffdo/EvtDeviceRemoveAddedResources"
req.header: wdffdo.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdffdo.h
api_name:
- EvtDeviceRemoveAddedResources
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceRemoveAddedResources</i> event callback function removes hardware resources that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterAddResourceRequirements</a> callback function added.


## -parameters




### -param Device [in]

A handle to the framework device object to which resources will be assigned.


### -param ResourcesRaw [in]

A handle to a resource list object that identifies the raw hardware resources that the PnP manager has assigned to the device. 


### -param ResourcesTranslated [in]

A handle to a resource list object that identifies the translated hardware resources that the PnP manager has assigned to the device. 


## -returns



If the driver encountered no errors it must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a> evaluates as <b>FALSE</b>.

For more information about return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.




## -remarks



Framework-based function drivers can provide an <i>EvtDeviceRemoveAddedResources</i> callback function. To register this callback function, drivers call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitseteventcallbacks">WdfFdoInitSetEventCallbacks</a>.

If a driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterAddResourceRequirements</a> callback function that adds resources to a device's hardware requirements list, the driver must also provide an <i>EvtDeviceRemoveAddedResources</i> callback function. The <i>EvtDeviceRemoveAddedResources</i> callback function examines the resource list that the PnP manager has assigned to the device, and removes the resources from the list that the <i>EvtDeviceFilterAddResourceRequirements</i> callback function added. If the driver removes a resource, it must remove it from both the raw and translated resource lists.

For more information about resource lists and the order in which the resources appear, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/raw-and-translated-resources">raw and translated hardware resources</a>.

The framework calls the driver's <i>EvtDeviceRemoveAddedResources</i> callback function immediately before it passes the device's resource list to the bus driver. This callback function removes added resources so that the bus driver will not attempt to use them. 

For more information about the <i>EvtDeviceRemoveAddedResources</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/modifying-a-resource-list">Modifying a Resource List</a>.

For more information about hardware resources, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

To define an <i>EvtDeviceRemoveAddedResources</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceRemoveAddedResources</i> callback function that is named <i>MyDeviceRemoveAddedResources</i>, use the <b>EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES  MyDeviceRemoveAddedResources;</pre>
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
<pre>_Use_decl_annotations_
NTSTATUS
 MyDeviceRemoveAddedResources (
    WDFDEVICE  Device,
    WDFCMRESLIST  ResourcesRaw,
    WDFCMRESLIST  ResourcesTranslated
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES</b> function type is defined in the Wdffdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterAddResourceRequirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nc-wdffdo-evt_wdf_device_filter_resource_requirements">EvtDeviceFilterRemoveResourceRequirements</a>
 

 

