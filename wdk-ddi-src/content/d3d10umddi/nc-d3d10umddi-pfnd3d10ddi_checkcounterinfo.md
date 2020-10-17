---
UID: NC:d3d10umddi.PFND3D10DDI_CHECKCOUNTERINFO
title: PFND3D10DDI_CHECKCOUNTERINFO (d3d10umddi.h)
description: The CheckCounterInfo function determines global information that is related to manipulating counters.
old-location: display\checkcounterinfo.htm
ms.assetid: 5dcea47c-aac7-46e5-afd5-c3390c3c5286
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CHECKCOUNTERINFO callback function"]
ms.keywords: CheckCounterInfo, CheckCounterInfo callback function [Display Devices], PFND3D10DDI_CHECKCOUNTERINFO, PFND3D10DDI_CHECKCOUNTERINFO callback, UserModeDisplayDriverDx10_Functions_7057ce5a-5677-4174-9bee-81c8ab5b18f7.xml, d3d10umddi/CheckCounterInfo, display.checkcounterinfo
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_CHECKCOUNTERINFO
 - d3d10umddi/PFND3D10DDI_CHECKCOUNTERINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CheckCounterInfo
product:
 - Windows
---

# PFND3D10DDI_CHECKCOUNTERINFO callback function


## -description

The <b>CheckCounterInfo</b> function determines global information that is related to manipulating counters.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCounterInfo* [out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_counter_info">D3D10DDI_COUNTER_INFO</a> structure that the driver populates with global information that is related to manipulating counters.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

If the user-mode display driver does not support any of the concepts that are represented in the members of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_counter_info">D3D10DDI_COUNTER_INFO</a> structure, it can populate the members of D3D10DDI_COUNTER_INFO with zeros. 

The driver's <b>CheckCounterInfo</b> function cannot call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set the D3DDDIERR_DEVICEREMOVED error code because <b>CheckCounterInfo</b> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <b>CheckCounterInfo</b>, even in the presence of D3DDDIERR_DEVICEREMOVED. <b>CheckCounterInfo</b> should not encounter any errors. However, <b>CheckCounterInfo</b> might call <b>pfnSetErrorCb</b> for critical errors.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_counter_info">D3D10DDI_COUNTER_INFO</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>