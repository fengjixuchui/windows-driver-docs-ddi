---
UID: NC:d3dkmddi.DXGKCB_MULTIPLANEOVERLAYDISABLED
title: DXGKCB_MULTIPLANEOVERLAYDISABLED (d3dkmddi.h)
description: This callback allows the kernel mode driver to indicate that the current multiplane overlay configuration is no longer supported on the specified VidPnSourceId.
old-location: display\dxgkcb_multiplaneoverlaydisabled.htm
ms.assetid: EA9FAB26-1EAF-4E67-B240-094BC2B03DEF
ms.date: 05/10/2018
ms.keywords: DXGKCB_MULTIPLANEOVERLAYDISABLED, DXGKCB_MULTIPLANEOVERLAYDISABLED callback, DXGKCB_MULTIPLANEOVERLAYDISABLED callback function [Display Devices], d3dkmddi/DXGKCB_MULTIPLANEOVERLAYDISABLED, display.dxgkcb_multiplaneoverlaydisabled
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: requires_max_(PASSIVE_LEVEL)
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DXGKCB_MULTIPLANEOVERLAYDISABLED"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_MULTIPLANEOVERLAYDISABLED
product:
 - Windows
---

# DXGKCB_MULTIPLANEOVERLAYDISABLED callback function

## -description

This callback allows the kernel mode driver to indicate that the current multiplane overlay configuration is no longer supported on the specified VidPnSourceId.

## -parameters

### -param hAdapter

Indicates the adapter on which the current multiplane overlay hardware configuration is no longer supported.

### -param VidPnSourceId

Indicates the VidPnSourceId on which the current multiplane overlay hardware configuration is no longer supported.

## -returns

DXGKCB_MULTIPLANEOVERLAYDISABLED returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|If the call has been successfully completed.|

## -remarks

This callback will notify the DWM that the current MPO configuration is no longer supported, allowing the DWM to fall back to composition. 

This callback can only be called at passive level.


This callback can be used in the following scenarios:


* A display change or hot plug event on one output makes it no longer possible to continue supporting an MPO configuration that is committed to a different monitor. In this case, the driver can disable the overlay planes on the monitor. The user will see a visible artifact but it should be corrected eventually by the DWM.

* MPO should be disabled due to thermal issues. In this case, the driver does not need to immediately disable MPO, but can wait until the DWM receives the notification and requires MPO support (which the KMD should indicate is not supported due to the thermal issue). At that time, the DWM will disable MPO and start composing.

