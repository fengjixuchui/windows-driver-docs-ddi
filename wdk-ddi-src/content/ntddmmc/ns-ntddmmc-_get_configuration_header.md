---
UID: NS:ntddmmc._GET_CONFIGURATION_HEADER
title: _GET_CONFIGURATION_HEADER (ntddmmc.h)
description: The GET_CONFIGURATION_HEADER structure is used to format the output data retrieved by the IOCTL_CDROM_GET_CONFIGURATION request.
old-location: storage\get_configuration_header.htm
tech.root: storage
ms.assetid: 8de19f1b-faca-4b27-9287-20edc12f2c83
ms.date: 03/29/2018
keywords: ["GET_CONFIGURATION_HEADER structure"]
ms.keywords: "*PGET_CONFIGURATION_HEADER, GET_CONFIGURATION_HEADER, GET_CONFIGURATION_HEADER structure [Storage Devices], PGET_CONFIGURATION_HEADER, PGET_CONFIGURATION_HEADER structure pointer [Storage Devices], _GET_CONFIGURATION_HEADER, ntddmmc/GET_CONFIGURATION_HEADER, ntddmmc/PGET_CONFIGURATION_HEADER, storage.get_configuration_header, structs-CD-ROM_f15044b6-5bbe-4d82-9826-dbe0c96a488c.xml"
req.header: ntddmmc.h
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
req.typenames: GET_CONFIGURATION_HEADER, *PGET_CONFIGURATION_HEADER
f1_keywords:
 - _GET_CONFIGURATION_HEADER
 - ntddmmc/_GET_CONFIGURATION_HEADER
 - PGET_CONFIGURATION_HEADER
 - ntddmmc/PGET_CONFIGURATION_HEADER
 - GET_CONFIGURATION_HEADER
 - ntddmmc/GET_CONFIGURATION_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - GET_CONFIGURATION_HEADER
---

# _GET_CONFIGURATION_HEADER structure


## -description

The GET_CONFIGURATION_HEADER structure is used to format the output data retrieved by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_configuration">IOCTL_CDROM_GET_CONFIGURATION</a> request.

## -struct-fields

### -field DataLength

Indicates the amount of data, in bytes, that is being returned in the buffer area pointed to by the <b>Data</b> member. If the data length is greater than 65,530 bytes, multiple GET CONFIGURATION commands will be required for the Initiator to read all configuration data. The bytes in this array are arranged in big-endian order. <b>DataLength</b>[0] has the most significant byte, and  <b>DataLength</b>[3] has the least significant byte.

### -field Reserved

Reserved.

### -field CurrentProfile

Contains an enumerator value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_profile_type">FEATURE_PROFILE_TYPE</a> that indicates the device's current profile. The bytes in this array are arranged in big-endian order. <b>CurrentProfile</b>[0] has the most significant byte, and  <b>CurrentProfile</b>[3] has the least significant byte.

### -field Data

Contains the feature data, beginning with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_profile_type">FEATURE_PROFILE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_configuration">IOCTL_CDROM_GET_CONFIGURATION</a>

