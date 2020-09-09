---
UID: NE:ehstorioctl._PDO_CAPS
title: _PDO_CAPS (ehstorioctl.h)
description: This enumeration describes the capabilities of Physical Device Objects (PDOs).
old-location: storage\pdo_caps.htm
tech.root: storage
ms.assetid: 78b6f3c7-bb42-4e93-8128-28b6f8e11dda
ms.date: 03/29/2018
keywords: ["PDO_CAPS enumeration"]
ms.keywords: PDO_CAPABILITY_INC512_CLEAR, PDO_CAPABILITY_INC512_SET, PDO_CAPABILITY_UNDEFINED, PDO_CAPS, PDO_CAPS enumeration [Storage Devices], _PDO_CAPS, ehstorioctl/PDO_CAPABILITY_INC512_CLEAR, ehstorioctl/PDO_CAPABILITY_INC512_SET, ehstorioctl/PDO_CAPABILITY_UNDEFINED, ehstorioctl/PDO_CAPS, storage.pdo_caps, structs-silo_bb81f7e7-c317-4937-87de-b38832944fe5.xml
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
targetos: Windows
req.typenames: PDO_CAPS
f1_keywords:
 - _PDO_CAPS
 - ehstorioctl/_PDO_CAPS
 - PDO_CAPS
 - ehstorioctl/PDO_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorIoctl.h
api_name:
 - PDO_CAPS
---

# _PDO_CAPS enumeration


## -description

This enumeration describes the capabilities of Physical Device Objects (PDOs).

## -enum-fields

### -field PDO_CAPABILITY_UNDEFINED

Command data block size granularity is undefined.

### -field PDO_CAPABILITY_INC512_SET

Command data block size granularity of 512 bytes is supported.

### -field PDO_CAPABILITY_INC512_CLEAR

Command data block size granularity of 1 byte is supported.

## -remarks

A silo must support either PDO_CAPABILITY_INC512_SET or PDO_CAPABILITY_INC512_CLEAR. It may also indicate that both values are supported by returning a logical OR of these two bits.

