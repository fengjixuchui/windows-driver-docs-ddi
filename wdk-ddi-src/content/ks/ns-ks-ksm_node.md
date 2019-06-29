---
UID: NS:ks.__unnamed_struct_4
title: KSM_NODE (ks.h)
description: Just as KSP_NODE is used for properties on a node, the KSM_NODE structure is used for methods on a node.
old-location: stream\ksm_node.htm
tech.root: stream
ms.assetid: 0e3f5abb-bf66-40e9-b318-9f6215f3d56c
ms.date: 04/23/2018
ms.keywords: "*PKSM_NODE, KSM_NODE, KSM_NODE structure [Streaming Media Devices], PKSM_NODE, PKSM_NODE structure pointer [Streaming Media Devices], ks-struct_14efff2f-6d11-4055-a4f8-35d9389589b8.xml, ks/KSM_NODE, ks/PKSM_NODE, stream.ksm_node"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSM_NODE
product:
- Windows
targetos: Windows
req.typenames: KSM_NODE, *PKSM_NODE
---

# KSM_NODE structure


## -description


Just as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksp_node">KSP_NODE</a> is used for properties on a node, the KSM_NODE structure is used for methods on a node.


## -struct-fields




### -field Method

A structure of type <a href="https://docs.microsoft.com/previous-versions/ff563398(v=vs.85)">KSMETHOD</a> that specifies the requested method.


### -field NodeId

Specifies the node ID.


### -field Reserved

Reserved for system use. Should be set to zero.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksp_node">KSP_NODE</a>
 

 

