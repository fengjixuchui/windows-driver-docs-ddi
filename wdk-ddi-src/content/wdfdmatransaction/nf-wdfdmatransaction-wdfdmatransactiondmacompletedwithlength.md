---
UID: NF:wdfdmatransaction.WdfDmaTransactionDmaCompletedWithLength
title: WdfDmaTransactionDmaCompletedWithLength function (wdfdmatransaction.h)
description: The WdfDmaTransactionDmaCompletedWithLength method notifies the framework that a device's DMA transfer operation is complete and supplies the length of the completed transfer.
old-location: wdf\wdfdmatransactiondmacompletedwithlength.htm
tech.root: wdf
ms.assetid: 7f436ac1-1e36-449c-a23f-b5729e5a20c2
ms.date: 02/26/2018
keywords: ["WdfDmaTransactionDmaCompletedWithLength function"]
ms.keywords: DFDmaObjectRef_b04fb6c6-98ce-4d3b-8bc9-10a29f6bde46.xml, WdfDmaTransactionDmaCompletedWithLength, WdfDmaTransactionDmaCompletedWithLength method, kmdf.wdfdmatransactiondmacompletedwithlength, wdf.wdfdmatransactiondmacompletedwithlength, wdfdmatransaction/WdfDmaTransactionDmaCompletedWithLength
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionDmaCompletedWithLength"
 - "WdfDmaTransactionDmaCompletedWithLength"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDmaTransactionDmaCompletedWithLength
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionDmaCompletedWithLength function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionDmaCompletedWithLength</b> method notifies the framework that a device's DMA transfer operation is complete and supplies the length of the completed transfer. 


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param TransferredLength [in]

The number of bytes that the device transferred in the current DMA transfer.


### -param Status [out]

A pointer to a location that receives the status of the DMA transfer. For more information, see the Remarks section for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>.


## -returns



<b>WdfDmaTransactionDmaCompletedWithLength</b> returns <b>FALSE</b> and <i>Status</i> receives STATUS_MORE_PROCESSING_REQUIRED if additional transfers are needed to complete the DMA transaction. The method returns <b>TRUE</b> if no additional transfers are required. 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



When your driver calls the <b>WdfDmaTransactionDmaCompletedWithLength</b> method, the framework ends the current transfer and, if necessary, starts a new one.

The <b>WdfDmaTransactionDmaCompletedWithLength</b> method behaves the same as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>, except that drivers call <b>WdfDmaTransactionDmaCompletedWithLength</b> for devices that report the number of bytes that were transferred. The framework uses the reported byte count to determine the beginning of the next DMA transfer for the specified DMA transaction, if multiple transfers are needed to complete the transaction.

For more information about completing DMA transfers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-a-dma-transfer">Completing a DMA Transfer</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">PLX9x5x</a> sample driver. This example calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiongetcurrentdmatransferlength">WdfDmaTransactionGetCurrentDmaTransferLength</a> to determine the current transfer's original length, and then it calculates the actual transfer length. Next, the example calls <b>WdfDmaTransactionDmaCompletedWithLength</b> to report the actual transfer length to the framework. If the current transfer is the last one for the transaction, the example calls a private routine that completes the I/O request.

```cpp
BOOLEAN  hasTransitioned;
PDMA_TRANSFER_ELEMENT  dteVA;
ULONG  length;
//
// Use "DMA Clear-Count Mode" to get the complementary 
// transferred byte count.
//
length = WdfDmaTransactionGetCurrentDmaTransferLength(dmaTransaction);
dteVA = (PDMA_TRANSFER_ELEMENT) devExt->ReadCommonBufferBase;
while(dteVA->DescPtr.LastElement == FALSE) {
    length -= dteVA->TransferSize;
    dteVA++;
}
length -= dteVA->TransferSize;
//
// Indicate that this DMA operation has completed.
//
hasTransitioned = 
    WdfDmaTransactionDmaCompletedWithLength(
                                            dmaTransaction,
                                            length,
                                            &status
                                            ); 
if (hasTransitioned) {
    //
    // Complete this DMA transaction.
    //
    devExt->CurrentReadDmaTransaction = NULL;
    PLxReadRequestComplete(
                           dmaTransaction,
                           status
                           );
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiongetcurrentdmatransferlength">WdfDmaTransactionGetCurrentDmaTransferLength</a>
 

 

