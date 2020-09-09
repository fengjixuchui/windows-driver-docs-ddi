---
UID: NS:ntddcdrm._CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
title: _CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR (ntddcdrm.h)
description: The CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure indicates that the result data from the IOCTL_CDROM_GET_PERFORMANCE I/O control request is for exception conditions.
old-location: storage\cdrom_exception_performance_descriptor.htm
tech.root: storage
ms.assetid: 054C8E89-D0A6-46D1-A5AA-2BE73931BB7A
ms.date: 03/29/2018
keywords: ["CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure"]
ms.keywords: "*PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure [Storage Devices], PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure pointer [Storage Devices], _CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, ntddcdrm/CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, ntddcdrm/PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, storage.cdrom_exception_performance_descriptor"
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
req.typenames: CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, *PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
f1_keywords:
 - _CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
 - ntddcdrm/_CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
 - PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
 - ntddcdrm/PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
 - CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
 - ntddcdrm/CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdrm.h
api_name:
 - CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
---

# _CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure


## -description

The <b>CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</b> structure indicates that the result data from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request is for exception conditions. Exception conditions are exception locations that could cause seek delays to occur. The <b>CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</b> is returned by the <b>IOCTL_CDROM_GET_PERFORMANCE</b> I/O control request when the request type is <b>CdromPerformanceRequest</b> and the <b>Except</b> field of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_performance_header">CDROM_PERFORMANCE_HEADER</a> is true (1).   Separate descriptors are returned for read and write performance requests. The fields in  <b>CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</b> correspond to the similarly named fields in the Performance Descriptor - Exceptions  table described in the MultiMedia Command Set - 6 (MMC-6)
specification.

## -struct-fields

### -field Lba

### -field Time

The Time field indicates the expected additional seek delay between LBA and the preceding LBA (LBA - 1) from nominal, in units of tenths
of milliseconds (100 microseconds). The cause of the seek delay might be linear replacement, zone boundaries, or other media
dependent features. 


#### - LBA

The LBA field  indicates that there is a seek delay between the logical block address (LBA) and the preceding LBA (LBA -1).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_performance_header">CDROM_PERFORMANCE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a>

