---
UID: NS:ntddcdrm._CDROM_TOC_ATIP_DATA_BLOCK
title: _CDROM_TOC_ATIP_DATA_BLOCK (ntddcdrm.h)
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in a header structure of type CDROM_TOC_ATIP_DATA followed by a series of ATIP data block descriptors defined by CDROM_TOC_ATIP_DATA_BLOCK.
old-location: storage\cdrom_toc_atip_data_block.htm
tech.root: storage
ms.assetid: b98d0ba9-9c32-44ed-b6c3-db6de26a1663
ms.date: 01/08/2020
keywords: ["CDROM_TOC_ATIP_DATA_BLOCK structure"]
ms.keywords: "*PCDROM_TOC_ATIP_DATA_BLOCK, CDROM_TOC_ATIP_DATA_BLOCK, CDROM_TOC_ATIP_DATA_BLOCK structure [Storage Devices], PCDROM_TOC_ATIP_DATA_BLOCK, PCDROM_TOC_ATIP_DATA_BLOCK structure pointer [Storage Devices], _CDROM_TOC_ATIP_DATA_BLOCK, ntddcdrm/CDROM_TOC_ATIP_DATA_BLOCK, ntddcdrm/PCDROM_TOC_ATIP_DATA_BLOCK, storage.cdrom_toc_atip_data_block, structs-CD-ROM_8c2f3446-c864-450a-a873-9e1d29b1e052.xml"
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
req.typenames: CDROM_TOC_ATIP_DATA_BLOCK, *PCDROM_TOC_ATIP_DATA_BLOCK
f1_keywords:
 - _CDROM_TOC_ATIP_DATA_BLOCK
 - ntddcdrm/_CDROM_TOC_ATIP_DATA_BLOCK
 - PCDROM_TOC_ATIP_DATA_BLOCK
 - ntddcdrm/PCDROM_TOC_ATIP_DATA_BLOCK
 - CDROM_TOC_ATIP_DATA_BLOCK
 - ntddcdrm/CDROM_TOC_ATIP_DATA_BLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdrm.h
api_name:
 - CDROM_TOC_ATIP_DATA_BLOCK
---

# _CDROM_TOC_ATIP_DATA_BLOCK structure


## -description

Device control IRPs with a control code of [IOCTL_CDROM_READ_TOC_EX](./ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md) and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in a header structure of type [CDROM_TOC_ATIP_DATA](./ns-ntddcdrm-_cdrom_toc_atip_data.md) followed by a series of ATIP data block descriptors defined by **CDROM_TOC_ATIP_DATA_BLOCK**.

## -struct-fields

### -field CdrwReferenceSpeed

Indicates the recommended write speed for the media. Values 0x00 to 0x01 are reserved. A value of 0x02 indicates a CD-ROM speed of 4X. A value of 0x03 indicates a CD-ROM speed of 8X. Values 0x04 to 0x07 are reserved.

### -field Reserved3

Reserved.

### -field WritePower

Indicates media's recommended initial laser power setting. The high order bit must be set to 1. The setting of the other bits varies between CD-R and CD-RW media. For an explanation of the values these bits can have, see the *SCSI Multimedia Commands - 3* (MMC-3) specification.

### -field True1

Must be set to 1.

### -field Reserved4

Reserved.

### -field UnrestrictedUse

Indicates, when set to 1, that the mounted disc is defined for unrestricted use. When set to zero, indicates that the mounted disc is defined for restricted use.

### -field Reserved5

Reserved.

### -field A3Valid

Indicates that bytes 16-18 (bytes 12-14 of the ATIP descriptor) are valid when set to 1. When set to zero, indicates that bytes 16-18 are invalid.

### -field A2Valid

Indicates that A2 values field is valid when set to 1. When set to zero, indicates that the A2 values field is invalid.

### -field A1Valid

Indicates that A3 values field is valid when set to 1. When set to zero, indicates that the A3 values field is invalid.

### -field DiscSubType

Must be set to zero.

### -field IsCdrw

Indicates the media is rewritable (CD-RW) when set to 1. When set to zero, indicates the media is write-once (CD-R).

### -field True2

Must be set to 1.

### -field Reserved7

Reserved.

### -field LeadInMsf

Indicates the ATIP start time of lead-in, in terms of minutes, seconds, and frames. Valid values of the first byte are from 0x50 to 0x63. For an explanation of the values that the second and third bytes can have, see the *SCSI Multimedia Commands - 3* (MMC-3) specification.

### -field Reserved8

Reserved.

### -field LeadOutMsf

Indicates the ATIP last possible start time of lead-out in terms of minutes, seconds, and frames. Valid values of the first byte are from 0x0 to 0x04F. For an explanation of the values that the second and third bytes can have, see the *SCSI Multimedia Commands - 3* (MMC-3) specification.

### -field Reserved9

Reserved.

### -field A1Values

See specification *T10/1363-D*, by National Committee for Information Technology Standards (NCITS) For information about the permissible values for this member.

### -field Reserved10

Reserved.

### -field A2Values

Reserved.

### -field Reserved11

Reserved.

### -field A3Values

Reserved.

### -field Reserved12

Reserved.

## -see-also

[CDROM_READ_TOC_EX](./ns-ntddcdrm-_cdrom_read_toc_ex.md)

[CDROM_TOC_ATIP_DATA](./ns-ntddcdrm-_cdrom_toc_atip_data.md)

[IOCTL_CDROM_READ_TOC_EX](./ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md)