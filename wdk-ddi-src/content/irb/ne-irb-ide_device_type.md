---
UID: NE:irb.__unnamed_enum_0
title: IDE_DEVICE_TYPE (irb.h)
description: The IDE_DEVICE_TYPE enumeration type indicates the device type.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_device_type.htm
tech.root: storage
ms.assetid: 6d94189f-d6ab-40ad-85e5-f4efe8c30ed8
ms.date: 03/29/2018
keywords: ["IDE_DEVICE_TYPE enumeration"]
ms.keywords: DeviceIsAta, DeviceIsAtapi, DeviceNotExist, DeviceUnknown, IDE_DEVICE_TYPE, IDE_DEVICE_TYPE enumeration [Storage Devices], irb/DeviceIsAta, irb/DeviceIsAtapi, irb/DeviceNotExist, irb/DeviceUnknown, irb/IDE_DEVICE_TYPE, storage.ide_device_type, structs-ATA_ebe5b232-fdb1-4be8-ada6-54e2dc3d09a8.xml
req.header: irb.h
req.include-header: Irb.h
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
req.typenames: IDE_DEVICE_TYPE
f1_keywords:
 - IDE_DEVICE_TYPE
 - irb/IDE_DEVICE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - irb.h
api_name:
 - IDE_DEVICE_TYPE
---

# IDE_DEVICE_TYPE enumeration


## -description

The IDE_DEVICE_TYPE enumeration type indicates the device type.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -enum-fields

### -field DeviceUnknown

Indicates that the device does not communicate by means of a known protocol.

### -field DeviceIsAta

Indicates an ATA device.

### -field DeviceIsAtapi

Indicates an ATAPI device.

### -field DeviceNotExist

Indicates that the device does not exist.