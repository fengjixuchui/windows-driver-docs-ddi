---
UID: NS:scsi._WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
title: _WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR (scsi.h)
description: The WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure is the third party copy descriptor for Windows systems.
old-location: storage\windows_block_device_token_limits_descriptor.htm
tech.root: storage
ms.assetid: A4DB93FE-96ED-4E6D-B912-31C53AD000FF
ms.date: 03/29/2018
keywords: ["WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure"]
ms.keywords: "*PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure pointer [Storage Devices], WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure [Storage Devices], _WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, scsi/PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, scsi/WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, storage.windows_block_device_token_limits_descriptor"
req.header: scsi.h
req.include-header: Scsi.h, Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.typenames: WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, *PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
f1_keywords:
 - _WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
 - scsi/_WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
 - PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
 - scsi/PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
 - WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
 - scsi/WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
---

# _WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure (scsi.h)


## -description

The <b>WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR</b> structure is the third party copy descriptor for Windows systems. This structure serves as the descriptor for the vital product data (VPD) third party copy page.

## -struct-fields

### -field DescriptorType

The descriptor type identifying this structure. The descriptor type is defined in <i>storport.h</i> as <b>BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR_TYPE_WINDOWS</b>.

### -field DescriptorLength

The length of this structure starting with the <b>VendorSpecific</b> member.

### -field VendorSpecific

Vendor specific bytes included in the descriptor. Windows applications must treat this member as reserved and ignore the reported value.

### -field MaximumRangeDescriptors

The maximum number of range descriptors that may be included along with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-populate_token_header">POPULATE_TOKEN_HEADER</a> or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-write_using_token_header">WRITE_USING_TOKEN_HEADER</a> structures.

### -field MaximumInactivityTimer

The maximum available to specify as the timeout value in the <b>InactivityTimeout</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-populate_token_header">POPULATE_TOKEN_HEADER</a> structure.

### -field DefaultInactivityTimer

The default value that is used by the copy provider when the <b>InactivityTimeout</b> of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-populate_token_header">POPULATE_TOKEN_HEADER</a> structure is set to 0.

### -field MaximumTokenTransferSize

The maximum number of logical blocks that can be specified as a total of the block range descriptors in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-populate_token_header">POPULATE_TOKEN_HEADER</a> or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-write_using_token_header">WRITE_USING_TOKEN_HEADER</a> structures.

### -field OptimalTransferCount

The optimal number of logical blocks, as a maximum, to specify as a total of the block range descriptors in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-populate_token_header">POPULATE_TOKEN_HEADER</a> or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-write_using_token_header">WRITE_USING_TOKEN_HEADER</a> structures. Offload data transfer performance may degrade if the transfer count is larger than this value.

## -remarks

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-populate_token_header">POPULATE_TOKEN_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-_vpd_third_party_copy_page">VPD_THIRD_PARTY_COPY_PAGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-write_using_token_header">WRITE_USING_TOKEN_HEADER</a>

