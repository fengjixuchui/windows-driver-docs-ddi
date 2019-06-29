---
UID: NI:ntddscsi.IOCTL_SCSI_MINIPORT
title: IOCTL_SCSI_MINIPORT (ntddscsi.h)
description: Sends a special control function to an HBA-specific miniport driver.
old-location: storage\ioctl_scsi_miniport.htm
tech.root: storage
ms.assetid: 5a9facc7-c83e-4dd4-9fb4-e3385c1b94ea
ms.date: 03/29/2018
ms.keywords: IOCTL_SCSI_MINIPORT, IOCTL_SCSI_MINIPORT control, IOCTL_SCSI_MINIPORT control code [Storage Devices], k307_49b821f3-1a79-44aa-a6a1-92543177181d.xml, ntddscsi/IOCTL_SCSI_MINIPORT, storage.ioctl_scsi_miniport
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddscsi.h
api_name:
- IOCTL_SCSI_MINIPORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SCSI_MINIPORT IOCTL


## -description



Sends a special control function to an HBA-specific miniport driver. Results vary, depending on the particular miniport driver to which this request is forwarded. If the caller specifies a nonzero <b>Length</b>, either the input or output buffer must be at least (<b>sizeof</b>(SRB_IO_CONTROL) + <i>DataBufferLength</i>)).


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> must contain an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> structure. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(SRB_IO_CONTROL), with additional storage for data if the <b>Length</b> field is nonzero.


### -output-buffer

An updated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> structure is returned to the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

The length of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a>
 

 

