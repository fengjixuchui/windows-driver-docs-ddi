---
UID: NC:sercx.EVT_SERCX2_SELECT_NEXT_RECEIVE_TRANSACTION_TYPE
title: EVT_SERCX2_SELECT_NEXT_RECEIVE_TRANSACTION_TYPE (sercx.h)
description: The EvtSerCx2SelectNextReceiveTransactionType event callback function is called by version 2 of the serial framework extension (SerCx2) to determine which data-transfer mechanism to use for the next read operation.
old-location: serports\evtsercx2selectnextreceivetransactiontype.htm
tech.root: serports
ms.assetid: CB4551F4-8B22-4595-8091-CB84671DC60C
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2SelectNextReceiveTransactionType, EVT_SERCX2_SELECT_NEXT_RECEIVE_TRANSACTION_TYPE, EVT_SERCX2_SELECT_NEXT_RECEIVE_TRANSACTION_TYPE callback, EvtSerCx2SelectNextReceiveTransactionType, EvtSerCx2SelectNextReceiveTransactionType callback function [Serial Ports], serports.evtsercx2selectnextreceivetransactiontype
ms.topic: callback
f1_keywords:
 - "sercx/EvtSerCx2SelectNextReceiveTransactionType"
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
- EvtSerCx2SelectNextReceiveTransactionType
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_SELECT_NEXT_RECEIVE_TRANSACTION_TYPE callback function


## -description


The <i>EvtSerCx2SelectNextReceiveTransactionType</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to determine which data-transfer mechanism to use for the next read operation.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>.


### -param Mdl [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> that describes the memory pages that are spanned by the read buffer for the next receive transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.


### -param Offset [in]

The starting offset for the next data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.


### -param RemainingLength [in]

The total number of bytes of data that remain to be transferred in the current read (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>) request. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


### -param CustomReceive [out]

A pointer to a location to which the function writes the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVE</a> handle to the custom-receive object. If the function returns <b>SerCx2TransactionTypeCustom</b>, the function must supply the object handle that the serial controller driver created in a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivecreate">SerCx2CustomReceiveCreate</a> method. If the return value is not <b>SerCx2TransactionTypeCustom</b>, this output value is ignored by SerCx2.


### -param NextTransactionLength [out]

A pointer to a location to which the function writes the number of bytes to transfer in the next receive transaction. If the return value is <b>SerCx2TransactionTypeDefault</b>, this output value is ignored by SerCx2.


## -returns



The <i>EvtSerCx2SelectNextReceiveTransactionType</i> function returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ne-sercx-_sercx2_transaction_type">SERCX2_TRANSACTION_TYPE</a> enumeration constant to indicate whether to use a driver-selected transaction type (programmed I/O (PIO), system DMA, or custom data transfer), or to let SerCx2 choose which transaction type to use for the next receive transaction.




## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers this function in the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

If your serial controller driver does not implement an <i>EvtSerCx2SelectNextReceiveTransactionType</i> function, then SerCx2 always decides what type of data-transfer mechanism (PIO, system DMA, or custom) to use for the next receive transaction. SerCx2 bases its decisions on the I/O configuration information supplied by the serial controller driver. A driver that supports system-DMA-receive transactions supplies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure that contains this information. A driver that supports custom-receive transactions supplies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_custom_receive_config">SERCX2_CUSTOM_RECEIVE_CONFIG</a> structure that contains this information.

If your serial controller driver implements an <i>EvtSerCx2SelectNextReceiveTransactionType</i> function, SerCx2 calls this function to determine what type of data-transfer mechanism (PIO, system DMA, or custom) to use for the next receive transaction. You might want to implement this function if the serial controller has special hardware capabilities that cannot adequately be described by the I/O configuration information in the <b>SERCX2_<i>XXX</i>_RECEIVE_CONFIG</b> structures.

<div class="alert"><b>Note</b>  Even if a serial controller driver implements an <i>EvtSerCx2SelectNextReceiveTransactionType</i> function, SerCx2 uses PIO-receive transactions to perform certain types of data transfers without first calling this function.</div>
<div> </div>
For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265243(v=vs.85)">Overview of SerCx2 I/O Transactions</a>.


#### Examples

To define an <i>EvtSerCx2CustomReceiveSelectNextTransactionType</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2CustomReceiveSelectNextTransactionType</i> callback function that is named <code>MyCustomReceiveSelectNextTransactionType</code>, use the <b>EVT_SERCX2_CUSTOM_RECEIVE_SELECT_NEXT_TRANSACTION_TYPE</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_CUSTOM_RECEIVE_SELECT_NEXT_TRANSACTION_TYPE  MyCustomReceiveTransactionStart;</pre>
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
SERCX2_TRANSACTION_TYPE
  EvtSerCx2SelectNextReceiveTransactionType(
    WDFDEVICE  Device,
    PMDL  Mdl,
    ULONG  Offset,
    ULONG  RemainingLength,
    SERCX2CUSTOMRECEIVE  *CustomReceive,
    PULONG  NextTransactionLength
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_CUSTOM_RECEIVE_SELECT_NEXT_TRANSACTION_TYPE</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_CUSTOM_RECEIVE_SELECT_NEXT_TRANSACTION_TYPE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_custom_receive_config">SERCX2_CUSTOM_RECEIVE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ne-sercx-_sercx2_transaction_type">SERCX2_TRANSACTION_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivecreate">SerCx2CustomReceiveCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>
 

 

