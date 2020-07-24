---
UID: NF:wdm.ClfsGetContainerName
title: ClfsGetContainerName function (wdm.h)
description: The ClfsGetContainerName routine returns the path name of a specified container.
old-location: kernel\clfsgetcontainername.htm
tech.root: kernel
ms.assetid: 727b2e29-9e2d-4386-a30b-5727e1261fad
ms.date: 04/30/2018
keywords: ["ClfsGetContainerName function"]
ms.keywords: ClfsGetContainerName, ClfsGetContainerName routine [Kernel-Mode Driver Architecture], Clfs_dce31248-386b-4f6d-8e88-55ef9d70fe84.xml, kernel.clfsgetcontainername, wdm/ClfsGetContainerName
f1_keywords:
 - "wdm/ClfsGetContainerName"
 - "ClfsGetContainerName"
req.header: wdm.h
req.include-header: Wdm.h
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
- ClfsGetContainerName
targetos: Windows
req.typenames: 
---

# ClfsGetContainerName function


## -description


The <b>ClfsGetContainerName</b> routine returns the path name of a specified container.


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents a CLFS log. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.


### -param cidLogicalContainer [in]

The logical identifier of a container in the CLFS log.


### -param puszContainerName [out]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure. The <b>Buffer</b> member of <i>puszContainerName</i> must point to a caller-allocated buffer that receives the path name of the container. The <b>MaximumLength</b> member must supply the size of the buffer.


### -param pcActualLenContainerName [out, optional]

A pointer to a ULONG-typed variable that receives the actual length, in Unicode characters, of the container's path name. This parameter can be <b>NULL</b>.


## -returns



<b>ClfsGetContainerName</b> returns one of the status codes defined in Ntstatus.h. The following table gives the meanings of various return values.

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
The <b>Buffer</b> member of <i>puszContainerName</i> receives the full path name of the container. If <i>pcActualLenContainerName</i> is not <b>NULL</b>, it receives the actual length, in Unicode characters, of the full path name.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The actual length, in Unicode characters, of the full path name is larger than <i>puszContainerName</i>-><b>MaximumLength</b>. The <b>Buffer</b> member of <i>puszContainerName</i> receives the full path name of the container truncated to the number of characters specified by <i>puszContainerName</i>-><b>MaximumLength</b>. If <i>pcActualLenContainerName</i> is not <b>NULL</b>, it receives the actual length, in Unicode characters, of the full path name. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other</b></dt>
</dl>
</td>
<td width="60%">
On return, the contents of <i>puszContainerName</i>-><b>Buffer</b> and <i>pcActualLenContainerName</i> are undefined.

</td>
</tr>
</table>
 




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainer">ClfsAddLogContainer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsremovelogcontainer">ClfsRemoveLogContainer</a>
 

 

