---
UID: NF:wiamdef.wiasWritePropFloat
title: wiasWritePropFloat function (wiamdef.h)
description: The wiasWritePropFloat function writes a single floating-point property value to a WIA item.
old-location: image\wiaswritepropfloat.htm
tech.root: image
ms.assetid: 097cd455-018e-46ef-8b8f-8eae7ea3eaff
ms.date: 05/03/2018
ms.keywords: image.wiaswritepropfloat, wiamdef/wiasWritePropFloat, wiasFncs_49539474-675e-420d-b7a4-67f147017975.xml, wiasWritePropFloat, wiasWritePropFloat function [Imaging Devices]
ms.topic: function
f1_keywords:
 - "wiamdef/wiasWritePropFloat"
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
- wiasWritePropFloat
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasWritePropFloat function


## -description


The <b>wiasWritePropFloat </b>function writes a single floating-point property value to a WIA item.


## -parameters




### -param pWiasContext [in]

A Pointer to a WIA item context.


### -param propid

Specifies the property identifier.


### -param fVal

Specifies the floating-point property value to write to the item.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasreadpropfloat">wiasReadPropFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritepropbin">wiasWritePropBin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritepropguid">wiasWritePropGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswriteproplong">wiasWritePropLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiaswritepropstr">wiasWritePropStr</a>
 

 

