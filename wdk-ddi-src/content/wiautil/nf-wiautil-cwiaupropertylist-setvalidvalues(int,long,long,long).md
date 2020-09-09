---
UID: NF:wiautil.CWiauPropertyList.SetValidValues(INT,LONG,LONG,LONG)
title: CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG) (wiautil.h)
description: The CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG) method sets the type, as well as default, current, and valid values for a property whose values are defined by a flag.
old-location: image\cwiaupropertylist_setvalidvalues_flag_.htm
tech.root: image
ms.assetid: e61b5bbb-14a8-4dfa-af36-99c5dd1ecc99
ms.date: 09/07/2018
keywords: ["CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG)"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetValidValues method, CWiauPropertyList.SetValidValues, CWiauPropertyList.SetValidValues(INT,LONG,LONG,LONG), CWiauPropertyList::SetValidValues, CWiauPropertyList::SetValidValues(INT  ,LONG  ,LONG  ,LONG  ), CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG), SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setvalidvalues_flag_, wiauFncs_11c27970-2fa2-480d-9f60-b12202b9b03c.xml, wiautil/CWiauPropertyList::SetValidValues
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - CWiauPropertyList::SetValidValues
 - wiautil/CWiauPropertyList::SetValidValues
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wiautil.h
api_name:
 - CWiauPropertyList.SetValidValues
---

# CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG)


## -description

The **CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG)** method sets the type, as well as default, current, and valid values for a property whose values are defined by a flag. The method also sets the property type to VT_I4 and subtype to WIA_PROP_FLAG.

## -parameters

### -param index

Specifies the property index. Set this parameter to the value in *_pIdx_ when the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method returns.

### -param defaultValue

Specifies the default setting of the property on the device.

### -param currentValue

Specifies the current setting of the property on the device.

### -param validFlags

Specifies a value containing all of the valid flags.

## -returns

This method does not return a value.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)

