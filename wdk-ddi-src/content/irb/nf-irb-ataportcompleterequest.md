---
UID: NF:irb.AtaPortCompleteRequest
title: AtaPortCompleteRequest function (irb.h)
description: The AtaPortCompleteRequest routine completes the indicated IRB.
old-location: storage\ataportcompleterequest.htm
tech.root: storage
ms.assetid: 2dddd012-9a13-49e4-9392-300938e78609
ms.date: 03/29/2018
keywords: ["AtaPortCompleteRequest function"]
ms.keywords: AtaPortCompleteRequest, AtaPortCompleteRequest routine [Storage Devices], atartns_6ed3a9ca-b9b8-4d2f-a2f2-5a57db2071f8.xml, irb/AtaPortCompleteRequest, storage.ataportcompleterequest
f1_keywords:
 - "irb/AtaPortCompleteRequest"
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
- AtaPortCompleteRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortCompleteRequest function


## -description


The <b>AtaPortCompleteRequest</b> routine completes the indicated IRB. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension.


### -param Irb [in]

A pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a> that defines the IDE request block (IRB) to be completed.


## -remarks



The miniport driver uses this routine to indicate to the port driver that the IRB has completed. The miniport driver must not touch the IRB after this call. It is an error to complete an IRB with status IRB_STATUS_PENDING.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a>
 

 

