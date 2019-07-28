---
UID: NF:storport.ScsiPortWritePortUchar
title: ScsiPortWritePortUchar macro (storport.h)
description: The ScsiPortWritePortUchar routine transfers an unsigned byte to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportuchar.htm
tech.root: storage
ms.assetid: aba28a55-d7bc-4f75-ac87-4148cb1b4cfb
ms.date: 03/29/2018
ms.keywords: ScsiPortWritePortUchar, ScsiPortWritePortUchar routine [Storage Devices], scsiprt_4dfda130-8e22-44b3-a57a-0656cd2a70f2.xml, srb/ScsiPortWritePortUchar, storage.scsiportwriteportuchar
ms.topic: macro
f1_keywords:
 - "storport/ScsiPortWritePortUchar"
req.header: storport.h
req.include-header: Miniport.h, Scsi.h, Storport.h
req.target-type: Desktop
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Scsiport.lib
- Scsiport.dll
api_name:
- ScsiPortWritePortUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWritePortUchar macro


## -description


The <b>ScsiPortWritePortUchar</b> routine transfers an unsigned byte to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Value [in]

Specifies the value to be written to the HBA's I/O port.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

