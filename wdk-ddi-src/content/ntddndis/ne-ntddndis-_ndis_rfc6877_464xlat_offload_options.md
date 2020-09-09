---
UID: NE:ntddndis._NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS
title: _NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS (ntddndis.h)
description: The NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS enumeration describes a miniport driver's 464XLAT hardware offload capabilities.
tech.root: netvista
ms.assetid: b3f8ea58-f66e-4e5d-bd2c-4dcedca81d95
ms.date: 05/22/2018
keywords: ["NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS enumeration"]
ms.keywords: _NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS, NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS,
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: 
req.target-min-winverclnt: NDIS 6.70
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS
 - ntddndis/_NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS
 - NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS
 - ntddndis/NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS
---

# _NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS enumeration


## -description

The **NDIS_RFC6877_464XLAT_OFFLOAD_OPTIONS** enumeration describes a miniport driver's 464XLAT hardware offload capabilities.

## -enum-fields

### -field NDIS_RFC6877_464XLAT_OFFLOAD_NOT_SUPPORTED 

The driver is incapable of 464XLAT hardware offload.

### -field NDIS_RFC6877_464XLAT_OFFLOAD_DISABLED 

The driver is capable of 464XLAT hardware offload, but it is disabled.

### -field NDIS_RFC6877_464XLAT_OFFLOAD_ENABLED 

The driver is capable of 464XLAT hardware offload, and it is enabled at all times.

### -field NDIS_RFC6877_464XLAT_OFFLOAD_ON_DEMAND 

The driver is capable of 464XLAT hardware offload, and it is only enabled on-demand.

## -remarks

## -see-also

[**NDIS_RFC6877_464XLAT_OFFLOAD**](ns-ntddndis-_ndis_rfc6877_464xlat_offload.md)

[**NDIS_OFFLOAD**](ns-ntddndis-_ndis_offload.md)

