---
UID: NS:ntddstor._STORAGE_OFFLOAD_WRITE_OUTPUT
title: _STORAGE_OFFLOAD_WRITE_OUTPUT (ntddstor.h)
description: The STORAGE_OFFLOAD_WRITE_OUTPUT structure is the output of an IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code request when the Action member of DEVICE_MANAGE_DATA_SET_ATTRIBUTES is set to DeviceDsmAction_OffloadWrite.
old-location: storage\storage_offload_write_output.htm
tech.root: storage
ms.assetid: 95EF1722-5171-4A09-8676-7910E53E3868
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_OFFLOAD_WRITE_OUTPUT, PSTORAGE_OFFLOAD_WRITE_OUTPUT, PSTORAGE_OFFLOAD_WRITE_OUTPUT structure pointer [Storage Devices], STORAGE_OFFLOAD_TOKEN_INVALID, STORAGE_OFFLOAD_WRITE_OUTPUT, STORAGE_OFFLOAD_WRITE_OUTPUT structure [Storage Devices], STORAGE_OFFLOAD_WRITE_RANGE_TRUNCATED, _STORAGE_OFFLOAD_WRITE_OUTPUT, ntddstor/PSTORAGE_OFFLOAD_WRITE_OUTPUT, ntddstor/STORAGE_OFFLOAD_WRITE_OUTPUT, storage.storage_offload_write_output"
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
- ntddstor.h
api_name:
- STORAGE_OFFLOAD_WRITE_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: STORAGE_OFFLOAD_WRITE_OUTPUT, *PSTORAGE_OFFLOAD_WRITE_OUTPUT
---

# _STORAGE_OFFLOAD_WRITE_OUTPUT structure


## -description


The <b>STORAGE_OFFLOAD_WRITE_OUTPUT</b> structure is the output of  an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> control code request when the <b>Action</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> is set to <b>DeviceDsmAction_OffloadWrite</b>.

On input, a token value in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_dsm_offload_write_parameters">DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</a> uniquely identifies the data set ranges requested for writing in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure. The <b>STORAGE_OFFLOAD_WRITE_OUTPUT</b> structure contains the results of the write operation.


## -struct-fields




### -field OffloadWriteFlags

Flags indicating the result of the offload write operation. This is set to one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STORAGE_OFFLOAD_WRITE_RANGE_TRUNCATED"></a><a id="storage_offload_write_range_truncated"></a><dl>
<dt><b>STORAGE_OFFLOAD_WRITE_RANGE_TRUNCATED</b></dt>
</dl>
</td>
<td width="60%">
The offload write was performed but the range written was truncated.

</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_OFFLOAD_TOKEN_INVALID_________"></a><a id="storage_offload_token_invalid_________"></a><dl>
<dt><b>STORAGE_OFFLOAD_TOKEN_INVALID         </b></dt>
</dl>
</td>
<td width="60%">
The token provided for the offload write operation was invalid.

</td>
</tr>
</table>
 


### -field Reserved

Reserved.


### -field LengthCopied

Bytes copied for the write request in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_dsm_offload_write_parameters">DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</a>.


## -remarks



The <b>STORAGE_OFFLOAD_WRITE_OUTPUT</b> structure is returned at the beginning of the system buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_dsm_offload_write_parameters">DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>
 

 

