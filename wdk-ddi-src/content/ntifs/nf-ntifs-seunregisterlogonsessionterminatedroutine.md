---
UID: NF:ntifs.SeUnregisterLogonSessionTerminatedRoutine
title: SeUnregisterLogonSessionTerminatedRoutine function (ntifs.h)
description: The SeUnregisterLogonSessionTerminatedRoutine routine unregisters a callback routine that was registered by an earlier call to SeRegisterLogonSessionTerminatedRoutine.
old-location: ifsk\seunregisterlogonsessionterminatedroutine.htm
tech.root: ifsk
ms.assetid: 74f24296-cd42-402b-a61f-0199c4a07fd0
ms.date: 04/16/2018
keywords: ["SeUnregisterLogonSessionTerminatedRoutine function"]
ms.keywords: SeUnregisterLogonSessionTerminatedRoutine, SeUnregisterLogonSessionTerminatedRoutine routine [Installable File System Drivers], ifsk.seunregisterlogonsessionterminatedroutine, ntifs/SeUnregisterLogonSessionTerminatedRoutine, seref_dbf0d7bc-c252-4805-99e1-075ce9e08ddc.xml
f1_keywords:
 - "ntifs/SeUnregisterLogonSessionTerminatedRoutine"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeUnregisterLogonSessionTerminatedRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeUnregisterLogonSessionTerminatedRoutine function


## -description


The <b>SeUnregisterLogonSessionTerminatedRoutine</b> routine unregisters a callback routine that was registered by an earlier call to <b>SeRegisterLogonSessionTerminatedRoutine</b>.


## -parameters




### -param CallbackRoutine [in]

Address of routine that was originally passed in to <b>SeRegisterLogonSessionTerminatedRoutine</b>.


## -returns



<b>SeUnregisterLogonSessionTerminatedRoutine</b> can return one of the following:

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
The callback routine was successfully removed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The value of <i>CallbackRoutine</i> is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A list entry could not be found for the callback routine.

</td>
</tr>
</table>
 




## -remarks



Each call to <b>SeRegisterLogonSessionTerminatedRoutine</b> must be matched by a subsequent call to <b>SeUnregisterLogonSessionTerminatedRoutine</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-semarklogonsessionforterminationnotification">SeMarkLogonSessionForTerminationNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seregisterlogonsessionterminatedroutine">SeRegisterLogonSessionTerminatedRoutine</a>
 

 

