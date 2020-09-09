---
UID: NF:ntddk.IoClearActivityIdThread
title: IoClearActivityIdThread function (ntddk.h)
description: The IoClearActivityIdThread routine clears the activity ID of the current thread.
old-location: kernel\ioclearactivityidthread.htm
tech.root: kernel
ms.assetid: 2F69FC2F-C336-4B51-8EFC-0A9AA22121B9
ms.date: 04/30/2018
keywords: ["IoClearActivityIdThread function"]
ms.keywords: IoClearActivityIdThread, IoClearActivityIdThread routine [Kernel-Mode Driver Architecture], kernel.ioclearactivityidthread, ntddk/IoClearActivityIdThread
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - IoClearActivityIdThread
 - ntddk/IoClearActivityIdThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoClearActivityIdThread
---

# IoClearActivityIdThread function


## -description

The IoClearActivityIdThread routine clears the activity ID of the current thread.

## -parameters

### -param OriginalId 

[in]
The activity ID that was previously set on the thread.

