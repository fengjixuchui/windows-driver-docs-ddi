---
UID: NF:ntddndis.NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO
title: NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO macro (ntddndis.h)
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO macro to access the first NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO element that is specified by an NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS structure.
tech.root: netvista
ms.assetid: 6aa3c33f-b9ed-467c-868b-dc4134107425
ms.date: 04/17/2018
keywords: ["NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO macro"]
ms.keywords: NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO
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
 - NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO
 - ntddndis/NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO
---

# NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO** macro to access the first [**NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_port_property_enum_info.md) element that is specified by an [**NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS**](ns-ntddndis-_ndis_switch_port_property_enum_parameters.md) structure.

## -parameters

### -param _PortEnumParams_

A pointer to an **NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS** structure.

## -returns

The **NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO** macro returns a pointer to the first [**NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_port_property_enum_info.md) element that is specified by an [**NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS**](nf-ntddndis-ndis_switch_port_property_enum_parameters_get_first_info.md) structure.

## -remarks

## -see-also

[**NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_port_property_enum_info.md)

[**NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS**](ns-ntddndis-_ndis_switch_port_property_enum_parameters.md)

