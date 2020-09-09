---
UID: NF:wdm.ExReleasePushLockExclusive
title: ExReleasePushLockExclusive macro (wdm.h)
description: Releases a specified push lock for exclusive access owned by the current thread.
ms.assetid: 4405aad6-919c-4609-bd48-e29474827d8b
ms.date: 09/30/2018
keywords: ["ExReleasePushLockExclusive macro"]
ms.keywords: ExReleasePushLockExclusive
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - ExReleasePushLockExclusive
 - wdm/ExReleasePushLockExclusive
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - ExReleasePushLockExclusive
---

# ExReleasePushLockExclusive macro


## -description

Releases a specified push lock for exclusive access owned by the current thread.

## -parameters

### -param Lock

Opaque push lock pointer specified in the [**ExAcquirePushLockExclusive**](nf-wdm-exacquirepushlockexclusive.md) call. This pointer must have been initialized by a previous call to [**ExInitializePushLock**](nf-wdm-exinitializepushlock.md).

## -remarks

To acquire a push lock for exclusive access, call [**ExAcquirePushLockExclusive**](nf-wdm-exacquirepushlockexclusive.md).

To acquire a push lock for shared access, call [**ExAcquirePushLockShared**](nf-wdm-exacquirepushlockshared.md).

## -see-also

