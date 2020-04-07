---
UID: NF:wdm.ClfsMgmtHandleLogFileFull
title: ClfsMgmtHandleLogFileFull function (wdm.h)
description: The ClfsMgmtHandleLogFileFull routine attempts to make more space available in a log. It might make more space available by adding containers to the log, or it might ask clients to move their log tails.
old-location: kernel\clfsmgmthandlelogfilefull.htm
tech.root: kernel
ms.assetid: acfd28c9-c6d5-4768-b095-488f174d78c0
ms.date: 04/30/2018
keywords: ["ClfsMgmtHandleLogFileFull function"]
ms.keywords: ClfsMgmtHandleLogFileFull, ClfsMgmtHandleLogFileFull routine [Kernel-Mode Driver Architecture], Clfs_management_244be38f-f0dc-45db-b0c2-ccdee1290840.xml, kernel.clfsmgmthandlelogfilefull, wdm/ClfsMgmtHandleLogFileFull
f1_keywords:
 - "wdm/ClfsMgmtHandleLogFileFull"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsMgmtHandleLogFileFull
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsMgmtHandleLogFileFull function


## -description


The <b>ClfsMgmtHandleLogFileFull</b> routine attempts to make more space available in a log. It might make more space available by adding containers to the log, or it might ask clients to move their log tails.


## -parameters




### -param Client [in]

The client that is requesting CLFS management to make space available in the log. The value of this parameter should be the <b>CLFS_MGMT_CLIENT</b> structure that is obtained through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a> routine.


## -returns



The <b>ClfsMgmtHandleLogFileFull</b> routine returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The client is not managing a log.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The value that was supplied for the <i>Client</i> parameter either was <b>NULL</b> or does not represent a valid client.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOG_FULL_HANDLER_IN_PROGRESS</b></dt>
</dl>
</td>
<td width="60%">
CLFS management is already attempting to resolve a log file full condition for this client.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
CLFS management was not able to process the request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
CLFS management is processing the request to create space in the log. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The requested amount of space is available in the log.

</td>
</tr>
</table>
 




## -remarks



To make more space available in the log, the <b>ClfsMgmtHandleLogFileFull</b> routine first tries to add more containers to the log in accordance with the growth rate, new container size, and maximum size policies. If more containers cannot be added, then the <b>ClfsMgmtHandleLogFileFull</b> routine tries to free existing space by invoking one or more clients' <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_advance_tail_callback">ClfsAdvanceTailCallback</a> functions.

If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING, the client's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a> function will be called when the request to make space in the log has been completed.

If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_LOG_FULL_HANDLER_IN_PROGRESS, the client has already requested CLFS management to handle a log file full condition. The client's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a> function will not be called a second time.

If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_SUCCESS, the call completed synchronously, and the client's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a> function will not be invoked.

If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING, then CLFS management is in the process of trying to free space in the log, and will call the client's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a> function when the log file full condition has been handled. If the log is pinned, CLFS management will call the client's <i>ClfsLogGrowthCompleteCallback</i> function with the <i>LogIsPinned</i> parameter set to <b>TRUE</b> before the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING.

<div class="alert"><b>Important</b>    It is possible that the client's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a> function could be called before the call to <b>ClfsMgmtHandleLogFileFull</b> returns.</div>
<div> </div>
<div class="alert"><b>Important</b>    If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING, you should not call the <b>ClfsMgmtHandleLogFileFull</b> routine again for this client until the client's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a> function has been called.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_advance_tail_callback">ClfsAdvanceTailCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a>
 

 

