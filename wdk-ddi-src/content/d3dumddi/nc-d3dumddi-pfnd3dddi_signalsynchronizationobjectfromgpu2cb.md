---
UID: NC:d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB (d3dumddi.h)
description: pfnSignalSynchronizationObjectFromGpu2Cb is used to signal a monitored fence.
old-location: display\pfnsignalsynchronizationobjectfromgpu2cb.htm
tech.root: display
ms.assetid: 03F9E47D-A3CA-44A1-A136-8236309D3D36
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB callback function"]
ms.keywords: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB, PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB callback, d3dumddi/pfnSignalSynchronizationObjectFromGpu2Cb, display.pfnsignalsynchronizationobjectfromgpu2cb, pfnSignalSynchronizationObjectFromGpu2Cb, pfnSignalSynchronizationObjectFromGpu2Cb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB
 - d3dumddi/PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnSignalSynchronizationObjectFromGpu2Cb
product:
 - Windows
---

# PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB callback function


## -description

<b>pfnSignalSynchronizationObjectFromGpu2Cb</b> is used to signal a monitored fence. When a particular graphics processing unit (GPU) engine is not capable of writing a new monitored fence value directly using its GPU virtual address, the driver needs to flush its command buffer and issue a signal from the GPU packet using <b>pfnSignalSynchronizationObjectFromGpu2Cb</b>. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb">pfnSignalSynchronizationObjectCb</a> and <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb">pfnSignalSynchronizationObject2Cb</a> callbacks are deprecated and will eventually be removed. WDDM v2 user mode drivers should switch to <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpucb">pfnSignalSynchronizationObjectFromGpuCb</a>, as it supports all synchronization object types.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromgpu2">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a> structure that provides the details of the requested operation.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromgpu2">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb">pfnSignalSynchronizationObject2Cb</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb">pfnSignalSynchronizationObjectCb</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpucb">pfnSignalSynchronizationObjectFromGpuCb</a>