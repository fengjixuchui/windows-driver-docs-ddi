---
UID: NF:ntddk.RtlIsRoot
title: RtlIsRoot macro (ntddk.h)
description: The RtlIsRoot routine determines whether the specified node is the root node of a splay link tree.
old-location: ifsk\rtlisroot.htm
tech.root: ifsk
ms.assetid: 74b3894e-972f-430b-bb8f-20fa46bf8b7d
ms.date: 04/16/2018
keywords: ["RtlIsRoot macro"]
ms.keywords: RtlIsRoot, RtlIsRoot routine [Installable File System Drivers], ifsk.rtlisroot, ntddk/RtlIsRoot, rtlref_d7c73e66-d8b8-4a18-a987-d61f13f48dc4.xml
f1_keywords:
 - "ntddk/RtlIsRoot"
 - "RtlIsRoot"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- RtlIsRoot
targetos: Windows
req.typenames: 
---

# RtlIsRoot macro


## -description


The <b>RtlIsRoot</b> routine determines whether the specified node is the root node of a splay link tree. 


## -parameters




### -param Links [in]

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 



## -remarks

**RtlIsRoot** returns TRUE if the node at Links has no parent node, FALSE otherwise. 


Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlIsRoot</b> must be running at IRQL <= DISPATCH_LEVEL if the splay link tree or just-initialized node at <i>Links</i> is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializesplaylinks">RtlInitializeSplayLinks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisleftchild">RtlIsLeftChild</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisrightchild">RtlIsRightChild</a>
 

 

