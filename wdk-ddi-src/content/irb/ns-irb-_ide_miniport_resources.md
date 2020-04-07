---
UID: NS:irb._IDE_MINIPORT_RESOURCES
title: _IDE_MINIPORT_RESOURCES (irb.h)
description: The IDE_MINIPORT_RESOURCES structure is used by the port driver to provide the miniport driver with resources.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_miniport_resources.htm
tech.root: storage
ms.assetid: 867b6152-9846-484f-9eac-07d0f24d55df
ms.date: 03/29/2018
keywords: ["_IDE_MINIPORT_RESOURCES structure"]
ms.keywords: "*PIDE_MINIPORT_RESOURCES, IDE_MINIPORT_RESOURCES, IDE_MINIPORT_RESOURCES structure [Storage Devices], PIDE_MINIPORT_RESOURCES, PIDE_MINIPORT_RESOURCES structure pointer [Storage Devices], _IDE_MINIPORT_RESOURCES, irb/IDE_MINIPORT_RESOURCES, irb/PIDE_MINIPORT_RESOURCES, storage.ide_miniport_resources, structs-ATA_28df7197-d4b0-4279-a4db-e9b1269f6ba7.xml"
f1_keywords:
 - "irb/IDE_MINIPORT_RESOURCES"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- irb.h
api_name:
- IDE_MINIPORT_RESOURCES
product:
- Windows
targetos: Windows
req.typenames: IDE_MINIPORT_RESOURCES, *PIDE_MINIPORT_RESOURCES
---

# _IDE_MINIPORT_RESOURCES structure


## -description


The IDE_MINIPORT_RESOURCES structure is used by the port driver to provide the miniport driver with resources.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field NumberOfAccessRanges

Contains the number of access ranges pointed to by <b>IdeAccessRange</b>. Each is a range either of memory addresses or I/O port addresses.


### -field IdeAccessRange

Pointer to the first address range in a series of contiguous address ranges defined by a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_access_range">IDE_ACCESS_RANGE</a>. The value in the <b>NumberOfAccessRanges</b> member indicates how many address ranges are provided. The port driver populates each <b>IDE_ACCESS_RANGE</b> structure with the address ranges allocated for the controller.


## -remarks



The port driver passes this structure to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_access_range">IDE_ACCESS_RANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_control">IdeHwControl</a>
 

 

