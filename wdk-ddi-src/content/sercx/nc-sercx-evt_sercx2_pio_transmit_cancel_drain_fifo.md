---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO
title: EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO (sercx.h)
description: The EvtSerCx2PioTransmitCancelDrainFifo event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a previous request to drain the transmit FIFO in the serial controller hardware.
old-location: serports\evtsercx2piotransmitcanceldrainfifo.htm
tech.root: serports
ms.assetid: DAAE9C91-F83F-4D14-8851-7B5DEEA340B3
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2PioTransmitCancelDrainFifo, EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO, EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO callback, EvtSerCx2PioTransmitCancelDrainFifo, EvtSerCx2PioTransmitCancelDrainFifo callback function [Serial Ports], serports.evtsercx2piotransmitcanceldrainfifo
ms.topic: callback
f1_keywords:
 - "sercx/EvtSerCx2PioTransmitCancelDrainFifo"
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
- EvtSerCx2PioTransmitCancelDrainFifo
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO callback function


## -description


The <i>EvtSerCx2PioTransmitCancelDrainFifo</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a previous request to drain the transmit FIFO in the serial controller hardware.


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method to create this object.


## -returns



The <i>EvtSerCx2PioTransmitCancelDrainFifo</i> function returns <b>TRUE</b> if it successfully cancels the pending drain request, and the serial controller driver can guarantee that it will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitdrainfifocomplete">SerCx2PioTransmitDrainFifoComplete</a> method to notify SerCx2 that the FIFO is drained. Otherwise, this function returns <b>FALSE</b> to indicate that the driver has already called or is about to call <b>SerCx2PioTransmitDrainFifoComplete</b>.




## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

Your driver should implement an <i>EvtSerCx2PioTransmitCancelDrainFifo</i> function if the serial controller has a hardware FIFO (or similar buffering mechanism) to hold transmit data. If your driver implements this function, it must also implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_drain_fifo">EvtSerCx2PioTransmitDrainFifo</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_purge_fifo">EvtSerCx2PioTransmitPurgeFifo</a> event callback functions.

SerCx2 calls the <i>EvtSerCx2PioTransmitDrainFifo</i> event callback function to ask the serial controller driver to drain the transmit FIFO, and then waits for the serial controller driver to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitdrainfifocomplete">SerCx2PioTransmitDrainFifoComplete</a>. A drain operation can take an indefinite amount of time to finish. Thus, if the write request times out or is canceled while the drain operation is in progress, SerCx2 calls the <i>EvtSerCx2PioTransmitCancelDrainFifo</i> function to cancel the pending drain operation before it finishes.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265336(v=vs.85)">SerCx2 PIO-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioTransmitCancelDrainFifo</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioTransmitCancelDrainFifo</i> callback function that is named <code>MyPioTransmitCancelDrainFifo</code>, use the <b>EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO  MyPioTransmitCancelDrainFifo;</pre>
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
  MyPioTransmitCancelDrainFifo(
    SERCX2PIOTRANSMIT  PioTransmit
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_drain_fifo">EvtSerCx2PioTransmitDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_purge_fifo">EvtSerCx2PioTransmitPurgeFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_purge">IOCTL_SERIAL_PURGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitdrainfifocomplete">SerCx2PioTransmitDrainFifoComplete</a>
 

 

