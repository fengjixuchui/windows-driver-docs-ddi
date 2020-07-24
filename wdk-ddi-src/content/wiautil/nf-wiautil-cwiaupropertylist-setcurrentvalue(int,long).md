---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,LONG)
title: CWiauPropertyList::SetCurrentValue(INT,LONG) (wiautil.h)
description: The CWiauPropertyList::SetCurrentValue(INT,LONG) method sets the current value of a property of type LONG, and sets its type to VT_I4.
old-location: image\cwiaupropertylist_setcurrentvalue_long_.htm
tech.root: image
ms.assetid: 583c8ec9-7a57-4da3-beaf-9f9db943a652
ms.date: 09/07/2018
keywords: ["CWiauPropertyList::SetCurrentValue(INT,LONG)"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,LONG), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT,LONG), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setcurrentvalue_long_, wiauFncs_e59bb543-0827-4c93-955c-6a2bef4b67b7.xml, wiautil/CWiauPropertyList::SetCurrentValue
f1_keywords:
 - "wiautil/CWiauPropertyList.SetCurrentValue"
 - "CWiauPropertyList.SetCurrentValue"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wiautil.h
api_name:
- CWiauPropertyList.SetCurrentValue
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# CWiauPropertyList::SetCurrentValue(INT,LONG)

## -description

The **CWiauPropertyList::SetCurrentValue(INT,LONG)** method sets the current value of a property of type **LONG**, and sets its type to VT_I4.

## -parameters

### -param index

Specifies the property index. Set this parameter to the value in *<i>pIdx</i> when the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method returns.

### -param value

Specifies the value that is written to the device property in the property list.

## -returns

This method does not return a value.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)
