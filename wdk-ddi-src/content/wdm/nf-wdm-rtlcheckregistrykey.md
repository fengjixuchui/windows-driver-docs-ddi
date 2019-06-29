---
UID: NF:wdm.RtlCheckRegistryKey
title: RtlCheckRegistryKey function (wdm.h)
description: The RtlCheckRegistryKey routine checks for the existence of a given named key in the registry.
old-location: kernel\rtlcheckregistrykey.htm
tech.root: kernel
ms.assetid: b752a764-1f7d-4768-9fa2-c8976560f840
ms.date: 04/30/2018
ms.keywords: RtlCheckRegistryKey, RtlCheckRegistryKey routine [Kernel-Mode Driver Architecture], k109_d4610b64-e689-4734-aca9-4536889ae2b9.xml, kernel.rtlcheckregistrykey, wdm/RtlCheckRegistryKey
ms.topic: function
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
- RtlCheckRegistryKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCheckRegistryKey function


## -description


The <b>RtlCheckRegistryKey</b> routine checks for the existence of a given named key in the registry.


## -parameters




### -param RelativeTo [in]

Specifies whether <i>Path</i> is an absolute registry path or is relative to a predefined key path as one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
RTL_REGISTRY_ABSOLUTE

</td>
<td>
Path is an absolute registry path.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_CONTROL

</td>
<td>
Path is relative to <b>\Registry\Machine\System\CurrentControlSet\Control</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_DEVICEMAP

</td>
<td>
Path is relative to <b>\Registry\Machine\Hardware\DeviceMap</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_SERVICES

</td>
<td>
Path is relative to <b>\Registry\Machine\System\CurrentControlSet\Services</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_USER

</td>
<td>
Path is relative to the registry settings for the current user. (For a system process, this is <b>\Users\.Default</b>.)  This is equivalent to HKEY_CURRENT_USER in user mode.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_WINDOWS_NT

</td>
<td>
Path is relative to <b>\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_HANDLE

</td>
<td>
This value should not be passed into this routine. Despite the redundancy of a check for the existence of an already-opened key, it has the side effect of closing the passed handle.

</td>
</tr>
</table>
 


### -param Path [in]

Specifies the registry path according to the <i>RelativeTo</i> value. If RTL_REGISTRY_HANDLE is set, <i>Path</i> is a handle to be used directly.


## -returns



If the given named key exists in the registry along the given relative path, <b>RtlCheckRegistryKey</b> returns STATUS_SUCCESS.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlqueryregistryvalues">RtlQueryRegistryValues</a>
 

 

