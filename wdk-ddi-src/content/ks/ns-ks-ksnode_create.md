---
UID: NS:ks.__unnamed_struct_25
title: KSNODE_CREATE (ks.h)
description: The KSNODE_CREATE structure describes the set of information used to create the node handle.
old-location: stream\ksnode_create.htm
tech.root: stream
ms.assetid: db08cc72-3797-46e3-8e4d-d8469dc126ab
ms.date: 04/23/2018
keywords: ["KSNODE_CREATE structure"]
ms.keywords: "*PKSNODE_CREATE, KSNODE_CREATE, KSNODE_CREATE structure [Streaming Media Devices], PKSNODE_CREATE, PKSNODE_CREATE structure pointer [Streaming Media Devices], ks-struct_2fb3dcb7-5945-4f8a-b1f1-945910ec8396.xml, ks/KSNODE_CREATE, ks/PKSNODE_CREATE, stream.ksnode_create"
f1_keywords:
 - "ks/KSNODE_CREATE"
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
- KSNODE_CREATE
product:
- Windows
targetos: Windows
req.typenames: KSNODE_CREATE, *PKSNODE_CREATE
---

# KSNODE_CREATE structure


## -description


The KSNODE_CREATE structure describes the set of information used to create the node handle.


## -struct-fields




### -field CreateFlags

Set to zero.


### -field Node

Indicates what node a handle should be created for. This refers to the node identifiers returned when querying topology information. A node identifier of −1 may be used to refer to the collection of nodes as a whole, if the filter supports it.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kscreatetopologynode">KsCreateTopologyNode</a>
 

 

