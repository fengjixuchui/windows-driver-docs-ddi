---
UID: NF:ntifs.NtQuerySecurityObject
title: NtQuerySecurityObject function (ntifs.h)
description: The ZwQuerySecurityObject routine retrieves a copy of an object's security descriptor.
old-location: kernel\zwquerysecurityobject.htm
tech.root: kernel
ms.assetid: bc3c494d-890c-4699-a272-62cbcc234cdd
ms.date: 04/30/2018
ms.keywords: NtQuerySecurityObject, ZwQuerySecurityObject, ZwQuerySecurityObject routine [Kernel-Mode Driver Architecture], k111_50bbb447-b993-4020-a8d7-e54f0b31e84e.xml, kernel.zwquerysecurityobject, ntifs/NtQuerySecurityObject, ntifs/ZwQuerySecurityObject
ms.topic: function
f1_keywords:
 - "ntifs/ZwQuerySecurityObject"
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
- ZwQuerySecurityObject
- NtQuerySecurityObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtQuerySecurityObject function


## -description


The <b>NtQuerySecurityObject</b> routine retrieves a copy of an object's security descriptor. 


## -parameters




### -param Handle [in]

Handle for the object whose security descriptor is to be queried. This handle must have the access specified in the Meaning column of the table shown in the description of the <i>SecurityInformation</i> parameter. 


### -param SecurityInformation [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a> value specifying the information to be queried.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DACL_SECURITY_INFORMATION

</td>
<td>
Indicates the discretionary access control list (DACL) of the object is being queried. Requires READ_CONTROL access. 

</td>
</tr>
<tr>
<td>
GROUP_SECURITY_INFORMATION

</td>
<td>
Indicates the primary group identifier of the object is being queried. Requires READ_CONTROL access. 

</td>
</tr>
<tr>
<td>
OWNER_SECURITY_INFORMATION

</td>
<td>
Indicates the owner identifier of the object is being queried. Requires READ_CONTROL access. 

</td>
</tr>
<tr>
<td>
SACL_SECURITY_INFORMATION

</td>
<td>
Indicates the system ACL (SACL) of the object is being queried. Requires ACCESS_SYSTEM_SECURITY access. 

</td>
</tr>
</table>
 


### -param SecurityDescriptor [out]

Caller-allocated buffer that <b>NtQuerySecurityObject</b> fills with a copy of the specified security descriptor. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> structure is returned in self-relative format. 


### -param Length [in]

Size, in bytes, of the buffer pointed to by <i>SecurityDescriptor</i>. 


### -param LengthNeeded [out]

Pointer to a caller-allocated variable that receives the number of bytes required to store the copied security descriptor. 


## -returns



<b>NtQuerySecurityObject</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

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
<i>Handle</i> did not have the required access. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer is too small for the security descriptor. None of the security information was copied to the buffer. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>Handle</i> was not a valid handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
<i>Handle</i> was not a handle of the expected type. 

</td>
</tr>
</table>
 




## -remarks



A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the structure are located contiguously in memory. In absolute form, the structure only contains pointers to the members. 

The NTFS file system imposes a 64K limit on the size of the security descriptor that is written to disk for a file. (The FAT file system does not support security descriptors for files.) Thus a 64K <i>SecurityDescriptor</i> buffer is guaranteed to be large enough to hold the returned <b>SECURITY_DESCRIPTOR</b> structure. 

For more information about security and access control, see the documentation on these topics in the Windows SDK.

Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltquerysecurityobject">FltQuerySecurityObject</a> instead of <b>NtQuerySecurityObject</b>. 

<div class="alert"><b>Note</b>  If the call to the <b>NtQuerySecurityObject</b> function occurs in user mode, you should use the name "<b>NtQuerySecurityObject</b>" instead of "<b>ZwQuerySecurityObject</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltquerysecurityobject">FltQuerySecurityObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567106">ZwSetSecurityObject</a>
 

 

