---
UID: NF:sensorsutils.PropKeyFindKeyGetDouble
title: PropKeyFindKeyGetDouble function (sensorsutils.h)
description: This routine gets a double precision floating point value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.assetid: 8dc6e964-d55a-4b06-b571-985e1c302e84
ms.date: 08/08/2018
keywords: ["PropKeyFindKeyGetDouble function"]
tech.root: sensors
ms.keywords: PropKeyFindKeyGetDouble
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - PropKeyFindKeyGetDouble
 - sensorsutils/PropKeyFindKeyGetDouble
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - PropKeyFindKeyGetDouble
product:
 - Windows
---

# PropKeyFindKeyGetDouble function


## -description

This routine gets a double precision floating point value from a PROPVARIANT within a collection list based on the PROPERTYKEY.

## -parameters

### -param pList

[in] Pointer to the list of PROPVARIANT collection.

### -param pKey

[in] Pointer to a PROPERTYKEY for the target PROPVARIANT.

### -param pRetValue

[out] Pointer to a PROPERTYKEY for the target PROPVARIANT.

## -returns

This function returns an NTSTATUS code that represents:

* STATUS_INVALID_PARAMETER if pList, pKey or, pRetValue is nullptr.
* STATUS_NOT_FOUND if the element identified by pKey was not found.
* STATUS_SUCCESS if the function was successful.

## -remarks

## -see-also

