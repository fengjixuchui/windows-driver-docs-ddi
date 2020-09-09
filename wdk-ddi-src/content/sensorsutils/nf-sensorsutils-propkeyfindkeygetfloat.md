---
UID: NF:sensorsutils.PropKeyFindKeyGetFloat
title: PropKeyFindKeyGetFloat function (sensorsutils.h)
description: This routine gets a single precision floating point value from a PROPVARIANT within a collection list based on the PROPERTYKEY.
ms.assetid: ce0f82e3-6537-4423-b7d5-7c440657d245
ms.date: 08/08/2018
keywords: ["PropKeyFindKeyGetFloat function"]
tech.root: sensors
ms.keywords: PropKeyFindKeyGetFloat
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
 - PropKeyFindKeyGetFloat
 - sensorsutils/PropKeyFindKeyGetFloat
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - PropKeyFindKeyGetFloat
product:
 - Windows
---

# PropKeyFindKeyGetFloat function


## -description

This routine gets a single precision floating point value from a PROPVARIANT within a collection list based on the PROPERTYKEY.

## -parameters

### -param pList

[in] Pointer to the list of PROPVARIANT collection.

### -param pKey

[in] Pointer to a PROPERTYKEY for the target PROPVARIANT.

### -param pRetValue

[out] Pointer to the output buffer.

## -returns

This function returns one of the following NTSTATUS codes:

* STATUS_INVALID_PARAMETER if pList, pKey or, pRetValue is nullptr.
* STATUS_NOT_FOUND if the element identified by pKey was not found.
* STATUS_SUCCESS on success.

## -remarks

## -see-also

