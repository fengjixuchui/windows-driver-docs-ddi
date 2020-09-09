---
UID: NC:mrx.PMRX_CREATE_SRVCALL
title: PMRX_CREATE_SRVCALL (mrx.h)
description: The MRxCreateSrvCall routine is called by RDBSS to request that the network mini-redirector create an SRV_CALL structure and establish connection with a server.
old-location: ifsk\mrxcreatesrvcall.htm
tech.root: ifsk
ms.assetid: 2f6325e1-4ede-41e5-87d3-833c6b52157a
ms.date: 04/16/2018
keywords: ["PMRX_CREATE_SRVCALL callback function"]
ms.keywords: MRxCreateSrvCall, MRxCreateSrvCall routine [Installable File System Drivers], PMRX_CREATE_SRVCALL, ifsk.mrxcreatesrvcall, mrx/MRxCreateSrvCall, mrxref_bc85d9c3-6d64-4510-ae94-0ec858c49110.xml
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PMRX_CREATE_SRVCALL
 - mrx/PMRX_CREATE_SRVCALL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - MRxCreateSrvCall
---

# PMRX_CREATE_SRVCALL callback function


## -description

The<i> MRxCreateSrvCall</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector create an SRV_CALL structure and establish connection with a server.

## -parameters

### -param SrvCall

### -param SrvCallCallBackContext

#### - pCallbackContext [in, out]

A pointer to the callback context used by the network mini-redirector to notify RDBSS when the <i>MRxCreateSrvCall</i> request is finally completed. The <i>pCallbackContext</i> parameter points to an MRX_SRVCALLDOWN_STRUCTURE structure that contains the RX_CONTEXT structure for this request, as well as the <b>Callback</b> routine that the mini-redirector calls when the <i>MRxCreateSrvCall</i> request is finally completed. 


#### - pSrvCall [in, out]

A pointer to the SRV_CALL structure to be created.

## -returns

RDBSS expects <i>MRxCreateSrvCall</i> to return STATUS_PENDING on success or failure. This behavior results because RDBSS expects this call to be completed asynchronously. A network mini-redirector should map STATUS_SUCCESS to STATUS_PENDING as a return value for <i>MRxCreateSrvCall</i>.

The final completion status is returned in the <b>pCallbackContext->Status</b> member once the call completes and the routine in the <b>Callback</b> member in the MRX_SRVCALLDOWN_STRUCTURE structure is called by the network mini-redirector. This member initially contains STATUS_BAD_NETWORK_PATH until the network mini-redirector changes this value on completion. 



The <b>pCallbackContext->Status</b> member contains STATUS_SUCCESS on success once the call is completed or one of the following common error codes on failure (although other error codes are possible): 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BAD_NETWORK_PATH</b></dt>
</dl>
</td>
<td width="60%">
The network path that was specified is bad. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NETWORK_UNREACHABLE</b></dt>
</dl>
</td>
<td width="60%">
The network was unreachable.

</td>
</tr>
</table>

## -remarks

The two important abstractions used in the interface between RDBSS and a network mini-redirector are the SRV_CALL structure and the NET_ROOT structure. An SRV_CALL structure corresponds to the context associated with a server once a connection is established. A NET_ROOT structure corresponds to a share on a server (this could also be viewed as a portion of the namespace that has been claimed by a network mini-redirector).

The creation of an SRV_CALL structure typically involves at least one network round trip. This operation can take considerable time to complete because a network connection with a remote resource may need to be established. To ensure that the asynchronous operations continue, the creation of an SRV_CALL structure is modeled as a two-phase activity. Each call down to a network mini-redirector for creating an SRV_CALL structure is accompanied by a call up from the network mini-redirector to RDBSS that specifies the completion status of the request. RDBSS assumes that <i>MRxCreateSrvCall</i> will be completed asynchronously. So RDBSS expects <i>MRxCreateSrvCall</i> to return STATUS_PENDING. RDBSS will be notified using the callback routine when the call finally completes. 

A network mini-redirector implementation of <i>MRxCreateSrvCall</i> is expected to  return STATUS_PENDING to the initial call. When processing is completed, the network mini-redirector calls the callback routine that is passed in as part of the <i>pCallbackContext</i> parameter to notify RDBSS that the call was completed and to return the completion status. The callback routine that the network mini-redirector calls is specified as the <b>Callback</b> member in the MRX_SRVCALLDOWN_STRUCTURE of the <i>pCallbackContext</i> parameter. The final completion status of the call must be stored in the <b>Status</b> member of the <i>pCallbackContext</i> parameter. 

On success, the network mini-redirector must also store some value in the <b>RecommunicateContext</b> member of the <i>pCallbackContext</i>. The value stored in the <b>RecommunicateContext</b> member is the value that RDBSS will pass to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_srvcall_winner_notify">MRxSrvCallWinnerNotify</a> in the <i>RecommunicateContext</i> parameter if <i>MRxCreateSrvCall</i> was successful. The network mini-redirector must also fill the appropriate data in the <i>pSrvCall</i> parameter for the SRV_CALL structure that was created. Note that the p<i>SrvCall</i> parameter passed to <i>MRxCreateSrvCall</i> is the same as the <b>SrvCall</b> member in the MRX_SRVCALLDOWN_STRUCTURE of the <i>pCallbackContext</i> parameter. This same pSrvCall parameter is also passed to <b>MRxSrvCallWinnerNotify</b> in the <i>SrvCall</i> parameter.

The implementation of <i>MRxCreateSrvCall</i> in a network mini-redirector is also complicated by the need for transport handles. Certain transport-related interfaces require a handle to be created and used for all communication. Creating an SRV_CALL structure may require establishing transport-related handles for network communications. Because the process of establishing a network connection can be time consuming, once a connection is established it makes sense to use the connection for communication as long as possible. Once a transport handle to a remote network resource is established, it can be reused by any number of other application requests. When a user application terminates, the handles associated with the process are deleted. For this reason, establishing transport handles in the context of a transient user-mode process that could be short-lived does not make sense. So an SRV_CALL structure normally needs to be initialized in the context of a well known process that will not disappear while these transport handles are being used for communication. 

One method used to work around the potential problems with transport handles is to have the RDBSS system process allocate the transport handles. This affects how the <i>MRxCreateSrvCall</i> routine is executed. If the request to <i>MRxCreateSrvCall</i> was issued in the context of the RDBSS system process, then this call can be executed immediately and does not need to be posted to a work queue. However, in order to avoid problems, if the request to <i>MRxCreateSrvCall</i> is from any other process, the request would be posted to a system work queue using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxworkq/nf-rxworkq-rxdispatchtoworkerthread">RxDispatchToWorkerThread</a> for later execution. RDBSS will later use one of its system threads to process the work queue request and execute <i>MRxCreateSrvCall</i>. This ensures that any transport handles will be owned by a system process. 

A network mini-redirector can determine if a call to <i>MRxCreateSrvCall</i> was received directly from RDBSS by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxstruc/nf-rxstruc-rxgetrdbssprocess">RxGetRDBSSProcess</a>. <b>RxGetRDBSSProcess</b> will return the RDBBS process and this value can be compared with the current process returned using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcurrentprocess">IoGetCurrentProcess</a>. If the call to <i>MRxCreateSrvCall</i> was not initiated in the context of the RDBSS system process, then <i>MRxCreateSrvCall</i> can return STATUS_PENDING and post the call to a work queue using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxworkq/nf-rxworkq-rxdispatchtoworkerthread">RxDispatchToWorkerThread </a>for later execution by RDBSS. Normally, these calls would be posted to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_work_queue_type">DelayedWorkQueue</a>. 

It is up to the developer of the network mini-redirector to decide how <i>MRxCreateSrvCall</i> is implemented. If the process to create a SRV_CALL can take a considerable amount of time, then <i>MRxCreateSrvCall</i> should be completed asynchronously. If transport handles are needed, then the network mini-redirector needs to find a system process that is long-lived to establish these handles. 

When this call completes, the <i>pSrvCall</i> parameter should be modified with the SRV_CALL structure information updated from the network mini-redirector.

A network mini-redirector that indicates support as a UNC provider will receive a prefix claim from the Multiple UNC Provider (MUP) as a call to <i>MRxCreateSrvCall</i>. For more information about UNC Naming and MUP, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/support-for-unc-naming-and-mup">Support for UNC Naming and MUP</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcurrentprocess">IoGetCurrentProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_create_v_net_root">MRxCreateVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_extract_netroot_name">MRxExtractNetRootName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_finalize_net_root_calldown">MRxFinalizeNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_finalize_srvcall_calldown">MRxFinalizeSrvCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_finalize_v_net_root_calldown">MRxFinalizeVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_preparse_name">MRxPreparseName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_srvcall_winner_notify">MRxSrvCallWinnerNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxworkq/nf-rxworkq-rxdispatchtoworkerthread">RxDispatchToWorkerThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxstruc/nf-rxstruc-rxgetrdbssprocess">RxGetRDBSSProcess</a>

