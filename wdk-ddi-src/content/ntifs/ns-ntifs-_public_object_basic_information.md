---
UID: NS:ntifs._PUBLIC_OBJECT_BASIC_INFORMATION
title: _PUBLIC_OBJECT_BASIC_INFORMATION (ntifs.h)
description: The PUBLIC_OBJECT_BASIC_INFORMATION structure holds a subset of the full information that is available for an object.
old-location: ifsk\public_object_basic_information.htm
tech.root: ifsk
ms.assetid: 2190f88e-6905-4e58-9523-2b6d4864c776
ms.date: 04/16/2018
keywords: ["PUBLIC_OBJECT_BASIC_INFORMATION structure"]
ms.keywords: "*PPUBLIC_OBJECT_BASIC_INFORMATION, PPUBLIC_OBJECT_BASIC_INFORMATION, PPUBLIC_OBJECT_BASIC_INFORMATION structure pointer [Installable File System Drivers], PUBLIC_OBJECT_BASIC_INFORMATION, PUBLIC_OBJECT_BASIC_INFORMATION structure [Installable File System Drivers], _PUBLIC_OBJECT_BASIC_INFORMATION, ifsk.public_object_basic_information, ntifs/PPUBLIC_OBJECT_BASIC_INFORMATION, ntifs/PUBLIC_OBJECT_BASIC_INFORMATION, objectstructures_f0dec604-d95c-47b4-aedc-168a3ae1dedc.xml"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Microsoft Windows 2000.
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
targetos: Windows
req.typenames: PUBLIC_OBJECT_BASIC_INFORMATION, *PPUBLIC_OBJECT_BASIC_INFORMATION
f1_keywords:
 - _PUBLIC_OBJECT_BASIC_INFORMATION
 - ntifs/_PUBLIC_OBJECT_BASIC_INFORMATION
 - PPUBLIC_OBJECT_BASIC_INFORMATION
 - ntifs/PPUBLIC_OBJECT_BASIC_INFORMATION
 - PUBLIC_OBJECT_BASIC_INFORMATION
 - ntifs/PUBLIC_OBJECT_BASIC_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - PUBLIC_OBJECT_BASIC_INFORMATION
---

# _PUBLIC_OBJECT_BASIC_INFORMATION structure


## -description

The PUBLIC_OBJECT_BASIC_INFORMATION structure holds a subset of the full information that is available for an object.

## -struct-fields

### -field Attributes

Specifies the attributes of the object.

### -field GrantedAccess

Specifies a mask that represents the granted access to the object.

### -field HandleCount

Specifies the number of handles to the object.

### -field PointerCount

Specifies the number of pointers at an object.

### -field Reserved

Reserved for system use.

