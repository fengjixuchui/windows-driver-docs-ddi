---
UID: NF:wiamdef.wiasReadPropFloat
title: wiasReadPropFloat function (wiamdef.h)
description: The wiasReadPropFloat function retrieves a floating-point property value from a WIA item.
old-location: image\wiasreadpropfloat.htm
tech.root: image
ms.assetid: 042ef9d9-a980-41eb-a396-e03658ea072a
ms.date: 05/03/2018
keywords: ["wiasReadPropFloat function"]
ms.keywords: image.wiasreadpropfloat, wiamdef/wiasReadPropFloat, wiasFncs_9b143e96-64a5-4de3-b40d-c542bc440dc0.xml, wiasReadPropFloat, wiasReadPropFloat function [Imaging Devices]
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
targetos: Windows
req.typenames: 
f1_keywords:
 - wiasReadPropFloat
 - wiamdef/wiasReadPropFloat
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasReadPropFloat
---

# wiasReadPropFloat function


## -description

The <b>wiasReadPropFloat </b>function retrieves a floating-point property value from a WIA item.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param propid

Specifies the property identifier.

### -param pfVal 

[out]
Pointer to a memory location that receives the floating-point value of the property.

### -param pfValOld 

[out, optional]
Pointer to a memory location that receives the former floating-point value of the property. If this information is not needed, set this parameter to <b>NULL</b>.

### -param bMustExist

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist; if set to <b>FALSE</b>, it does not have to exist.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropbin">wiasReadPropBin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropguid">wiasReadPropGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadproplong">wiasReadPropLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropstr">wiasReadPropStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropfloat">wiasWritePropFloat</a>

