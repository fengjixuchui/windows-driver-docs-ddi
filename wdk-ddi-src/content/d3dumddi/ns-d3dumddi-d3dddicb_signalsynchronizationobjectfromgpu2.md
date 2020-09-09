---
UID: NS:d3dumddi.D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
title: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 (d3dumddi.h)
description: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 is used with pfnSignalSynchronizationObjectFromGpu2Cb to signal a monitored fence.
old-location: display\d3dddicb_signalsynchronizationobjectfromgpu2.htm
tech.root: display
ms.assetid: 077BFCCB-4963-40CF-B56E-EAA08681ED5F
ms.date: 05/10/2018
keywords: ["D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure"]
ms.keywords: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure [Display Devices], d3dumddi/D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2, display.d3dddicb_signalsynchronizationobjectfromgpu2
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
f1_keywords:
 - D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
 - d3dumddi/D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
---

# D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 structure


## -description

<b>D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpu2cb">pfnSignalSynchronizationObjectFromGpu2Cb</a> to signal a monitored fence.

## -struct-fields

### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.

### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for.

### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_signalflags">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.

### -field BroadcastContextCount

[in] The number of contexts this signal operation will be broadcast to.

### -field BroadcastContextArray

[in] An array of kernel-mode handles to the context streams in which a signal for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted. The synchronization events are considered signaled only when all broadcast contexts reach the signal insertion point.

### -field FenceValue

[in] A 64-bit value that specifies the current fence value of the GPU synchronization object. This value applies only if the GPU synchronization object is of type <b>D3DDDI_FENCE</b>.

### -field CpuEventHandle

[in] The handle of an event object that will be signaled when the signal command is processed. This member must be set only when <b>Flags.EnqueueCpuEvent</b> is specified.

### -field MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to signal, each of which correspond to a synchronization object in <b>ObjectHandleArray</b>.

### -field Reserved

This member is reserved and should be set to zero.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_signalflags">D3DDDICB_SIGNALFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpu2cb">pfnSignalSynchronizationObjectFromGpu2Cb</a>

