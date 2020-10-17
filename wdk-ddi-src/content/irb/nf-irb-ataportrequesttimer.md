---
UID: NF:irb.AtaPortRequestTimer
title: AtaPortRequestTimer function (irb.h)
description: The AtaPortRequestTimer routine requests a timer callback.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequesttimer.htm
tech.root: storage
ms.assetid: b057ae2e-53ae-4da9-8668-1ebca3c80998
ms.date: 03/29/2018
keywords: ["AtaPortRequestTimer function"]
ms.keywords: AtaPortRequestTimer, AtaPortRequestTimer routine [Storage Devices], atartns_604a8d41-c918-4121-97ef-10d3a7fbf3b4.xml, irb/AtaPortRequestTimer, storage.ataportrequesttimer
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortRequestTimer
 - irb/AtaPortRequestTimer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - irb.h
api_name:
 - AtaPortRequestTimer
---

# AtaPortRequestTimer function


## -description

The <b>AtaPortRequestTimer</b> routine requests a timer callback.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param ChannelExtension 

[in]
A pointer to the channel extension.

### -param CallBackRoutine

<p>A pointer to the timer routine. </p>

### -param TimerValue 

[in]
Time interval in units of microseconds.

## -returns

None

## -remarks

The <b>AtaPortRequestTimer</b> routine informs the ATA port driver that it must call the timer routine that is pointed to by <i>TimerRoutine</i> in the number of microseconds indicated by <i>TimerValue</i>. 

The ATA port driver passes a pointer to the channel extension to the timer routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportstallexecution">AtaPortStallExecution</a>