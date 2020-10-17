---
UID: NF:srb.ScsiPortWriteRegisterBufferUchar
title: ScsiPortWriteRegisterBufferUchar function (srb.h)
description: The ScsiPortWriteRegisterBufferUchar routine transfers a given number of unsigned bytes from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteregisterbufferuchar.htm
tech.root: storage
ms.assetid: 6c04c3ae-bca4-4235-a76a-2cfd1fbe4db7
ms.date: 03/29/2018
keywords: ["ScsiPortWriteRegisterBufferUchar function"]
ms.keywords: ScsiPortWriteRegisterBufferUchar, ScsiPortWriteRegisterBufferUchar routine [Storage Devices], scsiprt_260290c1-818a-49dd-9705-ea79984fa0af.xml, srb/ScsiPortWriteRegisterBufferUchar, storage.scsiportwriteregisterbufferuchar
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
 - ScsiPortWriteRegisterBufferUchar
 - srb/ScsiPortWriteRegisterBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortWriteRegisterBufferUchar
---

# ScsiPortWriteRegisterBufferUchar function


## -description

The <b>ScsiPortWriteRegisterBufferUchar</b> routine transfers a given number of unsigned bytes from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register 

[in]
Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

### -param Buffer 

[in]
Pointer to a buffer containing the data to be written.

### -param Count 

[in]
Specifies the number of bytes to be transferred to the HBA.

## -returns

None

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>