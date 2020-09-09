---
UID: NE:dispmprt._DXGK_SURPRISE_REMOVAL_TYPE
title: _DXGK_SURPRISE_REMOVAL_TYPE (dispmprt.h)
description: Indicates the type of surprise removal event when an external display device is disconnected from the system.
old-location: display\dxgk_surprise_removal_type.htm
tech.root: display
ms.assetid: 3045f46d-d78a-4f07-9838-f3afd97d9244
ms.date: 08/05/2020
keywords: ["DXGK_SURPRISE_REMOVAL_TYPE enumeration"]
ms.keywords: DXGK_SURPRISE_REMOVAL_TYPE, DXGK_SURPRISE_REMOVAL_TYPE enumeration [Display Devices], DxgkRemovalHibernation, _DXGK_SURPRISE_REMOVAL_TYPE, display.dxgk_surprise_removal_type, dispmprt/DXGK_SURPRISE_REMOVAL_TYPE, dispmprt/DxgkRemovalHibernation
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: DXGK_SURPRISE_REMOVAL_TYPE
f1_keywords:
 - _DXGK_SURPRISE_REMOVAL_TYPE
 - dispmprt/_DXGK_SURPRISE_REMOVAL_TYPE
 - DXGK_SURPRISE_REMOVAL_TYPE
 - dispmprt/DXGK_SURPRISE_REMOVAL_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dispmprt.h
api_name:
 - DXGK_SURPRISE_REMOVAL_TYPE
---

# _DXGK_SURPRISE_REMOVAL_TYPE enumeration


## -description

Indicates the type of surprise removal event when an external display device is disconnected  from the system.

## -enum-fields

### -field DxgkRemovalHibernation

The disconnected external display device was in hibernation mode.

### -field DxgkRemovalPnPNotify

The disconnected external display device was surprise removed/unplugged while it was still running.

## -remarks

See the [**DXGKDDI_NOTIFY_SURPRISE_REMOVAL**](nc-dispmprt-dxgkddi_notify_surprise_removal.md) callback for details.

