---
UID: NF:ntifs.SeAppendPrivileges
title: SeAppendPrivileges function (ntifs.h)
description: The SeAppendPrivileges routine appends additional privileges to the privilege set in an access state structure.
old-location: ifsk\seappendprivileges.htm
tech.root: ifsk
ms.assetid: b7a9142a-b6db-4a64-a5e3-d03d39ac3d09
ms.date: 04/16/2018
ms.keywords: SeAppendPrivileges, SeAppendPrivileges routine [Installable File System Drivers], ifsk.seappendprivileges, ntifs/SeAppendPrivileges, seref_c48fbff8-669f-4138-8f55-84bc083d9af5.xml
ms.topic: function
f1_keywords:
 - "ntifs/SeAppendPrivileges"
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
- SeAppendPrivileges
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeAppendPrivileges function


## -description


The <b>SeAppendPrivileges</b> routine appends additional privileges to the privilege set in an access state structure.


## -parameters




### -param AccessState [in, out]

Pointer to a caller-allocated ACCESS_STATE structure representing the current access request. 


### -param Privileges [in]

Pointer to a caller-allocated PRIVILEGE_SET structure containing the privileges to be added. 


## -returns



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
The append operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>SeAppendPrivileges</b> encountered a pool allocation failure when allocating memory for the new privileges.

</td>
</tr>
</table>
 




## -remarks



Initially, an access state structure can hold up to three privileges in its privilege set. If more than three privileges need to be stored, <b>SeAppendPrivileges</b> allocates a new privilege set from the paged pool and copies into it both the current privileges and the new privileges.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_access_state">ACCESS_STATE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551860(v=vs.85)">PRIVILEGE_SET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-seaccesscheck">SeAccessCheck</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sefreeprivileges">SeFreePrivileges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seprivilegecheck">SePrivilegeCheck</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sesetaccessstategenericmapping">SeSetAccessStateGenericMapping</a>
 

 

