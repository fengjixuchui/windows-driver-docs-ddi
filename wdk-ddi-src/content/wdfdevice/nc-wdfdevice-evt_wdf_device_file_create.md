---
UID: NC:wdfdevice.EVT_WDF_DEVICE_FILE_CREATE
title: EVT_WDF_DEVICE_FILE_CREATE (wdfdevice.h)
description: A driver's EvtDeviceFileCreate callback function handles operations that must be performed when an application requests access to a device.
old-location: wdf\evtdevicefilecreate.htm
tech.root: wdf
ms.assetid: ee44c0bf-1fca-442d-8871-df6079e89ced
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_FILE_CREATE callback function"]
ms.keywords: DFDeviceObjectGeneralRef_74ee41b0-ed8c-4028-8f82-d747a4d916bb.xml, EVT_WDF_DEVICE_FILE_CREATE, EVT_WDF_DEVICE_FILE_CREATE callback, EvtDeviceFileCreate, EvtDeviceFileCreate callback function, kmdf.evtdevicefilecreate, wdf.evtdevicefilecreate, wdfdevice/EvtDeviceFileCreate
f1_keywords:
 - "wdfdevice/EvtDeviceFileCreate"
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
- EvtDeviceFileCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_FILE_CREATE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceFileCreate</i> callback function handles operations that must be performed when an application requests access to a device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Request [in]

A handle to a framework request object that represents a file creation request.


### -param FileObject [in]

A handle to a framework file object that describes a file that is being opened for the specified request. This parameter is <b>NULL</b> if the driver has specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_fileobject_class">WdfFileObjectNotRequired</a> for the <b>FileObjectClass </b>member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a> structure.


## -remarks



The framework calls a driver's <i>EvtDeviceFileCreate</i> callback function when a user application or another driver opens the device to perform an I/O operation, such as reading or writing a file. 

The driver can pass the <i>Request</i> handle to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a> to retrieve parameters that are associated with the file creation request. The parameters are stored in the <b>Parameters.Create</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> structure. 

This callback function is called synchronously, in the context of the thread that opens the device. 

To register an <i>EvtDeviceFileCreate</i> callback function, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a> method.

The driver must either complete the request or send it with [**WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_send_options_flags).

Alternatively, the driver can receive create requests in a queue. For more info, see [**WdfDeviceConfigureRequestDispatching**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurerequestdispatching).

For more information about framework file objects and the <i>EvtDeviceFileCreate</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.


#### Examples

To define an <i>EvtDeviceFileCreate</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceFileCreate</i> callback function that is named <i>MyDeviceFileCreate</i>, use the <b>EVT_WDF_DEVICE_FILE_CREATE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_FILE_CREATE  MyDeviceFileCreate;</pre>
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
 MyDeviceFileCreate (
    WDFDEVICE  Device,
    WDFREQUEST  Request,
    WDFFILEOBJECT  FileObject
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_FILE_CREATE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_FILE_CREATE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a>
 

 

