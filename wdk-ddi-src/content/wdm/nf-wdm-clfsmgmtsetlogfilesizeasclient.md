---
UID: NF:wdm.ClfsMgmtSetLogFileSizeAsClient
title: ClfsMgmtSetLogFileSizeAsClient function (wdm.h)
description: The ClfsMgmtSetLogFileSizeAsClient routine sets the log file size by adding containers to a client log or deleting containers from a client log.
old-location: kernel\clfsmgmtsetlogfilesizeasclient_.htm
tech.root: kernel
ms.assetid: C049A6BE-6E2B-46F2-B7CF-316E4CDB35E4
ms.date: 04/30/2018
keywords: ["ClfsMgmtSetLogFileSizeAsClient function"]
ms.keywords: ClfsMgmtSetLogFileSizeAsClient, ClfsMgmtSetLogFileSizeAsClient , ClfsMgmtSetLogFileSizeAsClient routine [Kernel-Mode Driver Architecture], kernel.clfsmgmtsetlogfilesizeasclient_, wdm/ClfsMgmtSetLogFileSizeAsClient
f1_keywords:
 - "wdm/ClfsMgmtSetLogFileSizeAsClient"
 - "ClfsMgmtSetLogFileSizeAsClient"
req.header: wdm.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.dll: Clfs.sys
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsMgmtSetLogFileSizeAsClient
targetos: Windows
req.typenames: 
---

# ClfsMgmtSetLogFileSizeAsClient function


## -description


The <b>ClfsMgmtSetLogFileSizeAsClient</b>  routine sets the log file size by adding containers to a client log or deleting containers from a client log.


## -parameters




### -param LogFile [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents the Common Log File System (CLFS) log, or a stream within the log, to which containers are being added or deleted. The value of this parameter is obtained through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a> routine.


### -param ClientCookie [in, optional]

A pointer to a client-supplied cookie. The value of this parameter should be the <b>CLFS_MGMT_CLIENT</b> structure that is obtained through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a> routine.


### -param NewSizeInContainers [in]

The desired size of the log, expressed in the number of containers. There can be at most 1,024 containers for a log file.


### -param ResultingSizeInContainers [out, optional]

The actual size of the log, expressed in the number of containers.


### -param CompletionRoutine [in, optional]

 Not used.


### -param CompletionRoutineData [in, optional]

 Not used. 


## -returns



The <b>ClfsMgmtSetLogFileSizeAsClient</b> routine returns an NTSTATUS value.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The log file size has been set. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>LogFile</i> parameter is <b>NULL</b>, or the contents of the <i>NewSizeInContainers</i> parameter is 1.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>NewSizeInContainers</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOG_POLICY_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The installed set of policies on the log is invalid. This might be due to an invalid <a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/bb540325(v=vs.85)">ClfsMgmtPolicyAutoShrink</a> policy or <a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/bb540328(v=vs.85)">ClfsMgmtPolicyMaximumSize</a> policy.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_COULD_NOT_RESIZE_LOG</b></dt>
</dl>
</td>
<td width="60%">
CLFS management could not delete enough containers to reach the value in <i>NewSizeInContainers</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOG_POLICY_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
A policy on the specified log   prevented the operation from completing. This may occur if CLFS management could not add enough containers to the log to reach the value in <i>NewSizeInContainers</i>. This might be due to a conflict with a policy that the client set.

</td>
</tr>
</table>
 

This routine might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">CLFS Management Library Routines</a>
 

 

