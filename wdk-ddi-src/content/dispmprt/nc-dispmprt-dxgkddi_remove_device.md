---
UID: NC:dispmprt.DXGKDDI_REMOVE_DEVICE
title: DXGKDDI_REMOVE_DEVICE (dispmprt.h)
description: The DxgkDdiRemoveDevice function frees any resources allocated during DxgkDdiAddDevice.
old-location: display\dxgkddiremovedevice.htm
tech.root: display
ms.assetid: 0d5f96e8-dcb3-49e5-8347-ba20d757618b
ms.date: 05/10/2018
keywords: ["DXGKDDI_REMOVE_DEVICE callback function"]
ms.keywords: DXGKDDI_REMOVE_DEVICE, DXGKDDI_REMOVE_DEVICE callback, DmFunctions_b8ab26af-93dd-4e49-b2a2-9c620678457d.xml, DxgkDdiRemoveDevice, DxgkDdiRemoveDevice callback function [Display Devices], display.dxgkddiremovedevice, dispmprt/DxgkDdiRemoveDevice
f1_keywords:
 - "dispmprt/DxgkDdiRemoveDevice"
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiRemoveDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_REMOVE_DEVICE callback function


## -description


The <i>DxgkDdiRemoveDevice</i> function frees any resources allocated during <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


## -returns



<i>DxgkDdiRemoveDevice </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



<i>DxgkDdiRemoveDevice</i> must free the context block represented by <i>MiniportDeviceContext</i>.

<i>DxgkDdiRemoveDevice</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>
 

 

