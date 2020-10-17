---
UID: NS:wiamindr_lh._WIAS_ENDORSER_VALUE
title: _WIAS_ENDORSER_VALUE (wiamindr_lh.h)
description: The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings.
old-location: image\wias_endorser_value.htm
tech.root: image
ms.assetid: 54395899-c35d-4251-9e9d-ec2128b28c67
ms.date: 05/03/2018
keywords: ["WIAS_ENDORSER_VALUE structure"]
ms.keywords: "*PWIAS_ENDORSER_VALUE, PWIAS_ENDORSER_VALUE, PWIAS_ENDORSER_VALUE structure pointer [Imaging Devices], WIAS_ENDORSER_VALUE, WIAS_ENDORSER_VALUE structure [Imaging Devices], _WIAS_ENDORSER_VALUE, image.wias_endorser_value, wiamindr_lh/PWIAS_ENDORSER_VALUE, wiamindr_lh/WIAS_ENDORSER_VALUE, wiastrct_b6e376e1-ecfd-4988-b752-3d81755cf990.xml"
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Windows
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
req.typenames: WIAS_ENDORSER_VALUE, *PWIAS_ENDORSER_VALUE
f1_keywords:
 - _WIAS_ENDORSER_VALUE
 - wiamindr_lh/_WIAS_ENDORSER_VALUE
 - PWIAS_ENDORSER_VALUE
 - wiamindr_lh/PWIAS_ENDORSER_VALUE
 - WIAS_ENDORSER_VALUE
 - wiamindr_lh/WIAS_ENDORSER_VALUE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiamindr_lh.h
api_name:
 - WIAS_ENDORSER_VALUE
---

# _WIAS_ENDORSER_VALUE structure


## -description

The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings.

## -struct-fields

### -field wszTokenName

Specifies a string value that represents the token name. Endorser token names begin and end with the $ character (for example, L"$MY_TOKEN_NAME$").

### -field wszValue

Specifies the value with which to replace the token.

## -remarks

This structure is used indirectly by the [wiasParseEndorserString](../wiamdef/nf-wiamdef-wiasparseendorserstring.md) function. One of the parameters of this function is a [WIAS_ENDORSER_INFO](./ns-wiamindr_lh-_wias_endorser_info.md) structure, which has a WIAS_ENDORSER_VALUE structure as one of its members.

## -see-also

[WIAS_ENDORSER_INFO](./ns-wiamindr_lh-_wias_endorser_info.md)

[wiasParseEndorserString](../wiamdef/nf-wiamdef-wiasparseendorserstring.md)