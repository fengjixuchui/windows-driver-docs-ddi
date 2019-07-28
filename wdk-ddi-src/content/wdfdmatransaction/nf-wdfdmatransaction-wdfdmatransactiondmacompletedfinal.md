---
UID: NF:wdfdmatransaction.WdfDmaTransactionDmaCompletedFinal
title: WdfDmaTransactionDmaCompletedFinal function (wdfdmatransaction.h)
description: The WdfDmaTransactionDmaCompletedFinal method notifies the framework that a device's DMA transfer operation has completed with an underrun condition and supplies the length of the completed transfer.
old-location: wdf\wdfdmatransactiondmacompletedfinal.htm
tech.root: wdf
ms.assetid: de16eaf4-11f0-428b-8833-1d1e6ef78853
ms.date: 02/26/2018
ms.keywords: DFDmaObjectRef_ceac647e-264e-416b-947f-61cc95e6d4ab.xml, WdfDmaTransactionDmaCompletedFinal, WdfDmaTransactionDmaCompletedFinal method, kmdf.wdfdmatransactiondmacompletedfinal, wdf.wdfdmatransactiondmacompletedfinal, wdfdmatransaction/WdfDmaTransactionDmaCompletedFinal
ms.topic: function
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionDmaCompletedFinal"
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDmaTransactionDmaCompletedFinal
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionDmaCompletedFinal function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionDmaCompletedFinal</b> method notifies the framework that a device's DMA transfer operation has completed with an underrun condition and supplies the length of the completed transfer. 


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param FinalTransferredLength [in]

The number of bytes that the device transferred.


### -param Status [out]

A pointer to a location that receives the status of the DMA transfer. For more information, see the Remarks section for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>.


## -returns



<b>WdfDmaTransactionDmaCompletedFinal</b> returns <b>FALSE</b> if the driver supplies an invalid input parameter. Otherwise, <b>WdfDmaTransactionDmaCompletedFinal</b> always returns <b>TRUE</b>, which indicates that the framework will not attempt to transfer any more bytes for the DMA transaction that the <i>DmaTransaction</i> parameter specified. 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver typically calls <b>WdfDmaTransactionDmaCompletedFinal</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback. A driver for a system-mode DMA device might call <b>WdfDmaTransactionDmaCompletedFinal</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete">EvtDmaTransactionDmaTransferComplete</a> event callback function.

In the  <a href="https://go.microsoft.com/fwlink/p/?linkid=256157">PLX9x5x</a> sample, the driver calls  <b>WdfDmaTransactionDmaCompletedFinal</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> callback function.

The <b>WdfDmaTransactionDmaCompletedFinal</b> method behaves the same as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>, except that drivers typically call <b>WdfDmaTransactionDmaCompletedFinal</b> if the hardware reports an underrun condition. An underrun condition means that the hardware could not transfer all of the bytes that were specified for the last DMA transfer. A call to <b>WdfDmaTransactionDmaCompletedFinal</b> stops the framework from starting any more DMA transfers for the specified DMA transaction.

When your driver calls <b>WdfDmaTransactionDmaCompletedFinal</b>, the driver supplies the number of bytes that were transferred. The return value is always <b>TRUE</b>, because the framework will not attempt to transfer any more bytes for the specified transaction. 

For more information about completing DMA transfers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-a-dma-transfer">Completing a DMA Transfer</a>. 


#### Examples

The following code example notifies the framework that a device's DMA transfer operation has completed with an underrun condition.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN  success;
NTSTATUS  status;

success = WdfDmaTransactionDmaCompletedFinal(
                                             DmaTransaction,
                                             transferLength,
                                             &status
                                             );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>
 

 

