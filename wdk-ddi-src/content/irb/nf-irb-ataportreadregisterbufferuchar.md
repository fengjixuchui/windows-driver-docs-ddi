---
UID: NF:irb.AtaPortReadRegisterBufferUchar
title: AtaPortReadRegisterBufferUchar function (irb.h)
description: The AtaPortReadRegisterBufferUchar routine transfers a specified number of unsigned bytes from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisterbufferuchar.htm
tech.root: storage
ms.assetid: adc6724b-f3dc-4605-8ee1-198c88bc3fcd
ms.date: 03/29/2018
keywords: ["AtaPortReadRegisterBufferUchar function"]
ms.keywords: AtaPortReadRegisterBufferUchar, AtaPortReadRegisterBufferUchar routine [Storage Devices], atartns_5c57e652-3b37-4673-b5cf-fbcdf38853ad.xml, irb/AtaPortReadRegisterBufferUchar, storage.ataportreadregisterbufferuchar
req.header: irb.h
req.include-header: Ata.h, Irb.h
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
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortReadRegisterBufferUchar
 - irb/AtaPortReadRegisterBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ataport.lib
 - ataport.dll
 - pciidex.lib
 - pciidex.dll
api_name:
 - AtaPortReadRegisterBufferUchar
---

# AtaPortReadRegisterBufferUchar function


## -description

The <b>AtaPortReadRegisterBufferUchar</b> routine transfers a specified number of unsigned bytes from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register 

[in]
Contains the register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses that are obtained by a call to <a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.

### -param Buffer 

[in]
A pointer to the destination buffer.

### -param Count 

[in]
Specifies the number of bytes to read from the HBA.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisterbufferulong">AtaPortReadRegisterBufferUlong</a>



<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisterbufferushort">AtaPortReadRegisterBufferUshort</a>