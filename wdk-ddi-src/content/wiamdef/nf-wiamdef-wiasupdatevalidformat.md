---
UID: NF:wiamdef.wiasUpdateValidFormat
title: wiasUpdateValidFormat function (wiamdef.h)
description: The wiasUpdateValidFormat function updates the valid format of the property context for the current minidriver.
old-location: image\wiasupdatevalidformat.htm
tech.root: image
ms.assetid: 04e66f34-3771-4b09-b546-f814e4b41906
ms.date: 05/03/2018
ms.keywords: image.wiasupdatevalidformat, wiamdef/wiasUpdateValidFormat, wiasFncs_dfbd0aa5-1c7c-4b4f-a1da-82176b36e914.xml, wiasUpdateValidFormat, wiasUpdateValidFormat function [Imaging Devices]
ms.topic: function
f1_keywords:
 - "wiamdef/wiasUpdateValidFormat"
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
- wiasUpdateValidFormat
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasUpdateValidFormat function


## -description


The <b>wiasUpdateValidFormat</b> function updates the valid format of the property context for the current minidriver.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param pContext [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context">WIA_PROPERTY_CONTEXT</a> structure containing a property context.


### -param pIMiniDrv [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv">IWiaMiniDrv Interface</a> of the current minidriver.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context">WIA_PROPERTY_CONTEXT</a>
 

 

