---
UID: NF:ks.KsAddObjectCreateItemToObjectHeader
title: KsAddObjectCreateItemToObjectHeader function (ks.h)
description: The KsAddObjectCreateItemToObjectHeader function adds the specified create-item to an empty item in the previously allocated create item list for this object header.
old-location: stream\ksaddobjectcreateitemtoobjectheader.htm
tech.root: stream
ms.assetid: 9946e896-7f1a-4ff2-afa5-9e231047af11
ms.date: 04/23/2018
keywords: ["KsAddObjectCreateItemToObjectHeader function"]
ms.keywords: KsAddObjectCreateItemToObjectHeader, KsAddObjectCreateItemToObjectHeader function [Streaming Media Devices], ks/KsAddObjectCreateItemToObjectHeader, ksfunc_de112daa-c37a-4d5b-b646-5fc45fd8ae1c.xml, stream.ksaddobjectcreateitemtoobjectheader
f1_keywords:
 - "ks/KsAddObjectCreateItemToObjectHeader"
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAddObjectCreateItemToObjectHeader
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAddObjectCreateItemToObjectHeader function


## -description


The <b>KsAddObjectCreateItemToObjectHeader</b> function adds the specified create-item to an empty item in the previously allocated create item list for this object header. An empty item is signified by a <b>NULL</b> create dispatch function in the entry. This function assumes that the caller is serializing multiple changes to the create items list.


## -parameters




### -param Header [in]

Points to the object header that contains the previously allocated child- create table.


### -param Create [in]

Specifies the create dispatch function to use.


### -param Context [in]

Specifies the context parameter.


### -param ObjectClass [in]

Specifies a pointer to a <b>NULL</b>-terminated character string that is used for comparison on create requests. This pointer must remain valid while the object is active.


### -param SecurityDescriptor [in, optional]

Specifies the security descriptor. This must remain valid while the object is active.


## -returns



The <b>KsAddObjectCreateItemToObjectHeader</b> function returns STATUS_SUCCESS if an empty create item slot was found and the item was added. If unsuccessful, it returns STATUS_ALLOTTED_SPACE_EXCEEDED.



