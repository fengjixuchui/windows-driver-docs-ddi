---
UID: NI:ntddscsi.IOCTL_SCSI_PASS_THROUGH_DIRECT
title: IOCTL_SCSI_PASS_THROUGH_DIRECT (ntddscsi.h)
description: Allows an application to send almost any SCSI command to a target device, with the following restrictions:Multitarget commands, such as COPY, are not allowed.Bidirectional data transfer operations are not supported.If a class driver for the target type of device exists, the request must be sent to that class driver. Thus, an application can send this request directly to the system port driver for a target logical unit only if there is no class driver for the type of device connected to that LU.This request must be made if the input CDB might require the underlying miniport driver to access memory directly.The calling application creates the SCSI command descriptor block, which can include a request for request-sense data if a CHECK CONDITION occurs. If the CDB requests a data transfer operation, the caller must set up an adapter device aligned buffer from which or into which the miniport driver can transfer data directly. This request is typically used for transferring larger amounts of data (>16K).Applications can send this request by means of an IRP_MJ_DEVICE_CONTROL request. Storage class drivers set the minor IRP number to IRP_MN_SCSI_CLASS to indicate that the request has been processed by a storage class driver.
old-location: storage\ioctl_scsi_pass_through_direct.htm
tech.root: storage
ms.assetid: 7706e861-b8d6-41c3-9b64-371de4f58d48
ms.date: 03/29/2018
ms.keywords: IOCTL_SCSI_PASS_THROUGH_DIRECT, IOCTL_SCSI_PASS_THROUGH_DIRECT control, IOCTL_SCSI_PASS_THROUGH_DIRECT control code [Storage Devices], k307_4d0f0379-41c5-45c5-98b4-1a222349b4e1.xml, ntddscsi/IOCTL_SCSI_PASS_THROUGH_DIRECT, storage.ioctl_scsi_pass_through_direct
ms.topic: ioctl
f1_keywords:
 - "ntddscsi/IOCTL_SCSI_PASS_THROUGH_DIRECT"
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
- IOCTL_SCSI_PASS_THROUGH_DIRECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SCSI_PASS_THROUGH_DIRECT IOCTL


## -description



Allows an application to send almost any SCSI command to a target device, with the following restrictions:

<ul>
<li>
Multitarget commands, such as COPY, are not allowed.

</li>
<li>
Bidirectional data transfer operations are not supported.

</li>
<li>
If a class driver for the target type of device exists, the request must be sent to that class driver. Thus, an application can send this request directly to the system port driver for a target logical unit only if there is no class driver for the type of device connected to that LU.

</li>
<li>
This request <i>must</i> be made if the input CDB might require the underlying miniport driver to access memory directly.

</li>
</ul>
The calling application creates the SCSI command descriptor block, which can include a request for request-sense data if a CHECK CONDITION occurs. If the CDB requests a data transfer operation, the caller must set up an adapter device aligned buffer from which or into which the miniport driver can transfer data directly. This request is typically used for transferring larger amounts of data (>16K).

Applications can send this request by means of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a> request. 

Storage class drivers set the minor IRP number to IRP_MN_SCSI_CLASS to indicate that the request has been processed by a storage class driver. 


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -ioctlparameters




### -input-buffer

This structure includes a SCSI CDB, which must be initialized by the caller except for the path, target ID, and LUN, which are filled in by the port driver. For a data-out command, the data to be transferred must be in an adapter device aligned buffer. The <b>DataBuffer</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct">SCSI_PASS_THROUGH_DIRECT</a> is a pointer to this adapter device aligned buffer. The caller must allocate additional storage, following the <b>SCSI_PASS_THROUGH_DIRECT</b> structure, if the caller asks for request-sense data.


### -input-buffer-length

<i>
       Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer at <i>Irp->AssociatedIrp.SystemBuffer</i>, which must be at least (<i>sense data size</i> + <b>sizeof</b> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct">SCSI_PASS_THROUGH_DIRECT</a>)). The size of the <b>SCSI_PASS_THROUGH_DIRECT</b> structure is fixed.


### -output-buffer

The port driver returns any request-sense data and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct">SCSI_PASS_THROUGH_DIRECT</a> structure to the buffer at <i>Irp->AssociatedIrp.SystemBuffer</i>. 


### -output-buffer-length

<b>SenseInfoLength</b>
 and 
<b>DataTransferLength</b>
 are updated to indicate the amount of data transferred. The port driver returns any data transferred from the device to the supplied cache-aligned buffer at 
<b>DataBuffer</b>
.

### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned in the output buffer at <i>Irp->AssociatedIrp.SystemBuffer</i>. The Status field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_BUFFER_TOO_SMALL</b> or <b>STATUS_INVALID_PARAMETER</b> if the input <b>Length</b> value in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct">SCSI_PASS_THROUGH_DIRECT</a> is improperly set or the buffer specifed in  <b>DataBuffer</b> is not properly device aligned.



## -remarks



For data transfer operations, a buffer with alignment  matching the adapter device  is required. Applications can retrieve the device alignment mask by issuing an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> control code request with a query type of <b>PropertyStandardQuery</b> and property id of <b>StorageAdapterProperty</b>. The alignment mask is found in the <b>AlignmentMask</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_adapter_descriptor">STORAGE_ADAPTER_DESCRIPTOR</a> structure that is returned. Drivers may also use the value in the <b>AlignmentMask</b> member of the adapter's <i>DeviceObject</i>.

In the following  example function, a   buffer is prepared as a device  aligned data transfer buffer.

```cpp
PVOID AllocateAlignedBuffer(ULONG size, ULONG AlignmentMask, PVOID *pUnAlignedBuffer)
{
    PVOID AlignedBuffer;
    ULONG_PTR FullWordMask = (ULONG_PTR)AlignmentMask;

    if (AlignmentMask == 0)
    {
        AlignedBuffer = malloc(size);
        // return the original buffer to free later
        *pUnAlignedBuffer = AlignedBuffer;
    }
    else
    {
        // expand the size for the alignment window
        size += AlignmentMask;
        AlignedBuffer = malloc(size);
        // return the original buffer to free later
        *pUnAlignedBuffer = AlignedBuffer;
        // adjust buffer pointer for the desired alignment
        AlignedBuffer = (PVOID)(((ULONG_PTR)AlignedBuffer + FullWordMask) & ~FullWordMask);
    }

    return AlignedBuffer;
}
```


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through">IOCTL_SCSI_PASS_THROUGH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct">SCSI_PASS_THROUGH_DIRECT</a>
 

 

