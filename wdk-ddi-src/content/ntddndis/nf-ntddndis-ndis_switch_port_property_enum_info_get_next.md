---
UID: NF:ntddndis.NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT
title: NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT macro (ntddndis.h)
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT macro to access the next NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO element that follows an NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO structure in the array that is specified by an NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS structure.
tech.root: netvista
ms.assetid: 7b35770f-2722-41ea-a161-4fcb20ee55d0
ms.date: 04/17/2018
keywords: ["NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT macro"]
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT"
 - "NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT"
ms.keywords: NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ntddndis.h
api_name: 
- NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT
targetos: Windows

---

# NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT** macro to access the next [**NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_port_property_enum_info.md) element that follows an **NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO** structure in the array that is specified by an [**NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS**](ns-ntddndis-_ndis_switch_port_property_enum_parameters.md) structure.

## -parameters

### -param _PortEnumInfo_

A pointer to an **NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO** structure.

## -returns

The **NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT** macro returns a pointer to the next [**NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_port_property_enum_info.md) element in the array. If the *\_\_PortEnumInfo\_\_* parameter is the last element in the array, the macro returns **NULL**.

## -remarks

## -see-also

[**NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_port_property_enum_info.md)

[**NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS**](ns-ntddndis-_ndis_switch_port_property_enum_parameters.md)
