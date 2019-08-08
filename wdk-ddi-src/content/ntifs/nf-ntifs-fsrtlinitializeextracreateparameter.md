---
UID: NF:ntifs.FsRtlInitializeExtraCreateParameter
title: FsRtlInitializeExtraCreateParameter function (ntifs.h)
description: The FsRtlInitializeExtraCreateParameter routine initializes an extra create parameter (ECP) context structure.
old-location: ifsk\fsrtlinitializeextracreateparameter.htm
tech.root: ifsk
ms.assetid: e3be12e4-84f3-4bd5-af9a-26ad89948e50
ms.date: 04/16/2018
ms.keywords: FsRtlInitializeExtraCreateParameter, FsRtlInitializeExtraCreateParameter routine [Installable File System Drivers], fsrtlref_266d4d18-e024-42e8-8ca1-fa8b6fabef9b.xml, ifsk.fsrtlinitializeextracreateparameter, ntifs/FsRtlInitializeExtraCreateParameter
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlInitializeExtraCreateParameter"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlInitializeExtraCreateParameter routine is available starting with Windows 7.
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
- FsRtlInitializeExtraCreateParameter
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlInitializeExtraCreateParameter function


## -description


The <b>FsRtlInitializeExtraCreateParameter</b> routine initializes an extra create parameter (ECP) context structure. 


## -parameters




### -param Ecp [in]

Pointer to the ECP context structure to initialize. 


### -param EcpFlags [in]

Defines initialization options. Currently, no flags are defined. 


### -param CleanupCallback [in, optional]

Optional pointer to a filter-defined cleanup callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>. The cleanup callback routine is called when the ECP context structure (created by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545609">FsRtlAllocateExtraCreateParameter</a> routine) is deleted. Set this parameter to <b>NULL</b> if a cleanup callback routine is not applicable. 


### -param TotalSize [in]

The size, in bytes, of the ECP context structure to initialize. 


### -param EcpType [in]

Pointer to a GUID that indicates the type of ECP for which the context structure will be initialized. For more information about ECPs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/using-extra-create-parameters-with-an-irp-mj-create-operation">Using Extra Create Parameters with an IRP_MJ_CREATE Operation</a>. 


### -param ListAllocatedFrom [in, optional]

Optional pointer to the list from which the ECP context structure is allocated. 


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545609">FsRtlAllocateExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551124">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>
 

 

