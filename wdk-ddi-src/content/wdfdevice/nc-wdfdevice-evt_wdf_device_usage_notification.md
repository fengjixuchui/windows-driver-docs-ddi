---
UID: NC:wdfdevice.EVT_WDF_DEVICE_USAGE_NOTIFICATION
title: EVT_WDF_DEVICE_USAGE_NOTIFICATION (wdfdevice.h)
description: A driver's EvtDeviceUsageNotification event callback function informs the driver when a device is being used for special files.
old-location: wdf\evtdeviceusagenotification.htm
tech.root: wdf
ms.assetid: b6b7dd80-fd91-4194-8288-4d703983a798
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_bbf01697-e3d0-4711-aa7f-c53bfd205ea7.xml, EVT_WDF_DEVICE_USAGE_NOTIFICATION, EVT_WDF_DEVICE_USAGE_NOTIFICATION callback, EvtDeviceUsageNotification, EvtDeviceUsageNotification callback function, kmdf.evtdeviceusagenotification, wdf.evtdeviceusagenotification, wdfdevice/EvtDeviceUsageNotification
ms.topic: callback
f1_keywords:
 - "wdfdevice/EvtDeviceUsageNotification"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- Wdfdevice.h
api_name:
- EvtDeviceUsageNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_USAGE_NOTIFICATION callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceUsageNotification</i> event callback function informs the driver when a device is being used for special files.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param NotificationType [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_special_file_type">WDF_SPECIAL_FILE_TYPE</a>-typed value that identifies the type of special file that the system is storing on the specified device.


### -param IsInNotificationPath [in]

A Boolean value which, if <b>TRUE</b>, indicates that the system has starting using the special file and, if <b>FALSE</b>, indicate that the system as finished using the special file.


## -remarks



To register an <i>EvtDeviceUsageNotification</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

Your driver must provide an <i>EvtDeviceUsageNotification</i> callback function only if must provide driver-specific handling of special files. 

For more information about special files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-special-files">Supporting Special Files</a>.


#### Examples

To define an <i>EvtDeviceUsageNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceUsageNotification</i> callback function that is named <i>MyDeviceUsageNotification</i>, use the <b>EVT_WDF_DEVICE_USAGE_NOTIFICATION</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_USAGE_NOTIFICATION  MyDeviceUsageNotification;</pre>
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
VOID
 MyDeviceUsageNotification (
    WDFDEVICE  Device,
    WDF_SPECIAL_FILE_TYPE NotificationType,
    BOOLEAN  IsInNotificationPath
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_USAGE_NOTIFICATION</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_USAGE_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.



