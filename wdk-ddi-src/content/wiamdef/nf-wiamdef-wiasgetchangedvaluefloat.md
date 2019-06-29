---
UID: NF:wiamdef.wiasGetChangedValueFloat
title: wiasGetChangedValueFloat function (wiamdef.h)
description: The wiasGetChangedValueFloat function determines whether a property with a floating-point value has been changed by an application.
old-location: image\wiasgetchangedvaluefloat.htm
tech.root: image
ms.assetid: 934ea038-e8fb-446d-8ba8-1cde56d3af87
ms.date: 05/03/2018
ms.keywords: image.wiasgetchangedvaluefloat, wiamdef/wiasGetChangedValueFloat, wiasFncs_d7b124d9-d108-4293-946c-a5d6bb43996f.xml, wiasGetChangedValueFloat, wiasGetChangedValueFloat function [Imaging Devices]
ms.topic: function
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
- wiasGetChangedValueFloat
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasGetChangedValueFloat function


## -description


The <b>wiasGetChangedValueFloat </b>function determines whether a property with a floating-point value has been changed by an application.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param pContext [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_wia_property_context">WIA_PROPERTY_CONTEXT</a> structure that contains the current property context.


### -param bNoValidation

Indicates whether the property's current value should be validated against its set of valid values. If this parameter is set to <b>TRUE</b>, the function does not perform validation on the property. If it is <b>FALSE</b>, the function performs data validation. 


### -param propID

Specifies the property identifier of the property being tested.


### -param pInfo






#### - pValInfo [out]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_wias_changed_value_info">WIAS_CHANGED_VALUE_INFO</a> structure that contains the current and previous values of the property.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -remarks



The driver should validate the property only after the driver has updated the values of the property. The driver updates the values as a result of property changes requested by the application.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_wias_changed_value_info">WIAS_CHANGED_VALUE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_wia_property_context">WIA_PROPERTY_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasgetchangedvalueguid">wiasGetChangedValueGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasgetchangedvaluelong">wiasGetChangedValueLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasgetchangedvaluestr">wiasGetChangedValueStr</a>
 

 

