---
UID: NF:wdm.KzRaiseIrql
title: KzRaiseIrql function (wdm.h)
description: Raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor.
ms.assetid: 61da4441-a9bd-47dc-bc54-23699213701a
ms.date: 09/30/2018
keywords: ["KzRaiseIrql function"]
f1_keywords:
 - "wdm/KzRaiseIrql"
 - "KzRaiseIrql"
ms.keywords: KzRaiseIrql, KeRaiseIrql
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.lib
req.dll:
req.irql: HIGH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- KzRaiseIrql
targetos: Windows


ms.custom: RS5
---

# KzRaiseIrql function


## -description

Raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor. For information about IRQLs, see [Managing Hardware Priorities](https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-hardware-priorities).

## -parameters

### -param NewIrql
[in] Specifies the new IRQL to which the hardware priority is to be raised.

## -returns
The original (unraised) IRQL value to be used in a subsequent call to [**KzLowerIrql**](nf-wdm-kzlowerirql.md).

## -remarks

This function is same as the [**KeRaiseIrql**](nf-wdm-keraiseirql.md) function.


## -see-also
