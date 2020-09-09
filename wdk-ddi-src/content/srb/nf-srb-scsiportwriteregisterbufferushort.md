---
UID: NF:srb.ScsiPortWriteRegisterBufferUshort
title: ScsiPortWriteRegisterBufferUshort function (srb.h)
description: The ScsiPortWriteRegisterBufferUshort routine transfers a given number of USHORT values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteregisterbufferushort.htm
tech.root: storage
ms.assetid: 663c0543-7059-4fb7-be3d-57edbba6bf83
ms.date: 03/29/2018
keywords: ["ScsiPortWriteRegisterBufferUshort function"]
ms.keywords: ScsiPortWriteRegisterBufferUshort, ScsiPortWriteRegisterBufferUshort routine [Storage Devices], scsiprt_300e2355-e8b2-4341-912d-a24954568824.xml, srb/ScsiPortWriteRegisterBufferUshort, storage.scsiportwriteregisterbufferushort
req.header: srb.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiPortWriteRegisterBufferUshort
 - srb/ScsiPortWriteRegisterBufferUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortWriteRegisterBufferUshort
---

# ScsiPortWriteRegisterBufferUshort function


## -description

The <b>ScsiPortWriteRegisterBufferUshort</b> routine transfers a given number of USHORT values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register 

[in]
Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

### -param Buffer 

[in]
Pointer to a buffer containing the data to be written.

### -param Count 

[in]
Specifies the number of USHORT values to be transferred to the HBA.

## -returns

None

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>

