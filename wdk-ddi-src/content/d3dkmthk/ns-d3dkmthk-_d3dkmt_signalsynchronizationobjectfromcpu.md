---
UID: NS:d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
title: _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU (d3dkmthk.h)
description: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU is used with D3DKMTSignalSynchronizationObjectFromCpu to enable a driver to signal a monitored fence.
old-location: display\d3dkmt_signalsynchronizationobjectfromcpu.htm
ms.assetid: 03B822CF-2FB0-412B-9F45-43756D8B4C19
ms.date: 05/10/2018
keywords: ["D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure"]
ms.keywords: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure [Display Devices], _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, display.d3dkmt_signalsynchronizationobjectfromcpu
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
f1_keywords:
 - _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
 - d3dkmthk/_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
 - D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
 - d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
---

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure


## -description

<b>D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromcpu">D3DKMTSignalSynchronizationObjectFromCpu</a> to enable a driver to signal a monitored fence.

## -struct-fields

### -field hDevice

[in] The handle to the device.

### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> and fence values in the <b>FenceValueArray</b>.

### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events to signal.

### -field FenceValueArray

[in] An array of 64 bit monitored fence values to signal, each corresponding to an object in the <b>ObjectHandleArray</b>.

### -field Flags

 

Flag options.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromcpu">D3DKMTSignalSynchronizationObjectFromCpu</a>