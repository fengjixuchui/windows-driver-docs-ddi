---
UID: NC:d3dumddi.PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB
title: PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB (d3dumddi.h)
description: The pfnDestroySynchronizationObjectCb function destroys the synchronization object that was created through a call to the pfnCreateSynchronizationObjectCb function.
old-location: display\pfndestroysynchronizationobjectcb.htm
tech.root: display
ms.assetid: 7ba549a2-f165-4b5e-8cf4-ab707222532c
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB callback function"]
ms.keywords: D3Druntime_Functions_a2b3f092-097e-4eb1-b38d-8f68e5edbcca.xml, PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB, PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB callback, d3dumddi/pfnDestroySynchronizationObjectCb, display.pfndestroysynchronizationobjectcb, pfnDestroySynchronizationObjectCb, pfnDestroySynchronizationObjectCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/pfnDestroySynchronizationObjectCb"
 - "pfnDestroySynchronizationObjectCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnDestroySynchronizationObjectCb
product:
 - Windows
---

# PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB callback function

## -description

The <b>pfnDestroySynchronizationObjectCb</b> function destroys the synchronization object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb">pfnCreateSynchronizationObjectCb</a> function.

## -parameters

### -param hDevice

A handle to a display device (that is, the graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_destroysynchronizationobject">D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT</a> structure that contains a handle to the synchronization object to destroy.

## -returns

<b>pfnDestroySynchronizationObjectCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The synchronization object was successfully destroyed.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 

This function might also return other HRESULT values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_destroysynchronizationobject">D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb">pfnCreateSynchronizationObjectCb</a>

