---
UID: NC:mrx.PMRX_SRVCALL_WINNER_NOTIFY
title: PMRX_SRVCALL_WINNER_NOTIFY (mrx.h)
description: The MRxSrvCallWinnerNotify routine is called by RDBSS to notify a network mini-redirector that it was chosen when multiple redirectors could fulfill the request.
old-location: ifsk\mrxsrvcallwinnernotify.htm
tech.root: ifsk
ms.assetid: 6853b73e-5516-485e-ade4-54b7faf6bb1d
ms.date: 04/16/2018
ms.keywords: MRxSrvCallWinnerNotify, MRxSrvCallWinnerNotify routine [Installable File System Drivers], PMRX_SRVCALL_WINNER_NOTIFY, ifsk.mrxsrvcallwinnernotify, mrx/MRxSrvCallWinnerNotify, mrxref_32054fb8-84ca-407a-ab65-90feee16041d.xml
ms.topic: callback
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- mrx.h
api_name:
- MRxSrvCallWinnerNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_SRVCALL_WINNER_NOTIFY callback function


## -description


The<i> MRxSrvCallWinnerNotify</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to notify a network mini-redirector that it was chosen when multiple redirectors could fulfill the request. 


## -parameters




### -param SrvCall


### -param ThisMinirdrIsTheWinner [in]

A Boolean value that indicates that this network mini-redirector was chosen.


### -param RecommunicateContext








#### - pSrvCall [in, out]

A pointer to the SRV_CALL structure. 


#### - pSrvCallContext [in, out]

A pointer to an SRV_CALL structure that is created by the network mini-redirector.


## -returns



<i>MRxSmbSrvCallWinnerNotify</i> returns STATUS_SUCCESS on success. 




## -remarks



<i>MRxSrvCallWinnerNotify</i> was originally designed to be called by RDBSS to notify a network mini-redirector that it was chosen when multiple redirectors could fulfill the request. The chosen network mini-redirector is expected to create the SRV_CALL structure and establish a connection with the server.

The network mini-redirector should complete the context for the SRV_CALL structure. If the network mini-redirector supports case-insensitive names for NET_ROOT structures and for filenames, then the SRV_CALL <b>Flags</b> member should set the bits for SRVCALL_FLAG_CASE_INSENSITIVE_NETROOTS and SRVCALL_FLAG_CASE_INSENSITIVE_FILENAMES.

Under the current implementation of RDBSS, each network mini-redirector has its own copy of RDBSS, so there are no competing network redirectors at the RDBSS layer. All network mini-redirectors will receive a call to <i>MRxSrvCallWinnerNotify</i> with the <i>ThisMinirdrIsTheWinner</i> parameter set to <b>TRUE</b> after receiving a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_create_srvcall">MRxCreateSrvCall</a> to create the SRV_CALL structure. 

When multiple redirectors are installed for handling the same UNC namespace, the redirector to service a request is chosen by multiple UNC provider (MUP) based on the order of redirectors specified in the registry. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_create_srvcall">MRxCreateSrvCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_create_v_net_root">MRxCreateVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_extract_netroot_name">MRxExtractNetRootName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_finalize_net_root_calldown">MRxFinalizeNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_finalize_v_net_root_calldown">MRxFinalizeVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nc-mrx-pmrx_preparse_name">MRxPreparseName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a>
 

 

