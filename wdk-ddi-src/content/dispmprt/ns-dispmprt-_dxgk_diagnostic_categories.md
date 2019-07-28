---
UID: NS:dispmprt._DXGK_DIAGNOSTIC_CATEGORIES
title: _DXGK_DIAGNOSTIC_CATEGORIES (dispmprt.h)
description: Structure with a bit-field for each defined category of diagnostic.
ms.assetid: ba2233ae-fe9b-4cd1-a9a6-7a26c95d5dae
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "dispmprt/_DXGK_DIAGNOSTIC_CATEGORIES"
ms.keywords: _DXGK_DIAGNOSTIC_CATEGORIES, DXGK_DIAGNOSTIC_CATEGORIES,
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_DIAGNOSTIC_CATEGORIES
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- _DXGK_DIAGNOSTIC_CATEGORIES
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_DIAGNOSTIC_CATEGORIES structure

## -description

Structure with a bit-field for each defined category of diagnostic.

## -struct-fields

### -field Notifications

An OS defined category which has diagnostic types defined in the [DXGK_DIAGTYPE_NOTIFICATIONS](ns-dispmprt-_dxgk_diagtype_notifications.md) structure.

### -field Progressions

A [DXGK_DIAGTYPE_PROGRESSIONS](../dispmprt/ns-dispmprt-_dxgk_diagtype_progressions.md) structure for indicating a Progressions diagnostic type.

### -field Reserved

Reserved.

### -field Value

Value of the categories.

