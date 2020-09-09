---
UID: NF:wiamdef.wiasWritePropBin
title: wiasWritePropBin function (wiamdef.h)
description: The wiasWritePropBin function writes a single binary-data property value to a WIA item.
old-location: image\wiaswritepropbin.htm
tech.root: image
ms.assetid: 953a43dd-1cab-442b-9d77-f310805166ee
ms.date: 05/03/2018
keywords: ["wiasWritePropBin function"]
ms.keywords: image.wiaswritepropbin, wiamdef/wiasWritePropBin, wiasFncs_fa38d5cc-94dd-4a1f-9e24-e12c42ce0429.xml, wiasWritePropBin, wiasWritePropBin function [Imaging Devices]
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
 - wiasWritePropBin
 - wiamdef/wiasWritePropBin
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasWritePropBin
---

# wiasWritePropBin function


## -description

The <b>wiasWritePropBin </b>function writes a single binary-data property value to a WIA item.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param propid

Specifies the property identifier.

### -param cbVal

Specifies the total number of bytes to write to the item.

### -param pbVal 

[in]
Pointer to the first byte of an array of bytes to be written to the item.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropbin">wiasReadPropBin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropfloat">wiasWritePropFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropguid">wiasWritePropGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswriteproplong">wiasWritePropLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropstr">wiasWritePropStr</a>

