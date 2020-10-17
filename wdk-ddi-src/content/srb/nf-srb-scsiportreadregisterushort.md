---
UID: NF:srb.ScsiPortReadRegisterUshort
title: ScsiPortReadRegisterUshort function (srb.h)
description: The ScsiPortReadRegisterUshort routine reads a USHORT value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisterushort.htm
tech.root: storage
ms.assetid: 192a525e-6a42-4bd0-9c50-d13741469a48
ms.date: 03/29/2018
keywords: ["ScsiPortReadRegisterUshort function"]
ms.keywords: ScsiPortReadRegisterUshort, ScsiPortReadRegisterUshort routine [Storage Devices], scsiprt_342c6cc3-090e-4bea-be54-1a52f50d8276.xml, srb/ScsiPortReadRegisterUshort, storage.scsiportreadregisterushort
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
 - ScsiPortReadRegisterUshort
 - srb/ScsiPortReadRegisterUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortReadRegisterUshort
---

# ScsiPortReadRegisterUshort function


## -description

The <b>ScsiPortReadRegisterUshort</b> routine reads a USHORT value from the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register 

[in]
Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

## -returns

<b>ScsiPortReadRegisterUshort</b> returns a USHORT value from the HBA's register.

## -remarks

<b>ScsiPortReadRegisterUshort</b> ensures that the data is transferred correctly.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>