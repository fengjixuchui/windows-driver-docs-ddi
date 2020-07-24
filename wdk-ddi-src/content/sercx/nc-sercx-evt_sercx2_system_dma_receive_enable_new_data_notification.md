---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION
title: EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION (sercx.h)
description: The EvtSerCx2SystemDmaReceiveEnableNewDataNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.
old-location: serports\evtsercx2systemdmareceiveenablenewdatanotification.htm
tech.root: serports
ms.assetid: E2B7FE14-1D06-48E7-95FB-C103358340EA
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION callback function"]
ms.keywords: 2/EvtSerCx2SystemDmaReceiveEnableNewDataNotification, EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION, EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION callback, EvtSerCx2SystemDmaReceiveEnableNewDataNotification, EvtSerCx2SystemDmaReceiveEnableNewDataNotification callback function [Serial Ports], serports.evtsercx2systemdmareceiveenablenewdatanotification
f1_keywords:
 - "sercx/EvtSerCx2SystemDmaReceiveEnableNewDataNotification"
 - "EvtSerCx2SystemDmaReceiveEnableNewDataNotification"
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
- EvtSerCx2SystemDmaReceiveEnableNewDataNotification
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION callback function


## -description


The <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.


## -parameters




### -param SystemDmaReceive [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method to create this object.


## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> call that creates the system-DMA-receive object.

After the <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function is called to enable a new-data notification for a system-DMA-receive transaction, the serial controller driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivenewdatanotification">SerCx2SystemDmaReceiveNewDataNotification</a> method to notify SerCx2 when the driver detects that one or more bytes of received data either are ready to be transferred or have already been transferred by the system DMA controller.

The new-data notification enabled by the <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function is a one-shot notification. After this function is called and the serial controller driver sends a new-data notification to SerCx2, no further notification is sent until SerCx2 calls the function again to enable another notification.

The <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function typically enables an interrupt to be triggered when the serial controller receives data from the peripheral device.

No more than one new-data notification can be pending at a time. After SerCx2 calls the <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function to enable a new-data notification, SerCx2 does not call this function again until the controller driver calls <b>SerCx2SystemDmaReceiveNewDataNotification</b>.

A pending new-data notification can be canceled if the associated read request times out or is canceled. To cancel a new-data notification for a system-DMA-receive transaction, SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_cancel_new_data_notification">EvtSerCx2SystemDmaReceiveCancelNewDataNotification</a> event callback function. A driver that implements an <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function must also implement an <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> function.

SerCx2 uses new-data notifications to efficiently manage interval time-outs that occur during the handling of read requests that are processed as system-DMA-receive transactions.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265343(v=vs.85)">SerCx2 System-DMA-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> callback function that is named <code>MySystemDmaReceiveEnableNewDataNotification</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION  MySystemDmaReceiveEnableNewDataNotification;</pre>
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
VOID
  MySystemDmaReceiveEnableNewDataNotification(
    SERCX2SYSTEMDMARECEIVE  SystemDmaReceive
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_cancel_new_data_notification">EvtSerCx2SystemDmaReceiveCancelNewDataNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_cleanup_transaction">EvtSerCx2SystemDmaReceiveCleanupTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pread_dma_counter">ReadDmaCounter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivenewdatanotification">SerCx2SystemDmaReceiveNewDataNotification</a>
 

 

