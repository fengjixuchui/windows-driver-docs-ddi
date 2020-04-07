---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030
title: PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 (d3d12umddi.h)
description: Used to create a protected session state.
old-location: display\pfnd3d12ddi_create_protected_session_cb_0030.htm
ms.assetid: 64E38759-2863-4481-8A89-6E6263CEFE8B
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback function"]
ms.keywords: PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030, PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback, PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030, display.pfnd3d12ddi_create_protected_session_cb_0030
req.header: d3d12umddi.h
req.include-header: 
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
req.typenames: 
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030
product:
 - Windows
---

# PFND3D12DDI_CREATE_PROTECTED_SESSION_CB_0030 callback function

## -description

Used to create a protected session state.

## -parameters

### -param hRTDevice

The hardware device being processed.

### -param hRTProtectedSession

The protected session.

### -param pArgs

*D3D12DDICB_CREATE_PROTECTED_RESOURCE_SESSION*

Arguments to use for the function.

## -returns

Returns STATUS_SUCCESS if completed successfully.

