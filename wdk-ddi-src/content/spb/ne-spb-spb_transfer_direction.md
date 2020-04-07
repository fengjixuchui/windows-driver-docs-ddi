---
UID: NE:spb.SPB_TRANSFER_DIRECTION
title: SPB_TRANSFER_DIRECTION (spb.h)
description: The SPB_TRANSFER_DIRECTION enumeration describes the direction (read or write) of a single transfer in an I/O transfer sequence.
old-location: spb\spb_transfer_direction.htm
tech.root: SPB
ms.assetid: 617450AB-6AC8-485A-BD88-377F903EEE15
ms.date: 04/30/2018
keywords: ["SPB_TRANSFER_DIRECTION enumeration"]
ms.keywords: "*PSPB_TRANSFER_DIRECTION, SPB.spb_transfer_direction, SPB_TRANSFER_DIRECTION, SPB_TRANSFER_DIRECTION enumeration [Buses], SpbTransferDirectionFromDevice, SpbTransferDirectionMax, SpbTransferDirectionNone, SpbTransferDirectionToDevice, spb/SPB_TRANSFER_DIRECTION, spb/SpbTransferDirectionFromDevice, spb/SpbTransferDirectionMax, spb/SpbTransferDirectionNone, spb/SpbTransferDirectionToDevice"
f1_keywords:
 - "spb/SPB_TRANSFER_DIRECTION"
req.header: spb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
- Spb.h
api_name:
- SPB_TRANSFER_DIRECTION
product:
- Windows
targetos: Windows
req.typenames: SPB_TRANSFER_DIRECTION, *PSPB_TRANSFER_DIRECTION
---

# SPB_TRANSFER_DIRECTION enumeration


## -description


The <b>SPB_TRANSFER_DIRECTION</b> enumeration describes the direction (read or write) of a single transfer in an <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/i-o-transfer-sequences">I/O transfer sequence</a>.


## -enum-fields




### -field SpbTransferDirectionNone

The data transfer direction is undefined.


### -field SpbTransferDirectionFromDevice

The data transfer direction is from the device to system memory (read from device).


### -field SpbTransferDirectionToDevice

The data transfer direction is from system memory to the device (write to device).


### -field SpbTransferDirectionMax

Reserved for use by the operating system.


## -remarks



The values in this enumeration indicate the directions of the individual transfers in an I/O transfer sequence. The input buffer for an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a> I/O control request is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list">SPB_TRANSFER_LIST</a> structure that specifies a list of transfers for the sequence. Each transfer is described by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry">SPB_TRANSFER_LIST_ENTRY</a> structure that contains the transfer parameters, which include the transfer direction. The transfer direction is <b>SpbTransferDirectionFromDevice</b> for a read operation, and is <b>SpbTransferDirectionToDevice</b> for a write operation.

Your SPB controller driver can call  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbrequestgetparameters">SpbRequestGetParameters</a> method to retrieve a set of SPB-specific parameters from an I/O request. One of these parameters is an <b>SPB_TRANSFER_DIRECTION</b> enumeration value that indicates the transfer direction of the previous I/O request. The SPB controller driver can use this direction value to determine whether the current read or write (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) request requires a change in transfer direction on the bus.

In addition, <b>SpbRequestGetParameters</b> retrieves a position value that indicates the relative position of a read or write  request in the list of transfers for the multiple-request sequence. If a read request or a write request has a position value of <b>SpbRequestSequencePositionSingle</b> or <b>SpbRequestSequencePositionFirst</b>, the direction value for the previous transfer is <b>SpbTransferDirectionNone</b> (that is, there is no previous transfer direction). For a read or write request that has a position value of <b>SpbRequestSequencePositionMiddle</b> or <b>SpbRequestSequencePositionLast</b>, the direction value indicates whether the previous transfer was a read or a write. For an unlock (<a href="https://msdn.microsoft.com/library/windows/hardware/hh450859">IOCTL_SPB_UNLOCK_CONTROLLER</a>) request, which has a position value of <b>SpbRequestSequencePositionLast</b>, the direction value indicates whether the last transfer in the sequence was a read or a write.

A lock (<a href="https://msdn.microsoft.com/library/windows/hardware/hh450858">IOCTL_SPB_LOCK_CONTROLLER</a>) request has no previous direction. Similarly, an I/O control request that is passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a> callback function has no previous direction. For either of these requests, the previous direction value retrieved by <b>SpbRequestGetParameters</b> is <b>SpbTransferDirectionNone</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_other">EvtSpbControllerIoOther</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450858">IOCTL_SPB_LOCK_CONTROLLER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450859">IOCTL_SPB_UNLOCK_CONTROLLER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list">SPB_TRANSFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry">SPB_TRANSFER_LIST_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbrequestgetparameters">SpbRequestGetParameters</a>
 

 

