---
UID: NF:ntifs.RtlEqualSid
title: RtlEqualSid function (ntifs.h)
description: The RtlEqualSid routine determines whether two security identifier (SID) values are equal. Two SIDs must match exactly to be considered equal.
old-location: ifsk\rtlequalsid.htm
tech.root: ifsk
ms.assetid: 4976fc27-c28a-46ec-ac07-19505cda8f14
ms.date: 04/16/2018
keywords: ["RtlEqualSid function"]
ms.keywords: RtlEqualSid, RtlEqualSid routine [Installable File System Drivers], ifsk.rtlequalsid, ntifs/RtlEqualSid, rtlref_bc81c0ad-e0e6-4133-a423-4f6c4c264286.xml
f1_keywords:
 - "ntifs/RtlEqualSid"
 - "RtlEqualSid"
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: Any
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlEqualSid
targetos: Windows
req.typenames: 
---

# RtlEqualSid function


## -description


The <b>RtlEqualSid</b> routine determines whether two security identifier (SID) values are equal. Two SIDs must match exactly to be considered equal. 


## -parameters




### -param Sid1 [in]

Pointer to the first SID structure to compare. Must point to a valid SID. 


### -param Sid2 [in]

Pointer to the second SID structure to compare. Must point to a valid SID. 


## -returns



<b>RtlEqualSid</b> returns <b>TRUE</b> if the SID structures are equal, <b>FALSE</b> otherwise. If either SID structure is invalid, the return value is undefined. 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcopysid">RtlCopySid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlequalprefixsid">RtlEqualPrefixSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlvalidsid">RtlValidSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>
 

 

