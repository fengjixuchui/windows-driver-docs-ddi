---
UID: NS:ntddmmc._FEATURE_DATA_RESTRICTED_OVERWRITE
title: _FEATURE_DATA_RESTRICTED_OVERWRITE (ntddmmc.h)
description: The FEATURE_DATA_RESTRICTED_OVERWRITE structure holds information about the Restricted Overwrite feature.
old-location: storage\feature_data_restricted_overwrite.htm
tech.root: storage
ms.assetid: d9f3e892-1ed5-4030-a656-7d2d294b1c82
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_RESTRICTED_OVERWRITE structure"]
ms.keywords: "*PFEATURE_DATA_RESTRICTED_OVERWRITE, FEATURE_DATA_RESTRICTED_OVERWRITE, FEATURE_DATA_RESTRICTED_OVERWRITE structure [Storage Devices], PFEATURE_DATA_RESTRICTED_OVERWRITE, PFEATURE_DATA_RESTRICTED_OVERWRITE structure pointer [Storage Devices], _FEATURE_DATA_RESTRICTED_OVERWRITE, ntddmmc/FEATURE_DATA_RESTRICTED_OVERWRITE, ntddmmc/PFEATURE_DATA_RESTRICTED_OVERWRITE, storage.feature_data_restricted_overwrite, structs-CD-ROM_d2d9725b-16c9-4361-a2fc-90bdc2d7905c.xml"
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
req.typenames: FEATURE_DATA_RESTRICTED_OVERWRITE, *PFEATURE_DATA_RESTRICTED_OVERWRITE
f1_keywords:
 - _FEATURE_DATA_RESTRICTED_OVERWRITE
 - ntddmmc/_FEATURE_DATA_RESTRICTED_OVERWRITE
 - PFEATURE_DATA_RESTRICTED_OVERWRITE
 - ntddmmc/PFEATURE_DATA_RESTRICTED_OVERWRITE
 - FEATURE_DATA_RESTRICTED_OVERWRITE
 - ntddmmc/FEATURE_DATA_RESTRICTED_OVERWRITE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - FEATURE_DATA_RESTRICTED_OVERWRITE
---

# _FEATURE_DATA_RESTRICTED_OVERWRITE structure


## -description

The FEATURE_DATA_RESTRICTED_OVERWRITE structure holds information about the Restricted Overwrite feature.

## -struct-fields

### -field Header

Contains a <a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

## -remarks

This structure holds data for the feature named "Restricted Overwrite" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can only overwrite a limited set of logical blocks at any given time. 

When queried, devices supporting this feature must return the information indicated in <a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>. No other feature-specific information is required.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>