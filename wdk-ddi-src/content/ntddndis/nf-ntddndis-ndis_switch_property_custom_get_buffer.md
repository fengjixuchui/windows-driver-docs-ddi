---
UID: NF:ntddndis.NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER
title: NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER macro (ntddndis.h)
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER macro to access the custom extensible switch property buffer inside an NDIS_SWITCH_PROPERTY_CUSTOM structure.
tech.root: netvista
ms.assetid: b4581a05-fdc8-446a-b6d3-05d02a1f48c8
ms.date: 04/17/2018
keywords: ["NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER macro"]
ms.keywords: NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER
 - ntddndis/NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER
---

# NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER** macro to access the custom extensible switch property buffer inside an [**NDIS_SWITCH_PROPERTY_CUSTOM**](ns-ntddndis-_ndis_switch_property_custom.md) structure.

## -parameters

### -param _SwitchPropertyCustom_

A pointer to an **NDIS_SWITCH_PROPERTY_CUSTOM** structure.

## -returns

The **NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER** macro returns a pointer to the custom extensible switch property buffer inside an [**NDIS_SWITCH_PROPERTY_CUSTOM**](ns-ntddndis-_ndis_switch_property_custom.md) structure.

## -remarks

## -see-also

[**NDIS_SWITCH_PROPERTY_CUSTOM**](ns-ntddndis-_ndis_switch_property_custom.md)

