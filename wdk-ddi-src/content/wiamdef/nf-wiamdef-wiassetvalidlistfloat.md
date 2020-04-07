---
UID: NF:wiamdef.wiasSetValidListFloat
title: wiasSetValidListFloat function (wiamdef.h)
description: The wiasSetValidListFloat function sets valid values for a WIA_PROP_LIST property of type VT_R4.
old-location: image\wiassetvalidlistfloat.htm
tech.root: image
ms.assetid: e1a833aa-fc8b-4506-aba8-ba6dc9a375ba
ms.date: 05/03/2018
keywords: ["wiasSetValidListFloat function"]
ms.keywords: image.wiassetvalidlistfloat, wiamdef/wiasSetValidListFloat, wiasFncs_ef1aa836-f63d-43e8-8378-22d37fbdc3a2.xml, wiasSetValidListFloat, wiasSetValidListFloat function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasSetValidListFloat"
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
- wiasSetValidListFloat
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasSetValidListFloat function


## -description


The <b>wiasSetValidListFloat </b>function sets valid values for a WIA_PROP_LIST property of type VT_R4.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the identifier of the property to be updated.


### -param ulCount

Specifies the number of items in the <i>plValues</i> array.


### -param fNom

Specifies the property's nominal value.


### -param pfValues [in]

Pointer to the first element of an array of valid property values.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidflag">wiasSetValidFlag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistguid">wiasSetValidListGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistlong">wiasSetValidListLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidliststr">wiasSetValidListStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangefloat">wiasSetValidRangeFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangelong">wiasSetValidRangeLong</a>
 

 

