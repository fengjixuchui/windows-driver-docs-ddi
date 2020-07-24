---
UID: NC:d3dkmddi.DXGKDDI_DESTROYPROTECTEDSESSION
title: DXGKDDI_DESTROYPROTECTEDSESSION (d3dkmddi.h)
description: Used to destroy a protected session.
old-location: display\dxgkddi_destroyprotectedsession.htm
ms.assetid: 42D4064A-1697-4772-8450-6D217C526347
ms.date: 05/10/2018
keywords: ["DXGKDDI_DESTROYPROTECTEDSESSION callback function"]
ms.keywords: DXGKDDI_DESTROYPROTECTEDSESSION, DXGKDDI_DESTROYPROTECTEDSESSION callback, DXGKDDI_DESTROYPROTECTEDSESSION callback function [Display Devices], d3dkmddi/DXGKDDI_DESTROYPROTECTEDSESSION, display.dxgkddi_destroyprotectedsession
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
req.irql: requires_(PASSIVE_LEVEL)
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DXGKDDI_DESTROYPROTECTEDSESSION"
 - "DXGKDDI_DESTROYPROTECTEDSESSION"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_DESTROYPROTECTEDSESSION
product:
 - Windows
---

# DXGKDDI_DESTROYPROTECTEDSESSION callback function

## -description

Used to destroy a protected session.

## -parameters

### -param hAdapter

The handle generated for the adapter.

### -param hProtectedSession

The driver generated handle driver returned at DxgkDdiCreateProtectedSession.

## -returns

Returns STATUS_SUCCESS when completed successfully.

