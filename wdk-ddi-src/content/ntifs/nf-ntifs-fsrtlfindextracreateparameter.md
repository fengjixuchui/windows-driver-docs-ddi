---
UID: NF:ntifs.FsRtlFindExtraCreateParameter
title: FsRtlFindExtraCreateParameter function (ntifs.h)
description: The FsRtlFindExtraCreateParameter routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found.
old-location: ifsk\fsrtlfindextracreateparameter.htm
tech.root: ifsk
ms.assetid: e72958d0-b7ff-45b6-bdd2-f894d5b44cf4
ms.date: 04/16/2018
ms.keywords: FsRtlFindExtraCreateParameter, FsRtlFindExtraCreateParameter routine [Installable File System Drivers], fsrtlref_3536c7a7-2d3c-4aa5-9a91-5579a8108655.xml, ifsk.fsrtlfindextracreateparameter, ntifs/FsRtlFindExtraCreateParameter
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlFindExtraCreateParameter"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlFindExtraCreateParameter routine is available starting with Windows Vista.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlFindExtraCreateParameter
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlFindExtraCreateParameter function


## -description


The <b>FsRtlFindExtraCreateParameter</b> routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found.


## -parameters




### -param EcpList [in]

Pointer to the ECP list structure that <b>FsRtlFindExtraCreateParameter</b> uses to search for the ECP context structure, supplied by the <i>EcpType</i> parameter.


### -param EcpType [in]

Pointer to a GUID that uniquely identifies the ECP context structure.  This GUID value is used by the <b>FsRtlFindExtraCreateParamter</b> routine to determine if the ECP context structure exists in the ECP list, supplied by the <i>EcpList</i> parameter.


### -param EcpContext [out, optional]

Optional parameter that receives a pointer to the found ECP context structure.  If the ECP context structure is not found in the ECP list, <i>EcpContext</i> is set to <b>NULL</b>.  If <i>EcpContext</i> is set to <b>NULL</b> by the caller, the return value of <b>FsRtlFindExtraCreateParamter</b> can be used to determine if the ECP context structure is in the ECP list.


### -param EcpContextSize [out, optional]

Optional parameter that receives the size, in bytes, of the found ECP context structure.  If the ECP context structure is not found, <i>EcpContextSize</i> is set to zero.


## -returns



<b>FsRtlFindExtraCreateParameter</b> returns one of the following NTSTATUS values:

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
<b>FsRtlFindExtraCreateParameter </b>found the specified ECP context structure in the specified ECP list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
<b>FsRtlFindExtraCreateParameter</b> didn't find the specified ECP context structure  in the specified ECP list.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<b>FltAllocateExtraCreateParameterFromLookasideList</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>
 

 

