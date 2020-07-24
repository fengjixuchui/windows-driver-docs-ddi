---
UID: NC:wdfdmatransaction.EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE
title: EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE (wdfdmatransaction.h)
description: A driver's EvtDmaTransactionDmaTransferComplete event callback function is called when the system-mode controller has completed the current DMA transfer.
old-location: wdf\evtdmatransactiondmatransfercomplete.htm
tech.root: wdf
ms.assetid: C638A505-AAE1-48FC-B06B-F2F161ADC948
ms.date: 02/26/2018
keywords: ["EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE callback function"]
ms.keywords: EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE, EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE callback, EvtDmaTransactionDmaTransferComplete, EvtDmaTransactionDmaTransferComplete callback function, kmdf.evtdmatransactiondmatransfercomplete, wdf.evtdmatransactiondmatransfercomplete, wdfdmatransaction/EvtDmaTransactionDmaTransferComplete
f1_keywords:
 - "wdfdmatransaction/EvtDmaTransactionDmaTransferComplete"
 - "EvtDmaTransactionDmaTransferComplete"
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfDmaTransaction.h
api_name:
- EvtDmaTransactionDmaTransferComplete
targetos: Windows
req.typenames: 
---

# EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   A driver's <i>EvtDmaTransactionDmaTransferComplete</i> event callback function is called when  the system-mode controller has completed the current DMA transfer.


## -parameters




### -param Transaction [in]

A handle to a DMA transaction object representing the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a> that has just completed.


### -param Device [in]

A handle to the framework device object that the driver specified when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param Context [in]

The context pointer that the driver specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback">WdfDmaTransactionSetTransferCompleteCallback</a>.


### -param Direction [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_direction">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the completing DMA transfer operation.


### -param Status [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-dma_completion_status">DMA_COMPLETION_STATUS</a>-typed value that specifies the status of the transfer.


## -remarks



The hardware for a bus-master DMA device typically issues an interrupt when a DMA transfer is complete. The driver then completes the DMA transfer in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>  callback function.

However, the hardware for a system-mode DMA device does not always signal DMA transfer completion by issuing an interrupt. To receive notification of DMA transfer completion, a driver for a system-mode DMA device can instead register an <i>EvtDmaTransactionDmaTransferComplete</i> event callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback">WdfDmaTransactionSetTransferCompleteCallback</a>.

The framework calls <i>EvtDmaTransactionDmaTransferComplete</i> after the system DMA controller has completed the transfer, once for each transfer in a transaction.

From within its <i>EvtDmaTransactionDmaTransferComplete</i> callback, the driver can call the following methods to notify the framework that the transfer has completed:

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>
The driver might not call one of the previous methods from <i>EvtDmaTransactionDmaTransferComplete</i>, opting instead to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-timers">create a timer object</a> or schedule a DPC to complete the transfer later, as needed. After <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> returns TRUE, indicating that no more transfers are needed to complete the DMA transaction, the driver can optionally call  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionexecute">WdfDmaTransactionExecute</a> to initiate a subsequent transaction.

If the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer">WdfDmaTransactionStopSystemTransfer</a>, the framework calls <i>EvtDmaTransactionDmaTransferComplete</i> with a <i>Status</i> value of <b>DmaCancelled</b>.  In this case, the driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a> from within <i>EvtDmaTransactionDmaTransferComplete</i>, and then can continue with request processing.

The driver must not manipulate the data buffers associated with the transaction until after <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> has returned TRUE.

The driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionrelease">WdfDmaTransactionRelease</a> from within <i>EvtDmaTransactionDmaTransferComplete</i> if it needs to terminate the DMA transaction.

For more information about system-mode DMA, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-mode-dma">Supporting System-Mode DMA</a>.


#### Examples

To define an <i>EvtDmaTransactionDmaTransferComplete</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDmaTransactionDmaTransferComplete</i> callback function that is named <i>MyDmaTransactionDmaTransferComplete</i>, use the <b>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE  MyDmaTransactionDmaTransferComplete;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
_Use_decl_annotations_
VOID
MyDmaTransactionDmaTransferComplete(
    WDFDMATRANSACTION Transaction,
    WDFDEVICE /* Device */,
    WDFCONTEXT Context,
    WDF_DMA_DIRECTION /* Direction */,
    DMA_COMPLETION_STATUS DmaStatus
    )
{
    PREQUEST_CONTEXT requestContext = (PREQUEST_CONTEXT) Context;
    NTSTATUS requestStatus;
    bool overrideStatus = true;
    size_t bytesTransferred;

    if (DmaStatus == DmaComplete) {
        //
        // Normal transfer completion.  Indicate this to the framework and see 
        // if there's more work to do.
        //
        if (WdfDmaTransactionDmaCompleted(Transaction, &requestStatus) == FALSE) {
            //
            // There are more DMA transfers to come.  The transaction 
            // may already have been completed on another processor.  
            // Return without touching it again.
            //
            goto exit;
        }

        requestStatus = STATUS_SUCCESS;
    }
    else {

        //
        // Complete the entire transaction.  But throw out the status and 
        // use one derived from the DmaStatus.
        //
        WdfDmaTransactionDmaCompletedFinal(Transaction, 0, &requestStatus);        
        
        //
        // Error or cancellation.  Indicate that this was the final transfer to 
        // the framework.
        //
        if (DmaStatus == DmaError) {
            requestStatus = STATUS_DEVICE_DATA_ERROR;
        }
        else {

            //
            // Cancel status should only be triggered by timeout or cancel.  Rely on 
            // someone having already set the status, which means we should lose
            // the race for BeginCompletion below.
            //
            requestStatus = STATUS_PENDING;
            overrideStatus = false;
        }
    }

    //
    // Begin completion.  There's nothing special to do here if cancel or
    // timeout got there first.
    //
    BeginCompletion(requestContext, requestStatus, overrideStatus);

    //
    // Record the number of bytes we transferred.
    //
    bytesTransferred = WdfDmaTransactionGetBytesTransferred(
                        requestContext->DmaTransaction
                        );

    WdfRequestSetInformation(requestContext->Request, bytesTransferred);

    //
    // Success, error or cancel, this was the last transfer in the 
    // transaction.  Attempt to complete the request.
    //
    AttemptRequestCompletion(requestContext, true);

exit: 
    return;
}

bool
BeginCompletion(
    __in PREQUEST_CONTEXT  RequestContext,
    __in NTSTATUS          CompletionStatus,
    __in bool              ForceStatusUpdate
    )
{
    bool completionStarted;

    //
    // Grab the object lock and mark the beginning of 
    // completion.
    //
    WdfSpinLockAcquire(RequestContext->Lock);

    completionStarted = RequestContext->CompletionStarted;
    RequestContext->CompletionStarted = true;

    if ((completionStarted == false) || 
        (ForceStatusUpdate == true)) {
        RequestContext->CompletionStatus = CompletionStatus;
    }

    WdfSpinLockRelease(RequestContext->Lock);

    return !completionStarted;
}

VOID
AttemptRequestCompletion(
    __in PREQUEST_CONTEXT RequestContext,
    __in bool TransferComplete
    )
{
    LONG refCount;

    NT_ASSERTMSG("No thread has begun completion", 
                 RequestContext->CompletionStarted == true);

    if (TransferComplete) {
        //
        // Unmark the request cancelable.  If that succeeds then drop the cancel reference
        //
        if (WdfRequestUnmarkCancelable(RequestContext->Request) == STATUS_SUCCESS) {
            refCount = InterlockedDecrement(&(RequestContext->CompletionRefCount));
            NT_ASSERTMSGW(L"Reference count should not have gone to zero yet",
                          refCount != 0);
        }
                
        //
        // Stop the timer if it's been started.
        //
        if (RequestContext->TimerStarted == true) {
            if (WdfTimerStop(RequestContext->Timer, FALSE) == TRUE) {
                //
                // The timer was queued but will never run.  Drop its 
                // reference count.
                //
                refCount = InterlockedDecrement(&RequestContext->CompletionRefCount);
                NT_ASSERTMSG("Completion reference count should not reach zero until "
                             L"this routine calls AttemptRequestCompletion",
                             refCount > 0);
            }
        }
    }

    //
    // Drop this caller's reference.  If that was the last one then 
    // complete the request.
    //
    refCount = InterlockedDecrement(&(RequestContext->CompletionRefCount));

    if (refCount == 0) {
        NT_ASSERTMSGW(L"Execution reference was released, but execution "
                      L"path did not set a completion status for the "
                      L"request",
                      RequestContext->CompletionStatus != STATUS_PENDING);
        
        
        //
        // Timers are disposed of at passive level.  If we leave it attached to 
        // the request then we can hit a verifier issue, since the request 
        // needs to be immediately disposable at dispatch-level.
        //
        // Delete the timer now so that we can complete the request safely.
        // At this point the timer has either expired or been succesfully 
        // cancelled so there's no race with the timer routine.
        //
        if (RequestContext->Timer != NULL) {
            WdfObjectDelete(RequestContext->Timer);
            RequestContext->Timer = NULL;
        }

        WdfRequestComplete(RequestContext->Request, 
                           RequestContext->CompletionStatus);
    }
}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE</b> function type is defined in the WdfDmaTransaction.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback">WdfDmaTransactionSetTransferCompleteCallback</a>
 

 

