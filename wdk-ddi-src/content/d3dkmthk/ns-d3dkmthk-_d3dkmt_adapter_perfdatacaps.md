---
UID: NS:d3dkmthk._D3DKMT_ADAPTER_PERFDATACAPS
title: _D3DKMT_ADAPTER_PERFDATACAPS (d3dkmthk.h)
description: Represents data capabilities that are static and queried once per GPU during initialization.
ms.assetid: 3b903827-ca27-425d-afdf-04e1d43436dc
ms.date: 10/19/2018
keywords: ["_D3DKMT_ADAPTER_PERFDATACAPS structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_ADAPTER_PERFDATACAPS"
 - "_D3DKMT_ADAPTER_PERFDATACAPS"
ms.keywords: _D3DKMT_ADAPTER_PERFDATACAPS, D3DKMT_ADAPTER_PERFDATACAPS,
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_ADAPTER_PERFDATACAPS
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- _D3DKMT_ADAPTER_PERFDATACAPS
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_ADAPTER_PERFDATACAPS structure

## -description

Represents data capabilities that are static and queried once per GPU during initialization.

## -struct-fields

### -field PhysicalAdapterIndex

The physical adapter index in the LDA (linked display adapter) chain.

### -field MaxMemoryBandwidth

Max memory bandwidth in bytes for 1 second.

### -field MaxPCIEBandwidth

Max PCIE bandwidth in bytes for 1 second.

### -field MaxFanRPM

The max fan rpm of the main fan.

### -field TemperatureMax

The max temperature before damage levels occur in deci Celsius. 1 = 0.1C.

### -field TemperatureWarning

The temperature level where temperature based throttling begins in deci Celsius. 1 = 0.1C.

