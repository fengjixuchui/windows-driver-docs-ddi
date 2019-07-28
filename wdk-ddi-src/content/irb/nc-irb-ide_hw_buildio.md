---
UID: NC:irb.IDE_HW_BUILDIO
title: IDE_HW_BUILDIO (irb.h)
description: The IdeHwBuildIo miniport driver routine is called one time for every incoming I/O request.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\idehwbuildio.htm
tech.root: storage
ms.assetid: 057fb78f-6f1c-4b16-b9fa-6fcff299a90d
ms.date: 03/29/2018
ms.keywords: IDE_HW_BUILDIO, IdeHwBuildIo, IdeHwBuildIo routine [Storage Devices], atartns_9111d60c-e0e1-4c5c-aacf-2af56fcf7338.xml, irb/IdeHwBuildIo, storage.idehwbuildio
ms.topic: callback
f1_keywords:
 - "irb/IdeHwBuildIo"
req.header: irb.h
req.include-header: Irb.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- irb.h
api_name:
- IdeHwBuildIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDE_HW_BUILDIO callback function


## -description


The <b><i>IdeHwBuildIo</i></b> miniport driver routine is called one time for every incoming I/O request.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the miniport driver channel extension.


### -param Irb [in]

A pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a> that defines the Integrated Device Electronics (IDE) input/output request block (IRB) to process.


## -returns



<b><i>IdeHwBuildIo</i></b> returns <b>TRUE</b> to acknowledge the receipt of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a> structure. The port driver ignores a return value of <b>FALSE</b>.




## -remarks



Miniport drivers provide an <b><i>AtaHwBuildlo</i></b> routine that performs unsynchronized I/O processing with interrupts enabled. After <b><i>IdeHwBuildIo</i></b> completes all unsynchronized processing of a request, it returns to the port driver, and the port driver passes the request to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nc-irb-ide_hw_startio">IdeHwStartIo</a> routine, which performs the tasks that require synchronization. 

The miniport driver must observe certain restrictions while it executes the <b><i>IdeHwBuildIo</i></b> routine. The miniport driver calls <b><i>IdeHwBuildIo</i></b> without holding any locks. In particular, the miniport driver must not touch any shared data in its channel extension, nor can it call any of the routines exported by the ATA port driver.

If the miniport driver must complete a request while it executes the <b><i>IdeHwBuildIo</i></b> routine, it must assign the appropriate completion status value to the <b>IrbStatus</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a> structure pointed to by the <i>Irb</i> parameter. The miniport driver must not set <b>IrbStatus</b> to a value of IRB_STATUS_PENDING.

The miniport driver can use the <b><i>IdeHwBuildIo</i></b> routine to indicate to the port driver how an IRB should be handled. For example, the miniport driver can request that the port driver map the buffer at <i>DataBuffer </i>by setting the <b>IrbFlags</b> member of the IRB to the appropriate value. The miniport driver should not request that the buffer that is associated with a request be mapped unless the request is some type of data transfer. 

The <b><i>IdeHwBuildIo</i></b> routine resembles Storport's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nc-storport-hw_buildio">HwStorBuildIo</a> routine in functionality. For more information about the <b><i>HwStorBuildIo</i></b> routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/unsynchronized-hwstorbuildio-routine">Unsynchronized HwStorBuildIo Routine</a>.

<b><i>IdeHwBuildIo</i></b> is an optional routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nc-irb-ide_hw_startio">IdeHwStartIo</a>
 

 

