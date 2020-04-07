---
UID: NF:ntifs.SecMakeSPNEx2
title: SecMakeSPNEx2 function (ntifs.h)
description: SecMakeSPNEx2 creates a service provider name string that can be used when it communicates with specific security service providers.
old-location: ifsk\secmakespnex2.htm
tech.root: ifsk
ms.assetid: abb8d45a-a698-41b0-94b3-c658fe3105bb
ms.date: 04/16/2018
keywords: ["SecMakeSPNEx2 function"]
ms.keywords: SecMakeSPNEx2, SecMakeSPNEx2 function [Installable File System Drivers], ifsk.secmakespnex2, ksecddref_be331d16-cc90-4e80-85cd-c2faaecca843.xml, ntifs/SecMakeSPNEx2
f1_keywords:
 - "ntifs/SecMakeSPNEx2"
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This function is available on Windows Vista, Windows Server 2008, and later versions of the Windows operating systems.
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
- SecMakeSPNEx2
product:
- Windows
targetos: Windows
req.typenames: 
---

# SecMakeSPNEx2 function


## -description


<b>SecMakeSPNEx2</b> creates a service provider name string that can be used when it communicates with specific security service providers.


## -parameters




### -param ServiceClass [in]

A pointer to a Unicode string that specifies the service class for the security service provider. 


### -param ServiceName [in]

A pointer to a Unicode string that specifies the service name for the security service provider. 


### -param OPTIONAL

<p>A pointer to an optional Unicode string that specifies the instance name that is used to connect with the security service provider. </p>


### -param Spn [in, out]

A pointer to a Unicode string that receives the security service provider name string that is created by this function.


### -param Allocate [in]

A Boolean variable that indicates if the memory that is used to store the <i>Spn</i> Unicode string should be allocated by this function. If this parameter is <b>TRUE</b>, memory for <i>Spn</i> will be allocated from paged pool.


### -param IsTargetInfoMarshaled [in]

A Boolean variable that indicates that the caller provided a marshaled <i>InTargetInfo</i> structure.  If <i>IsTargetInfoMarshaled</i> is <b>TRUE</b>, <i>InTargetInfo</i>->Buffer points to a string representation of the CREDENTIAL_TARGET_INFORMATION structure as returned by the <b>CredMarshalTargetInfo</b> function.


## -returns



<b>SecMakeSPNEx2</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The <i>Allocate</i> parameter was set to <b>FALSE</b> and one of the following conditions occurred:

The <i>Spn </i>parameter was a <b>NULL</b> pointer.

The maximum length for the <i>Spn</i> Unicode string parameter was too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A total length of the <i>Spn</i> parameter exceeds 65535 bytes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The <i>Allocate</i> parameter was set to <b>TRUE</b>, but the memory allocation request failed.

</td>
</tr>
</table>
 




## -remarks



<b>SecMakeSPNEx2</b> is an enhanced version of <b>SecMakeSPNEx</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556584">SecMakeSPN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556585">SecMakeSPNEx</a>
 

 

