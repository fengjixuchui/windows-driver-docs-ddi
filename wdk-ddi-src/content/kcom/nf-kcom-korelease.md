---
UID: NF:kcom.KoRelease
title: KoRelease function (kcom.h)
description: The KoRelease function decrements the reference count for the calling interface on an object.
old-location: stream\korelease.htm
tech.root: stream
ms.assetid: 59be582c-0f56-45d8-b407-e588ee0f7f8b
ms.date: 04/23/2018
ms.keywords: KoRelease, KoRelease function [Streaming Media Devices], kcom/KoRelease, ksfunc_5a688121-dc73-48fe-8b85-1f6c14fb3a22.xml, stream.korelease
ms.topic: function
f1_keywords:
 - "kcom/KoRelease"
req.header: kcom.h
req.include-header: Kcom.h
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
- KoRelease
product:
- Windows
targetos: Windows
req.typenames: 
---

# KoRelease function


## -description


<i>This function is intended for internal use only.</i>

The <b>KoRelease</b> function decrements the reference count for the calling interface on an object. 


## -parameters




### -param ClassId [in]

The CLSID of the object whose reference count will be decremented.


