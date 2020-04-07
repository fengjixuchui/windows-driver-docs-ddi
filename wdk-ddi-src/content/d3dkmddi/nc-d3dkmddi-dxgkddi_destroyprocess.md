---
UID: NC:d3dkmddi.DXGKDDI_DESTROYPROCESS
title: DXGKDDI_DESTROYPROCESS (d3dkmddi.h)
description: DxgkDdiDestroyProcess destroys a kernel mode driver process object.
old-location: display\dxgkddidestroyprocess.htm
ms.assetid: C5117F9B-876D-4F74-B528-47698666B44B
ms.date: 05/10/2018
keywords: ["DXGKDDI_DESTROYPROCESS callback function"]
ms.keywords: DXGKDDI_DESTROYPROCESS, DXGKDDI_DESTROYPROCESS callback, DxgkDdiDestroyProcess, DxgkDdiDestroyProcess callback function [Display Devices], d3dkmddi/DxgkDdiDestroyProcess, display.dxgkddidestroyprocess, dispmprt/DxgkDdiDestroyProcess
req.header: d3dkmddi.h
req.include-header: 
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
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiDestroyProcess"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
 - d3dkmddi.h
api_name:
 - DxgkDdiDestroyProcess
product:
 - Windows
---

# DXGKDDI_DESTROYPROCESS callback function

## -description

<b>DxgkDdiDestroyProcess</b> destroys a kernel mode driver process object.

## -parameters

### -param hAdapter

A handle to the display adapter.

### -param hKmdProcess

A handle to the kernel mode driver process.

## -returns

      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.

