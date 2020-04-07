---
UID: NC:wdfiotarget.EVT_WDF_IO_TARGET_REMOVE_COMPLETE
title: EVT_WDF_IO_TARGET_REMOVE_COMPLETE (wdfiotarget.h)
description: A driver's EvtIoTargetRemoveComplete event callback function performs operations when the removal of a specified remote I/O target is complete.
old-location: wdf\evtiotargetremovecomplete.htm
tech.root: wdf
ms.assetid: 204f101d-770c-4363-9371-0ee76dfa0b2c
ms.date: 02/26/2018
keywords: ["EVT_WDF_IO_TARGET_REMOVE_COMPLETE callback function"]
ms.keywords: DFIOTargetRef_d0c566ce-1ed7-4adb-9988-bc1751f000e1.xml, EVT_WDF_IO_TARGET_REMOVE_COMPLETE, EVT_WDF_IO_TARGET_REMOVE_COMPLETE callback, EvtIoTargetRemoveComplete, EvtIoTargetRemoveComplete callback function, kmdf.evtiotargetremovecomplete, wdf.evtiotargetremovecomplete, wdfiotarget/EvtIoTargetRemoveComplete
f1_keywords:
 - "wdfiotarget/EvtIoTargetRemoveComplete"
req.header: wdfiotarget.h
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
- WdfIoTarget.h
api_name:
- EvtIoTargetRemoveComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_TARGET_REMOVE_COMPLETE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoTargetRemoveComplete</i> event callback function performs operations when the removal of a specified remote I/O target is complete.


## -parameters




### -param IoTarget [in]

A handle to an I/O target object. 


## -remarks



To register an <i>EvtIoTargetRemoveComplete</i> callback function, place the callback function's address in the I/O target's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure. 

The framework calls your driver's <i>EvtIoTargetRemoveComplete</i> callback function after the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function returns STATUS_SUCCESS, or after the device has been removed unexpectedly (surprise-removed).

A driver's <i>EvtIoTargetRemoveComplete</i> callback function must permanently close the remote I/O target by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetclose">WdfIoTargetClose</a>. Because the target device has been removed, the <i>EvtIoTargetRemoveComplete</i> callback function should also perform any additional target-removal operations that might be necessary, such as releasing system resources that the driver might have allocated when it opened the target.

The <i>EvtIoTargetRemoveComplete</i> callback function is optional. If the driver does not supply this callback function, the framework permanently closes the I/O target.

For more information about the <i>EvtIoTargetRemoveComplete</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state">Controlling a General I/O Target's State</a>.


#### Examples

To define an <i>EvtIoTargetRemoveComplete</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoTargetRemoveComplete</i> callback function that is named <i>MyIoTargetRemoveComplete</i>, use the <b>EVT_WDF_IO_TARGET_REMOVE_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_TARGET_REMOVE_COMPLETE  MyIoTargetRemoveComplete;</pre>
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
 MyIoTargetRemoveComplete (
    WDFIOTARGET  IoTarget
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_TARGET_REMOVE_COMPLETE</b> function type is defined in the WdfIoTarget.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_TARGET_REMOVE_COMPLETE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_canceled">EvtIoTargetRemoveCanceled</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetclose">WdfIoTargetClose</a>
 

 

