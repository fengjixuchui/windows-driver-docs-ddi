---
UID: NF:ntifs.ZwQueryInformationToken
title: ZwQueryInformationToken function (ntifs.h)
description: The ZwQueryInformationToken routine retrieves a specified type of information about an access token. The calling process must have appropriate access rights to obtain the information.
old-location: kernel\zwqueryinformationtoken.htm
tech.root: kernel
ms.assetid: 554b541b-943a-413e-9803-7dba17d0c6ce
ms.date: 04/30/2018
ms.keywords: NtQueryInformationToken, ZwQueryInformationToken, ZwQueryInformationToken routine [Kernel-Mode Driver Architecture], k111_2f945a17-f3b4-423a-90fa-6f02d240d42d.xml, kernel.zwqueryinformationtoken, ntifs/NtQueryInformationToken, ntifs/ZwQueryInformationToken
ms.topic: function
f1_keywords:
 - "ntifs/ZwQueryInformationToken"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
- ZwQueryInformationToken
- NtQueryInformationToken
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwQueryInformationToken function


## -description


The <b>ZwQueryInformationToken</b> routine retrieves a specified type of information about an access token. The calling process must have appropriate access rights to obtain the information. 


## -parameters




### -param TokenHandle [in]

Handle for an access token from which information is to be retrieved. If <i>TokenInformationClass</i> is set to <b>TokenSource</b>, the handle must have TOKEN_QUERY_SOURCE access. For all other <i>TokenInformationClass</i> values, the handle must have TOKEN_QUERY access. For more information about access rights for access-token objects, see the Security section of the Windows SDK documentation.


### -param TokenInformationClass [in]

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a> enumerated type identifying the type of information to be retrieved. The possible values for this parameter are listed in the <i>TokenInformationClass</i> Value column of the table shown in the description of the <i>TokenInformation</i> parameter.


### -param TokenInformation [out]

Pointer to a caller-allocated buffer that receives the requested information about the token. The structure put into this buffer depends upon the value of <i>TokenInformationClass</i>, as shown in the following table. All structures must be aligned on a 32-bit boundary.

<table>
<tr>
<th><i>TokenInformationClass</i> Value</th>
<th>Effect on <i>TokenInformation</i> Buffer</th>
</tr>
<tr>
<td>
<b>TokenDefaultDacl</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_default_dacl">TOKEN_DEFAULT_DACL</a> structure containing the default <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl">DACL</a> for newly created objects. 

</td>
</tr>
<tr>
<td>
<b>TokenGroups</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a> structure containing the group accounts associated with the token.

</td>
</tr>
<tr>
<td>
<b>TokenImpersonationLevel</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a> value indicating the impersonation level of the token. If the access token is not an impersonation token, the call to <b>ZwQueryInformationToken</b> fails. 

</td>
</tr>
<tr>
<td>
<b>TokenOwner</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_owner">TOKEN_OWNER</a> structure containing the default owner <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid">SID</a> for newly created objects.

</td>
</tr>
<tr>
<td>
<b>TokenPrimaryGroup</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_primary_group">TOKEN_PRIMARY_GROUP</a> structure containing the default primary group SID for newly created objects. 

</td>
</tr>
<tr>
<td>
<b>TokenPrivileges</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_privileges">TOKEN_PRIVILEGES</a> structure containing the token's privileges.

</td>
</tr>
<tr>
<td>
<b>TokenSessionId</b>

</td>
<td>
The buffer receives a 32-bit value specifying the Terminal Services session identifier associated with the token. If the token is associated with the Terminal Server console session, the session identifier is zero. A nonzero session identifier indicates a Terminal Services client session. In a non-Terminal Services environment, the session identifier is zero.

</td>
</tr>
<tr>
<td>
<b>TokenSource</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_source">TOKEN_SOURCE</a> structure containing the source of the token. TOKEN_QUERY_SOURCE access is needed to retrieve this information.

</td>
</tr>
<tr>
<td>
<b>TokenStatistics</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_statistics">TOKEN_STATISTICS</a> structure containing various token statistics.

</td>
</tr>
<tr>
<td>
<b>TokenType</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ne-ntifs-_token_type">TOKEN_TYPE</a> value indicating whether the token is a primary or impersonation token. 

</td>
</tr>
<tr>
<td>
<b>TokenUser</b>

</td>
<td>
The buffer receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_user">TOKEN_USER</a> structure containing the token's user account. 

</td>
</tr>
</table>
 


### -param TokenInformationLength [in]

Length, in bytes, of the caller-allocated <i>TokenInformation</i> buffer. 


### -param ReturnLength [out]

Pointer to a caller-allocated variable that receives the actual length, in bytes, of the information returned in the <i>TokenInformation</i> buffer. If either of the following conditions is true, no data is returned in the <i>TokenInformation</i> buffer: 

<ul>
<li>
The size of the requested token information structure is greater than <i>TokenInformationLength</i>. In this case, <i>ReturnLength</i> receives the actual number of bytes needed to store the requested information. 

</li>
<li>
The value of <i>TokenInformationClass</i> is <b>TokenDefaultDacl</b>, and there is no default DACL established for the token. In this case, <i>ReturnLength</i> receives zero. 

</li>
</ul>

## -returns



<b>ZwQueryInformationToken</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenHandle</i> did not have the required access.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The size of the requested token information structure is greater than <i>TokenInformationLength</i>. The number of bytes required is returned in <i>ReturnLength</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenHandle</i> was not a valid handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenInformationClass</i> was not a valid token information class. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenHandle</i> was not a token handle. 

</td>
</tr>
</table>
 




## -remarks



The <b>ZwQueryInformationToken</b> routine can be used by a file system or file system filter driver to determine the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid">SID</a> of the caller that initiated the request during <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> processing. If <b>TokenUser</b> is specified for the <i>TokenInformationClass</i> parameter passed to <b>ZwQueryInformationToken</b>, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_user">TOKEN_USER</a> structure is returned in the buffer pointed to by the <i>TokenInformation</i> parameter. This returned buffer contains an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid_and_attributes">SID_AND_ATTRIBUTES</a> structure with the user <b>SID</b>.

For more information about security and access control, see the documentation on these topics in the Windows SDK. 

<div class="alert"><b>Note</b>  If the call to the <b>ZwQueryInformationToken</b> function occurs in user mode, you should use the name "<b>NtQueryInformationToken</b>" instead of "<b>ZwQueryInformationToken</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid_and_attributes">SID_AND_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_default_dacl">TOKEN_DEFAULT_DACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_owner">TOKEN_OWNER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_primary_group">TOKEN_PRIMARY_GROUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_privileges">TOKEN_PRIVILEGES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_source">TOKEN_SOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_statistics">TOKEN_STATISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ne-ntifs-_token_type">TOKEN_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_token_user">TOKEN_USER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

