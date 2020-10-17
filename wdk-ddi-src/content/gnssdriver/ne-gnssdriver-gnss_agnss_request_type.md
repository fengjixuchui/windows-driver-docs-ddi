---
UID: NE:gnssdriver.__unnamed_enum_5
title: GNSS_AGNSS_REQUEST_TYPE (gnssdriver.h)
description: This enumeration indicates the type of AGNSS injection request represented by the GNSS_AGNSS_REQUEST_PARAM structure.
old-location: gnss\gnss_agnss_request_type.htm
tech.root: gnss
ms.assetid: 31293354-D68B-475F-91BD-0504129207A5
ms.date: 02/15/2018
keywords: ["GNSS_AGNSS_REQUEST_TYPE enumeration"]
ms.keywords: GNSS_AGNSS_BlobInjection, GNSS_AGNSS_PositionInjection, GNSS_AGNSS_REQUEST_TYPE, GNSS_AGNSS_REQUEST_TYPE enumeration [Sensor Devices], GNSS_AGNSS_TimeInjection, gnss.gnss_agnss_request_type, gnssdriver/GNSS_AGNSS_BlobInjection, gnssdriver/GNSS_AGNSS_PositionInjection, gnssdriver/GNSS_AGNSS_REQUEST_TYPE, gnssdriver/GNSS_AGNSS_TimeInjection
req.header: gnssdriver.h
req.include-header: 
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
req.typenames: GNSS_AGNSS_REQUEST_TYPE
f1_keywords:
 - GNSS_AGNSS_REQUEST_TYPE
 - gnssdriver/GNSS_AGNSS_REQUEST_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - GNSS_AGNSS_REQUEST_TYPE
---

# GNSS_AGNSS_REQUEST_TYPE enumeration


## -description

This enumeration indicates the type of AGNSS injection request represented by the <a href="/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_agnss_request_param">GNSS_AGNSS_REQUEST_PARAM</a> structure.

## -enum-fields

### -field GNSS_AGNSS_TimeInjection

Indicates the injection request is for time injection.

### -field GNSS_AGNSS_PositionInjection

Indicates the injection request is for position injection.

### -field GNSS_AGNSS_BlobInjection

Indicates the injection request is for blob injection.