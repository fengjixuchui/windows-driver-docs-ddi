---
UID: NC:storport.HW_BUILDIO
title: HW_BUILDIO (storport.h)
description: The HwStorBuildIo routine processes the SRB with unsynchronized access to shared system data structures before passing it to HwStorStartIo.
old-location: storage\hwstorbuildio.htm
tech.root: storage
ms.assetid: ebbb8289-5996-4d99-98b6-e95fd9dc7ec9
ms.date: 03/29/2018
keywords: ["HW_BUILDIO callback function"]
ms.keywords: HW_BUILDIO, HwStorBuildIo, HwStorBuildIo routine [Storage Devices], storage.hwstorbuildio, stormini_3411fed2-32e6-4a3a-a9c3-0bbe0bb514ca.xml, storport/HwStorBuildIo
f1_keywords:
 - "storport/HwStorBuildIo"
 - "HwStorBuildIo"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL (See Remarks section.)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Storport.h
api_name:
- HwStorBuildIo
targetos: Windows
req.typenames: 
---

# HW_BUILDIO callback function


## -description


The <b>HwStorBuildIo</b> routine processes the SRB with unsynchronized access to shared system data structures before passing it to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a>.


## -parameters




### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area. 


### -param Srb

A pointer to the SCSI request block (SRB) to be processed.


## -returns



<b>HwStorBuildIo</b> returns <b>TRUE</b> to inform the caller that StorPort should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a> routine if StorPort considers the LUN ready to receive I/O. <b>HwStorBuildIo</b> returns <b>FALSE</b> to inform the caller that the SRB should not be passed to <b>HwStorStartIo</b>. In such cases, the miniport driver must complete the SRB by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportnotification">StorPortNotification</a> with a notification type of <b>RequestComplete</b>. This can be done in <b>HwStorBuildIo</b> or elsewhere in the miniport driver, as long as the SRB is completed before the timeout that is specified in the <b>TimeOutValue</b> field of the SRB structure.




## -remarks



The name <b>HwStorBuildIo</b> is just a placeholder for the miniport function that is pointed to by the <b>HwBuildIo</b> member in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure. The actual prototype of this routine is defined in Storport.h as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
BOOLEAN
HW_BUILDIO (
  _In_ PVOID DeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK  Srb
  );</pre>
</td>
</tr>
</table></span></div>
The port driver calls the <b>HwStorBuildIo</b> routine at DISPATCH IRQL without holding any spin locks. Because of this, memory allocation using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportallocatepool">StorPortAllocatePool</a> and mutual exclusion via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a> are allowed in <b>HwStorBuildIo</b>. In a multiprocessor environment, more than one <b>HwStorBuildIo</b> can be active at a time, so the miniport driver is required to synchronize access to system resources, which may be in contention if more than one instance of  <b>HwStorBuildIo</b> is active at any given time.

By completed time-consuming I/O setup activities in <b>HwStorBuildIo</b> instead of in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a>, the miniport driver enables greater I/O concurrency and therefore improves I/O throughput. For highest performance, miniport drivers are expected to do as much preprocessing as possible in <b>HwStorBuildIo</b> so that it can send requests to the HBA via <b>HwStorStartIo</b> in as short amount of time as possible. Preprocessed data and state can be stored in either the <i>DeviceExtension</i> or <i>SrbExtension</i> structures. Only modifications to unique portions of the <i>DeviceExtension</i> must occur since no locks are held. <b>HwStorBuildIo</b> and <b>HwStorStartIo</b> receive the following Srb function types:

<table>
<tr>
<th>Srb function</th>
<th>Expected action</th>
<th>Remarks</th>
</tr>
<tr>
<td>
SRB_FUNCTION_EXECUTE_SCSI 

</td>
<td>
Sends a CDB to the specified bus/target/lun.

</td>
<td>
Srb->DataTransferLength is valid for all Cdbs. 

Srb->DataBuffer is <b>NULL</b> for read and write requests . To access the associated data, either use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetscattergatherlist">StorPortGetScatterGatherList</a> (for Dma transfers) or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetsystemaddress">StorPortGetSystemAddress</a> (for program controlled I/O ) to get the Scatter Gather list or the virtual address of the buffer.

For other requests, Srb->Databuffer points to the data that is associated with the Srb.

Srb->PathId is valid and represents the pathid given to Storport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportnotification">StorPortNotification</a> (BusChange). Writers of miniport drivers need to use pathid as an index into a table of busses within the miniport. 

 Srb->TargetId and Srb->Lun are valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_IO_CONTROL 

</td>
<td>
Miniport defined.

</td>
<td>
Srb->DataTransferLength and Srb->DataBuffer are valid if set by the requester.

Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_RESET_LOGICAL_UNIT

</td>
<td>
Reset the specified logical unit (if the device is capable).

</td>
<td>
Srb->DataTransferLength and Srb->DataBuffer are invalid.

Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_RESET_DEVICE 

</td>
<td>
Reset the specified Scsi Target.

</td>
<td>
Srb->DataTransferLength and Srb->DataBuffer, Srb->Lun are invalid.

Srb->PathId and Srb->TargetId are valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_RESET_BUS 

</td>
<td>
Reset all of the targets on the specified SCSI bus.

</td>
<td>
Only Srb->PathId is valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_FLUSH 

</td>
<td>
Only performed by the miniport driver if it sets <b>CachesData</b> == <b>TRUE</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a>. Instructs the miniport driver to flush all cached data.

</td>
<td>
Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_SHUTDOWN

</td>
<td>
Only performed by the miniport driver if it sets <b>CachesData</b> == <b>TRUE</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a>. Instructs the miniport driver to flush all cached data preparatory to shut down.

</td>
<td>
Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_DUMP_POINTERS

</td>
<td>
This request is sent to a Storport virtual miniport driver that is used to control the disk that holds the crash dump data. The request supplies information needed for the miniport driver to support crash dump and hibernation.

Starting with Windows 8, non-virtual miniport drivers can optionally receive this request

</td>
<td>
Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_FREE_DUMP_POINTERS

</td>
<td>
Starting with Windows 8, this request is sent to the miniport to free and resources allocated during the SRB_FUNCTION_DUMP_POINTERS request.

</td>
<td>
Srb->PathId, Srb->TargetId, and Srb->Lun are all valid.

</td>
</tr>
</table>
 

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.

For more information about what you can and cannot do safely in this miniport driver routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/unsynchronized-hwstorbuildio-routine">Unsynchronized HwStorBuildIo Routine</a>. 


#### Examples

To define an <b>HwStorBuildIo</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorBuildIo</b> callback routine that is named <i>MyHwBuildIo</i>, use the <b>HW_BUILDIO</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_BUILDIO MyHwBuildIo;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
MyHwBuildIo (
  _In_ PVOID  DeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK  Srb
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_BUILDIO</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_BUILDIO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportallocatepool">StorPortAllocatePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportnotification">StorPortNotification</a>
 

 

