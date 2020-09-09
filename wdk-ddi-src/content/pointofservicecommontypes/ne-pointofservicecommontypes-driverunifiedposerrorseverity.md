---
UID: NE:pointofservicecommontypes.DriverUnifiedPosErrorSeverity
title: DriverUnifiedPosErrorSeverity (pointofservicecommontypes.h)
description: This enumeration indicates the severity of the error.
old-location: pos\unifiedposerrorseverity.htm
tech.root: pos
ms.assetid: a8c592fa-2736-49e4-8d4d-8729baef9c49
ms.date: 02/23/2018
keywords: ["DriverUnifiedPosErrorSeverity enumeration"]
ms.keywords: AssistanceRequired, DriverUnifiedPosErrorSeverity, DriverUnifiedPosErrorSeverity enumeration, Fatal, Recoverable, UnknownErrorSeverity, Unrecoverable, Warning, pointofservicecommontypes/ AssistanceRequired, pointofservicecommontypes/DriverUnifiedPosErrorSeverity, pointofservicecommontypes/Fatal, pointofservicecommontypes/Recoverable, pointofservicecommontypes/UnknownErrorSeverity, pointofservicecommontypes/Unrecoverable, pointofservicecommontypes/Warning, pos.unifiedposerrorseverity
req.header: pointofservicecommontypes.h
req.include-header: Pointofservicecommontypes.h
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
req.typenames: DriverUnifiedPosErrorSeverity
f1_keywords:
 - DriverUnifiedPosErrorSeverity
 - pointofservicecommontypes/DriverUnifiedPosErrorSeverity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicecommontypes.h
api_name:
 - DriverUnifiedPosErrorSeverity
---

# DriverUnifiedPosErrorSeverity enumeration


## -description

This enumeration indicates the severity of the error.

## -enum-fields

### -field UnknownErrorSeverity

The severity of the error is not known.

### -field Warning

The error or warning is informational.

### -field Recoverable

The device can recover from the error without closing the application or rebooting.

### -field Unrecoverable

The device is still working, but it must close the application to recover from the error.

### -field AssistanceRequired

Intervention is needed to respond to the error.

### -field Fatal

The error requires that the device be rebooted.

