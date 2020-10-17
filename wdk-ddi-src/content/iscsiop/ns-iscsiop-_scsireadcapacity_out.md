---
UID: NS:iscsiop._ScsiReadCapacity_OUT
title: _ScsiReadCapacity_OUT (iscsiop.h)
description: The ScsiReadCapacity_OUT structure holds the output data for the ScsiReadCapacity method.
old-location: storage\scsireadcapacity_out.htm
tech.root: storage
ms.assetid: 3330379f-e484-4fd7-b914-fc969398b56b
ms.date: 03/29/2018
keywords: ["ScsiReadCapacity_OUT structure"]
ms.keywords: "*PScsiReadCapacity_OUT, PScsiReadCapacity_OUT, PScsiReadCapacity_OUT structure pointer [Storage Devices], ScsiReadCapacity_OUT, ScsiReadCapacity_OUT structure [Storage Devices], _ScsiReadCapacity_OUT, iscsiop/PScsiReadCapacity_OUT, iscsiop/ScsiReadCapacity_OUT, storage.scsireadcapacity_out, structs-iSCSI_48750b99-26df-4890-b906-fa487efc3797.xml"
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
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
req.typenames: ScsiReadCapacity_OUT, *PScsiReadCapacity_OUT
f1_keywords:
 - _ScsiReadCapacity_OUT
 - iscsiop/_ScsiReadCapacity_OUT
 - PScsiReadCapacity_OUT
 - iscsiop/PScsiReadCapacity_OUT
 - ScsiReadCapacity_OUT
 - iscsiop/ScsiReadCapacity_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - ScsiReadCapacity_OUT
---

# _ScsiReadCapacity_OUT structure (iscsiop.h)


## -description

The ScsiReadCapacity_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/scsireadcapacity6">ScsiReadCapacity</a> method.

## -struct-fields

### -field Status

The status of the <b>ScsiReadCapacity</b> method. This member will contain 0 if the READ CAPACITY operation succeeds and ISDSC_SCSI_REQUEST_FAILED if the operation fails. If the READ CAPACITY operation fails, <b>ScsiStatus</b> will contain the SCSI status of the SCSI command. SCSI status qualifiers are documented in the <i>SCSI Primary Commands</i> specification. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

### -field ResponseBufferSize

The size, in bytes, of the buffer at <b>ResponseBuffer</b><i>. </i>

### -field ScsiStatus

The status of the SCSI READ CAPACITY command.

### -field SenseBuffer

A buffer that holds the SCSI sense data that the SCSI READ CAPACITY command received.

### -field ResponseBuffer

A buffer that holds the response data that the SCSI READ CAPACITY command received.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/scsireadcapacity6">ScsiReadCapacity</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_scsireadcapacity_in">ScsiReadCapacity_IN</a>