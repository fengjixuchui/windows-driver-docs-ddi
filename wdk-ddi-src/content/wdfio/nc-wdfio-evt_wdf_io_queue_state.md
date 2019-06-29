---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_STATE
title: EVT_WDF_IO_QUEUE_STATE (wdfio.h)
description: A driver's EvtIoQueueState event callback function delivers queue state information to the driver.
old-location: wdf\evtioqueuestate.htm
tech.root: wdf
ms.assetid: 14999036-c137-4056-b6f7-53a8476fd385
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_726524eb-d12b-451c-aa6e-3f60aa9b7940.xml, EVT_WDF_IO_QUEUE_STATE, EVT_WDF_IO_QUEUE_STATE callback, EvtIoQueueState, EvtIoQueueState callback function, kmdf.evtioqueuestate, wdf.evtioqueuestate, wdfio/EvtIoQueueState
ms.topic: callback
req.header: wdfio.h
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfio.h
api_name:
- EvtIoQueueState
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_QUEUE_STATE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoQueueState</i> event callback function delivers queue state information to the driver.


## -parameters




### -param Queue [in]

A handle to an I/O queue object.


### -param Context [in]

Driver-defined context information that the driver specified when it registered the <i>EvtIoQueueState</i> callback function.


## -returns



None




## -remarks



Drivers can register an <i>EvtIoQueueState</i> callback function by specifying its address as input to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuestop">WdfIoQueueStop</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuedrain">WdfIoQueueDrain</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuereadynotify">WdfIoQueueReadyNotify</a>. The framework calls the <i>EvtIoQueueState</i> callback function after the specified operation completes. 

The <i>EvtIoQueueState</i> callback function can be called at IRQL <= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the queue's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> is set to <b>WdfExecutionLevelPassive</b>, in which case it is called at IRQL = PASSIVE_LEVEL. If the queue specifies <b>WdfExecutionLevelInheritFromParent</b>, the property can be inherited from the WDFDEVICE or WDFDRIVER's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">critical region</a>.


#### Examples

To define an <i>EvtIoQueueState</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoQueueState</i> callback function that is named <i>MyIoQueueState</i>, use the <b>EVT_WDF_IO_QUEUE_STATE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_QUEUE_STATE  MyIoQueueState;</pre>
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
 MyIoQueueState (
    WDFQUEUE  Queue,
    WDFCONTEXT  Context
    )
 {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_QUEUE_STATE</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_STATE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuedrain">WdfIoQueueDrain</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuereadynotify">WdfIoQueueReadyNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuestop">WdfIoQueueStop</a>
 

 

