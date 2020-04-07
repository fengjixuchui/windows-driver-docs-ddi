---
UID: NF:irb.AtaPortReadRegisterBufferUlong
title: AtaPortReadRegisterBufferUlong function (irb.h)
description: The AtaPortReadRegisterBufferUlong routine transfers a specified number of ULONG values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisterbufferulong.htm
tech.root: storage
ms.assetid: 50baeaa1-5671-4f6d-83cd-f03cca18b18b
ms.date: 03/29/2018
keywords: ["AtaPortReadRegisterBufferUlong function"]
ms.keywords: AtaPortReadRegisterBufferUlong, AtaPortReadRegisterBufferUlong routine [Storage Devices], atartns_2e57cb04-ad9c-47fd-b4a5-9f9aa433c8ad.xml, irb/AtaPortReadRegisterBufferUlong, storage.ataportreadregisterbufferulong
f1_keywords:
 - "irb/AtaPortReadRegisterBufferUlong"
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
- AtaPortReadRegisterBufferUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortReadRegisterBufferUlong function


## -description


The <b>AtaPortReadRegisterBufferUlong</b> routine transfers a specified number of ULONG values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

Contains the register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the destination buffer.


### -param Count [in]

Specifies the number of ULONG values to read from the HBA.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetdevicebase">AtaPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisterbufferuchar">AtaPortReadRegisterBufferUchar</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportreadregisterbufferushort">AtaPortReadRegisterBufferUshort</a>
 

 

