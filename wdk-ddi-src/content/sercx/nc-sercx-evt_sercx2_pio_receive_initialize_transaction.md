---
UID: NC:sercx.EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION
title: EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION (sercx.h)
description: The EvtSerCx2PioReceiveInitializeTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller to perform a PIO-receive transaction.
old-location: serports\evtsercx2pioreceiveinitializetransaction.htm
tech.root: serports
ms.assetid: E03B5319-BBBE-4396-8D03-8BC82FB97D15
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION callback function"]
ms.keywords: 2/EvtSerCx2PioReceiveInitializeTransaction, EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION, EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION callback, EvtSerCx2PioReceiveInitializeTransaction, EvtSerCx2PioReceiveInitializeTransaction callback function [Serial Ports], serports.evtsercx2pioreceiveinitializetransaction
f1_keywords:
 - "sercx/EvtSerCx2PioReceiveInitializeTransaction"
 - "EvtSerCx2PioReceiveInitializeTransaction"
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
- EvtSerCx2PioReceiveInitializeTransaction
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION callback function


## -description


The <i>EvtSerCx2PioReceiveInitializeTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller to perform a PIO-receive transaction.


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.


### -param Length [in]

The number of bytes to be transferred in the PIO-receive transaction.


## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method that creates the PIO-receive object.

Your driver should implement an <i>EvtSerCx2PioReceiveInitializeTransaction</i> function if it needs to initialize the serial controller and associated hardware in preparation for a new PIO-receive transaction. SerCx2 calls this function, if it is implemented, before a PIO-receive transaction starts. In response to this call, the serial controller driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceiveinitializetransactioncomplete">SerCx2PioReceiveInitializeTransactionComplete</a> method to notify SerCx2 after the initialization is finished.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265332(v=vs.85)">SerCx2 PIO-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioReceiveInitializeTransaction</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioReceiveInitializeTransaction</i> callback function that is named <code>MyPioReceiveInitializeTransaction</code>, use the <b>EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION  MyPioReceiveInitializeTransaction;</pre>
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
  MyPioReceiveInitializeTransaction(
    SERCX2PIORECEIVE  PioReceive,
    ULONG  Length
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceiveinitializetransactioncomplete">SerCx2PioReceiveInitializeTransactionComplete</a>
 

 

