---
UID: NF:wiamdef.wiasReadPropLong
title: wiasReadPropLong function (wiamdef.h)
description: The wiasReadPropLong function retrieves a long integer property value from a WIA item.
old-location: image\wiasreadproplong.htm
tech.root: image
ms.assetid: 77fc58fd-1bcf-4a68-b083-fa2bfa3ac312
ms.date: 05/03/2018
keywords: ["wiasReadPropLong function"]
ms.keywords: image.wiasreadproplong, wiamdef/wiasReadPropLong, wiasFncs_a60071a3-6ae9-431d-8d8b-a964547e9770.xml, wiasReadPropLong, wiasReadPropLong function [Imaging Devices]
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
 - wiasReadPropLong
 - wiamdef/wiasReadPropLong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasReadPropLong
---

# wiasReadPropLong function


## -description

The <b>wiasReadPropLong </b>function retrieves a long integer property value from a WIA item.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param propid

Specifies the property identifier.

### -param plVal 

[out]
Pointer to a memory location that receives the value of the property.

### -param plValOld 

[out, optional]
Pointer to a memory location that receives the property's previous value. If this information is not needed, set this parameter to <b>NULL</b>.

### -param bMustExist

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist, if set to <b>FALSE</b>, the property does not have to exist.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropbin">wiasReadPropBin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropfloat">wiasReadPropFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropguid">wiasReadPropGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropstr">wiasReadPropStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswriteproplong">wiasWritePropLong</a>

