---
UID: NF:sensorsutils.CollectionsListGetMarshalledSize
title: CollectionsListGetMarshalledSize function (sensorsutils.h)
description: Returns the size needed to accommodate serializing and marshaling a collection list, including embedded memory.
ms.assetid: a3773a22-cd27-4944-812c-e18054df4e57
ms.date: 08/08/2018
ms.topic: function
f1_keywords:
 - "sensorsutils/CollectionsListGetMarshalledSize"
tech.root: sensors
ms.keywords: CollectionsListGetMarshalledSize
req.header: sensorsutils.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- sensorsutils.h
api_name: 
- CollectionsListGetMarshalledSize
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# CollectionsListGetMarshalledSize function


## -description

This routine is maintained for compatibility. It returns the size needed to accommodate serializing and marshaling a collection list, including embedded memory. It does the same thing as [CollectionsListGetSerializedSize](nf-sensorsutils-collectionslistgetserializedsize.md).


## -parameters

### -param Collection

[in] Pointer to a sensor collection list.

## -returns

This function returns a ULONG that represents the size of the data.

## -remarks

## -see-also
