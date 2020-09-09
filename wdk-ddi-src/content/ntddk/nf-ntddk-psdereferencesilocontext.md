---
UID: NF:ntddk.PsDereferenceSiloContext
title: PsDereferenceSiloContext function (ntddk.h)
description: This routine decrements the reference count on the object.
old-location: kernel\psdereferencesilocontext.htm
tech.root: kernel
ms.assetid: B71C7E8F-E136-4C13-B771-03B3C3C1BE64
ms.date: 04/30/2018
keywords: ["PsDereferenceSiloContext function"]
ms.keywords: PsDereferenceSiloContext, PsDereferenceSiloContext routine [Kernel-Mode Driver Architecture], kernel.psdereferencesilocontext, ntddk/PsDereferenceSiloContext
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
req.irql: _IRQL_requires_max_(DISPATCH_LEVEL)
targetos: Windows
req.typenames: 
f1_keywords:
 - PsDereferenceSiloContext
 - ntddk/PsDereferenceSiloContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsDereferenceSiloContext
---

# PsDereferenceSiloContext function


## -description

This routine decrements the reference count on the object.

## -parameters

### -param SiloContext 

[in]
A pointer to the object created by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pscreatesilocontext">PsCreateSiloContext</a> routine. This parameter is required and it cannot be <b>NULL</b>.

## -remarks

If the reference count reaches zero it will call the cleanup callback provided when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pscreatesilocontext">PsCreateSiloContext</a> routine created the object.

