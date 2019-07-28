---
UID: NF:wdffdo.WdfFdoInitSetEventCallbacks
title: WdfFdoInitSetEventCallbacks function (wdffdo.h)
description: The WdfFdoInitSetEventCallbacks method registers a framework-based function driver's event callback functions, for a specified device.
old-location: wdf\wdffdoinitseteventcallbacks.htm
tech.root: wdf
ms.assetid: 0a47ea47-590c-4395-b38e-d1f1fb1929e1
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_3a3fbec9-836c-422e-a921-654fa4866989.xml, WdfFdoInitSetEventCallbacks, WdfFdoInitSetEventCallbacks method, kmdf.wdffdoinitseteventcallbacks, wdf.wdffdoinitseteventcallbacks, wdffdo/WdfFdoInitSetEventCallbacks
ms.topic: function
f1_keywords:
 - "wdffdo/WdfFdoInitSetEventCallbacks"
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfFdoInitSetEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoInitSetEventCallbacks function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfFdoInitSetEventCallbacks</b> method registers a framework-based function driver's event callback functions, for a specified device.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.


### -param FdoEventCallbacks [in]

A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/ns-wdffdo-_wdf_fdo_event_callbacks">WDF_FDO_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



Before calling <b>WdfFdoInitSetEventCallbacks</b>, the driver must allocate a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/ns-wdffdo-_wdf_fdo_event_callbacks">WDF_FDO_EVENT_CALLBACKS</a> structure and fill in the structure with pointers to the driver's event callback functions.

The driver must call <b>WdfFdoInitSetEventCallbacks</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about the <b>WdfFdoInitSetEventCallbacks</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-device-objects-in-a-function-driver">Creating Device Objects in a Function Driver</a>.


#### Examples

The following code example initializes a WDF_FDO_EVENT_CALLBACKS structure and then calls <b>WdfFdoInitSetEventCallbacks</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_FDO_EVENT_CALLBACKS fdoCallbacks;

WDF_FDO_EVENT_CALLBACKS_INIT(&fdoCallbacks);
fdoCallbacks.EvtDeviceFilterAddResourceRequirements = MyEvtDeviceFilterAddResourceRequirements;
fdoCallbacks.EvtDeviceFilterRemoveResourceRequirements = MyEvtDeviceFilterRemoveResourceRequirements;
fdoCallbacks.EvtDeviceRemoveAddedResources = MyEvtDeviceRemoveAddedResources;

WdfFdoInitSetEventCallbacks(
                            DeviceInit,
                            &fdoCallbacks
                            );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdf_fdo_event_callbacks_init">WDF_FDO_EVENT_CALLBACKS_INIT</a>
 

 

