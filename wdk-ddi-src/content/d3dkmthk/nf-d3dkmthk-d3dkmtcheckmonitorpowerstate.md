---
UID: NF:d3dkmthk.D3DKMTCheckMonitorPowerState
title: D3DKMTCheckMonitorPowerState function (d3dkmthk.h)
description: The D3DKMTCheckMonitorPowerState function verifies the power state of a monitor.
old-location: display\d3dkmtcheckmonitorpowerstate.htm
ms.assetid: 8f218b63-304e-4f25-88d8-ea1326c613ee
ms.date: 05/10/2018
keywords: ["D3DKMTCheckMonitorPowerState function"]
ms.keywords: D3DKMTCheckMonitorPowerState, D3DKMTCheckMonitorPowerState callback function [Display Devices], OpenGL_Functions_d05a2b63-fe81-45f0-908d-94043416b1d0.xml, PFND3DKMT_CHECKMONITORPOWERSTATE, PFND3DKMT_CHECKMONITORPOWERSTATE callback, d3dkmthk/D3DKMTCheckMonitorPowerState, display.d3dkmtcheckmonitorpowerstate
f1_keywords:
 - "d3dkmthk/D3DKMTCheckMonitorPowerState"
 - "D3DKMTCheckMonitorPowerState"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
api_name:
- D3DKMTCheckMonitorPowerState
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCheckMonitorPowerState function

## -description

The <b>D3DKMTCheckMonitorPowerState</b> function verifies the power state of a monitor.

## -parameters

### -param D3DKMT_CHECKMONITORPOWERSTATE

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_checkmonitorpowerstate">D3DKMT_CHECKMONITORPOWERSTATE</a> structure that describes the connection to the monitor for which to check the power state. 

## -returns

<b>D3DKMTCheckMonitorPowerState</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The power state of the monitor was successfully verified.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_checkmonitorpowerstate">D3DKMT_CHECKMONITORPOWERSTATE</a>
 

 

