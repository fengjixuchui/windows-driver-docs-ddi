---
UID: NF:wiamdef.wiasFreePropContext
title: wiasFreePropContext function (wiamdef.h)
description: The wiasFreePropContext function releases the memory occupied by a WIA_PROPERTY_CONTEXT structure.
old-location: image\wiasfreepropcontext.htm
tech.root: image
ms.assetid: 14a1a5bd-acc3-4ca6-87c6-5326c0f9ca82
ms.date: 05/03/2018
ms.keywords: image.wiasfreepropcontext, wiamdef/wiasFreePropContext, wiasFncs_60deac65-fa17-4f2e-abe1-fa6d424dc477.xml, wiasFreePropContext, wiasFreePropContext function [Imaging Devices]
ms.topic: function
f1_keywords:
 - "wiamdef/wiasFreePropContext"
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasFreePropContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasFreePropContext function


## -description


The <b>wiasFreePropContext </b>function releases the memory occupied by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_wia_property_context">WIA_PROPERTY_CONTEXT</a> structure.


## -parameters




### -param pContext [in, out]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_wia_property_context">WIA_PROPERTY_CONTEXT</a> structure that contains a property context.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_wia_property_context">WIA_PROPERTY_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiascreatepropcontext">wiasCreatePropContext</a>
 

 

