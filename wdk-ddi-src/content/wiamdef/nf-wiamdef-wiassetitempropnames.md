---
UID: NF:wiamdef.wiasSetItemPropNames
title: wiasSetItemPropNames function (wiamdef.h)
description: The wiasSetItemPropNames function writes property names to item properties.
old-location: image\wiassetitempropnames.htm
tech.root: image
ms.assetid: 4140a6c6-60e8-41ec-8de0-cfb56e757e34
ms.date: 05/03/2018
keywords: ["wiasSetItemPropNames function"]
ms.keywords: image.wiassetitempropnames, wiamdef/wiasSetItemPropNames, wiasFncs_e8f17c14-47a7-42bc-ad85-cdd52ecbab79.xml, wiasSetItemPropNames, wiasSetItemPropNames function [Imaging Devices]
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
 - wiasSetItemPropNames
 - wiamdef/wiasSetItemPropNames
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasSetItemPropNames
---

# wiasSetItemPropNames function


## -description

The <b>wiasSetItemPropNames </b>function writes property names to item properties.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param cItemProps

Specifies the number of property names to write.

### -param ppId 

[in, out]
Pointer to the first element of a caller-allocated array of property identifiers (PROPIDs).

### -param ppszNames

#### - ppSzNames [in, out]

Pointer to the first element of a caller-allocated array of property names to write.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -remarks

Minidrivers typically use this function when initializing item properties. The order of property identifiers in <i>ppId</i> must match the order of property names in <i>ppSzNames</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetitempropattribs">wiasSetItemPropAttribs</a>

