---
UID: NF:ntifs.SecLookupAccountSid
title: SecLookupAccountSid function (ntifs.h)
description: SecLookupAccountSid accepts a security identifier (SID) as input. It retrieves the name of the account for this SID and the name of the first domain on which this SID is found.
old-location: ifsk\seclookupaccountsid.htm
tech.root: ifsk
ms.assetid: 7237a041-46e0-4211-97c1-96d309ada602
ms.date: 04/16/2018
ms.keywords: SecLookupAccountSid, SecLookupAccountSid function [Installable File System Drivers], ifsk.seclookupaccountsid, ksecddref_ba65e59c-5c9a-47bb-bf2c-9b3b8c727bb6.xml, ntifs/SecLookupAccountSid
ms.topic: function
f1_keywords:
 - "ntifs/SecLookupAccountSid"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This SecLookupAccountSid function is only available on Windows XP and later.
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
req.lib: Ksecdd.lib
req.dll: 
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ksecdd.lib
- Ksecdd.dll
api_name:
- SecLookupAccountSid
product:
- Windows
targetos: Windows
req.typenames: 
---

# SecLookupAccountSid function


## -description


<b>SecLookupAccountSid</b> accepts a security identifier (SID) as input. It retrieves the name of the account for this SID and the name of the first domain on which this SID is found.


## -parameters




### -param Sid [in]

A pointer to the SID to look up. 


### -param NameSize [out]

A pointer to a variable that specifies the size of the <i>NameBuffer</i>. On input, this value specifies the size in bytes of the input <i>NameBuffer</i>. If the function fails because the buffer is too small, this variable receives the required buffer size. On success, this variable contains the size of the returned <i>NameBuffer</i>.


### -param NameBuffer [in, out]

A pointer to the <i>NameBuffer</i>. 


### -param OPTIONAL

<p>A pointer to an optional variable that specifies the size of the <i>ReferencedDomain</i> parameter. On input, this value specifies the size of the <i>ReferencedDomain</i> buffer. If the function fails because the buffer is too small, this variable receives the required buffer size. If the <i>ReferencedDomain</i> parameter is <b>NULL</b>, this parameter must be zero.</p>


### -param NameUse [out]

A pointer to a SID_NAME_USE enumerated type that indicates the type of the account when the function returns. 


## -returns



<b>SecLookupAccountSid</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>SEC_E_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The process ID associated with the currently executing thread does not match the current process ID. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer size for the <i>NameBuffer</i> or the <i>ReferencedDomain</i> parameter was too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The length of the <i>Name</i> parameter exceeded the length allowed in a message to the Local System Authority (LSA). 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
It was not possible to allocate sufficient memory for a temporary internal buffer used by this function.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NONE_MAPPED</b></dt>
</dl>
</td>
<td width="60%">
The <i>Sid</i> parameter could not be found. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl>
</td>
<td width="60%">
This process has terminated so it is not possible to establish a local procedure call (LPC) connection.

</td>
</tr>
</table>
 




## -remarks



<b>SecLookupAccountSid</b> attempts to find a name for the specified SID by first checking a list of well-known SIDs. If the supplied SID does not correspond to a well-known SID, the function checks built-in and administratively defined local accounts. Next, the function checks the primary domain. Security identifiers not recognized by the primary domain are checked against the trusted domains that correspond to their SID prefixes.

If the function cannot find an account name for the SID, <b>SecLookupAccountSid</b> fails. This can occur if a network time-out prevents the function from finding the name. It also occurs for SIDs that have no corresponding account name, such as a logon SID that identifies a logon session.

In addition to looking up SIDs for local accounts, local domain accounts, and explicitly trusted domain accounts, <b>SecLookupAccountSid</b> can look up SIDs for any account in any domain in the forest, including SIDs that appear only in the SIDhistory field of an account in the forest. The SIDhistory field stores former SIDs of an account that has been moved from another domain. To look up a SID, <b>SecLookupAccountSid</b> queries the global catalog of the forest. 

<b>SecLookupAccountSid</b> is equivalent to the Win32 <b>LookupAccountSid</b> function. 

<b>SecLookupAccountSid</b> is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. <b>SecLookupAccountSid</b> cannot be used during paging file I/O. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_sid_name_use">SID_NAME_USE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554795">SecLookupAccountName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556582">SecLookupWellKnownSid</a>
 

 

