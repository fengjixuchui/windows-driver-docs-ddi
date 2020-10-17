---
UID: NF:d3dkmthk.D3DKMTSignalSynchronizationObject
title: D3DKMTSignalSynchronizationObject function (d3dkmthk.h)
description: The D3DKMTSignalSynchronizationObject function inserts a signal for the specified synchronization objects in the specified context stream.
old-location: display\d3dkmtsignalsynchronizationobject.htm
ms.assetid: 1b8fc764-023f-4aa0-b610-2394a48efc02
ms.date: 05/10/2018
keywords: ["D3DKMTSignalSynchronizationObject function"]
ms.keywords: D3DKMTSignalSynchronizationObject, D3DKMTSignalSynchronizationObject function [Display Devices], OpenGL_Functions_183a6489-8a99-4dd3-a697-04db44b229c9.xml, d3dkmthk/D3DKMTSignalSynchronizationObject, display.d3dkmtsignalsynchronizationobject
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTSignalSynchronizationObject
 - d3dkmthk/D3DKMTSignalSynchronizationObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTSignalSynchronizationObject
---

# D3DKMTSignalSynchronizationObject function


## -description

The <b>D3DKMTSignalSynchronizationObject</b> function inserts a signal for the specified synchronization objects in the specified context stream.

## -parameters

### -param D3DKMT_SIGNALSYNCHRONIZATIONOBJECT

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_signalsynchronizationobject">D3DKMT_SIGNALSYNCHRONIZATIONOBJECT</a> structure that describes the synchronization objects and context stream that signaling is set up for.

## -returns

<b>D3DKMTSignalSynchronizationObject</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The signaling was successfully set up.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display context was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_signalsynchronizationobject">D3DKMT_SIGNALSYNCHRONIZATIONOBJECT</a>