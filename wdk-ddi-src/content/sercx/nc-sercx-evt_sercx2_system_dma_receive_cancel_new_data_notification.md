---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION
title: EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION (sercx.h)
description: The EvtSerCx2SystemDmaReceiveCancelNewDataNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a new-data notification that SerCx2 enabled in a previous call to the EvtSerCx2SystemDmaReceiveEnableNewDataNotification event callback function.
old-location: serports\evtsercx2systemdmareceivecancelnewdatanotification.htm
tech.root: serports
ms.assetid: 7C88F794-0C2B-4715-B09A-2AA49414F18A
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2SystemDmaReceiveCancelNewDataNotification, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION callback, EvtSerCx2SystemDmaReceiveCancelNewDataNotification, EvtSerCx2SystemDmaReceiveCancelNewDataNotification callback function [Serial Ports], serports.evtsercx2systemdmareceivecancelnewdatanotification
ms.topic: callback
f1_keywords:
 - "sercx/EvtSerCx2SystemDmaReceiveCancelNewDataNotification"
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 2.0\Sercx.h
api_name:
- EvtSerCx2SystemDmaReceiveCancelNewDataNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION callback function


## -description


The <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a new-data notification that SerCx2 enabled in a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a> event callback function.


## -parameters




### -param SystemDmaReceive [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method to create this object.


## -returns



The <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> function returns <b>TRUE</b> if the new-data notification was successfully canceled  and the serial controller driver can guarantee that this notification will not cause the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmareceivenewdatanotification">SerCx2SystemDmaReceiveNewDataNotification</a> method to be called. The function returns <b>FALSE</b> if the driver has already called the <b>SerCx2SystemDmaReceiveNewDataNotification</b> method, or is about to call this method.




## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> call that creates the system-DMA-receive object. A driver that implements this function must also implement an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a> event callback function.

If the associated read request times out or is canceled while a new-data notification request is pending, SerCx2 calls the <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> function to cancel the pending notification. If this call returns <b>FALSE</b>, SerCx2 expects the serial controller driver to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmareceivenewdatanotification">SerCx2SystemDmaReceiveNewDataNotification</a>; only after this call does SerCx2 call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_receive_cleanup_transaction">EvtSerCx2SystemDmaReceiveCleanupTransaction</a> function, if it is implemented, and complete the request.

To cancel the new-data notification, the <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> function typically disables the interrupt in the serial controller that indicates that more data is available to be read from the receive FIFO. This interrupt was enabled by a previous call to the <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265343(v=vs.85)">SerCx2 System-DMA-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> callback function that is named <code>MySystemDmaReceiveCancelNewDataNotification</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION  MySystemDmaReceiveCancelNewDataNotification;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
  MySystemDmaReceiveCancelNewDataNotification(
    SERCX2SYSTEMDMARECEIVE  SystemDmaReceive
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmareceivenewdatanotification">SerCx2SystemDmaReceiveNewDataNotification</a>
 

 

