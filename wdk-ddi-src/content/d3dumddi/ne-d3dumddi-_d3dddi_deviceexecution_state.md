---
UID: NE:d3dumddi._D3DDDI_DEVICEEXECUTION_STATE
title: _D3DDDI_DEVICEEXECUTION_STATE (d3dumddi.h)
description: Indicates the state of the device.
old-location: display\d3dddi_deviceexecution_state.htm
tech.root: display
ms.assetid: E81A31B5-E06F-4848-9AC6-8A18E8E97E15
ms.date: 05/10/2018
keywords: ["D3DDDI_DEVICEEXECUTION_STATE enumeration"]
ms.keywords: D3DDDI_DEVICEEXECUTION_ACTIVE, D3DDDI_DEVICEEXECUTION_ERROR_DMAFAULT, D3DDDI_DEVICEEXECUTION_ERROR_OUTOFMEMORY, D3DDDI_DEVICEEXECUTION_HUNG, D3DDDI_DEVICEEXECUTION_RESET, D3DDDI_DEVICEEXECUTION_STATE, D3DDDI_DEVICEEXECUTION_STATE enumeration [Display Devices], D3DDDI_DEVICEEXECUTION_STOPPED, _D3DDDI_DEVICEEXECUTION_STATE, d3dumddi/D3DDDI_DEVICEEXECUTION_ACTIVE, d3dumddi/D3DDDI_DEVICEEXECUTION_ERROR_DMAFAULT, d3dumddi/D3DDDI_DEVICEEXECUTION_ERROR_OUTOFMEMORY, d3dumddi/D3DDDI_DEVICEEXECUTION_HUNG, d3dumddi/D3DDDI_DEVICEEXECUTION_RESET, d3dumddi/D3DDDI_DEVICEEXECUTION_STATE, d3dumddi/D3DDDI_DEVICEEXECUTION_STOPPED, display.d3dddi_deviceexecution_state
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: D3DDDI_DEVICEEXECUTION_STATE
f1_keywords:
 - _D3DDDI_DEVICEEXECUTION_STATE
 - d3dumddi/_D3DDDI_DEVICEEXECUTION_STATE
 - D3DDDI_DEVICEEXECUTION_STATE
 - d3dumddi/D3DDDI_DEVICEEXECUTION_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - D3DDDI_DEVICEEXECUTION_STATE
---

# _D3DDDI_DEVICEEXECUTION_STATE enumeration


## -description

Indicates the state of the device.

## -enum-fields

### -field D3DDDI_DEVICEEXECUTION_ACTIVE

The device is active.

### -field D3DDDI_DEVICEEXECUTION_RESET

The device has been reset.

### -field D3DDDI_DEVICEEXECUTION_HUNG

The device is still running but has stopped responding (it is "hung").

### -field D3DDDI_DEVICEEXECUTION_STOPPED

The device has stopped.

### -field D3DDDI_DEVICEEXECUTION_ERROR_OUTOFMEMORY

The device has run out of memory.

### -field D3DDDI_DEVICEEXECUTION_ERROR_DMAFAULT

The device has a DMA fault error.

