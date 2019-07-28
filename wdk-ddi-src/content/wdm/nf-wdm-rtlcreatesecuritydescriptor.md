---
UID: NF:wdm.RtlCreateSecurityDescriptor
title: RtlCreateSecurityDescriptor function (wdm.h)
description: The RtlCreateSecurityDescriptor routine initializes a new absolute-format security descriptor. On return, the security descriptor is initialized with no system ACL, no discretionary ACL, no owner, no primary group, and all control flags set to zero.
old-location: kernel\rtlcreatesecuritydescriptor.htm
tech.root: kernel
ms.assetid: f9e08a57-c9dd-4703-b29d-c169ba77f194
ms.date: 04/30/2018
ms.keywords: RtlCreateSecurityDescriptor, RtlCreateSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_3e7817b3-76e0-4acb-b8a3-af78219ffb85.xml, kernel.rtlcreatesecuritydescriptor, wdm/RtlCreateSecurityDescriptor
ms.topic: function
f1_keywords:
 - "wdm/RtlCreateSecurityDescriptor"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlCreateSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCreateSecurityDescriptor function


## -description


The <b>RtlCreateSecurityDescriptor</b> routine initializes a new absolute-format security descriptor. On return, the security descriptor is initialized with no system ACL, no discretionary ACL, no owner, no primary group, and all control flags set to zero.


## -parameters




### -param SecurityDescriptor [out]

Pointer to the buffer for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> to be initialized.


### -param Revision [in]

Specifies the revision level to assign to the security descriptor. Set this parameter to SECURITY_DESCRIPTOR_REVISION.


## -returns



<b>RtlCreateSecurityDescriptor</b> can return one of the following.

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
The call completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an unsupported value  for <i>Revision</i>.

</td>
</tr>
</table>
 




## -remarks



A successful call to this routine initializes a security descriptor. The fields in this descriptor are set to initial values that indicate that there are no security constraints.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtllengthsecuritydescriptor">RtlLengthSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlsetdaclsecuritydescriptor">RtlSetDaclSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>
 

 

