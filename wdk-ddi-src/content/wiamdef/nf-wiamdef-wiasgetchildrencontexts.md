---
UID: NF:wiamdef.wiasGetChildrenContexts
title: wiasGetChildrenContexts function (wiamdef.h)
description: The wiasGetChildrenContexts function retrieves an array of item contexts belonging to the current item's children.
old-location: image\wiasgetchildrencontexts.htm
tech.root: image
ms.assetid: a69216f4-1272-488f-8d06-8dc3b6a88452
ms.date: 05/03/2018
ms.keywords: image.wiasgetchildrencontexts, wiamdef/wiasGetChildrenContexts, wiasFncs_fff487b8-2797-4df4-ae22-f25c08f21dfc.xml, wiasGetChildrenContexts, wiasGetChildrenContexts function [Imaging Devices]
ms.topic: function
f1_keywords:
 - "wiamdef/wiasGetChildrenContexts"
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
- wiasGetChildrenContexts
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasGetChildrenContexts function


## -description


The <b>wiasGetChildrenContexts</b> function retrieves an array of item contexts belonging to the current item's children.


## -parameters




### -param pParentContext [in]

Pointer to the parent item.


### -param pulNumChildren [out]

Pointer to a memory location that receives the number of children contexts.


### -param pppChildren [out]

Pointer to a memory location that points to an array whose elements are addresses of <b>IWiaItem</b> objects (described in the Microsoft Windows SDK documentation). Each <b>IWiaItem</b> object represents one child context.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Windows SDK documentation).



