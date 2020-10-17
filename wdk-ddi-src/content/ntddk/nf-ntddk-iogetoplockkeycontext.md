---
UID: NF:ntddk.IoGetOplockKeyContext
title: IoGetOplockKeyContext function (ntddk.h)
description: The IoGetOplockKeyContext routine returns a target oplock key context for a file object.
old-location: ifsk\iogetoplockkeycontext.htm
tech.root: ifsk
ms.assetid: E93091A2-203B-418D-93E7-1219DED25C52
ms.date: 04/16/2018
keywords: ["IoGetOplockKeyContext function"]
ms.keywords: IoGetOplockKeyContext, IoGetOplockKeyContextEx, IoGetOplockKeyContextEx routine [Installable File System Drivers], ifsk.iogetoplockkeycontext, ntddk/IoGetOplockKeyContextEx
req.header: ntddk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: The IoGetOplockKeyContext routine is available starting with Windows 7.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetOplockKeyContext
 - ntddk/IoGetOplockKeyContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - IoGetOplockKeyContextEx
---

# IoGetOplockKeyContext function


## -description

The <b>IoGetOplockKeyContext</b> routine returns a target oplock key context for a file object.

## -parameters

### -param FileObject

The file object to query for an oplock key context.

## -returns

An pointer to an <a href="/windows-hardware/drivers/ifs/oplock-key-ecp-context">OPLOCK_KEY_ECP_CONTEXT</a> structure containing the target oplock key for <i>FileObject</i>. Otherwise, NULL if <i>FileObject</i>  has no target oplock key.

## -remarks

Use the <b>IoGetOplockKeyContext</b> routine only in Windows 7. Because  <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogetoplockkeycontextex">IoGetOplockKeyContextEx</a> returns a dual oplock key context, it should be used in Windows 8 and later versions of Windows.

## -see-also

<a href="/windows-hardware/drivers/ifs/dual-oplock-key-ecp-context">DUAL_OPLOCK_KEY_ECP_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogetoplockkeycontextex">IoGetOplockKeyContextEx</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_oplock_key_context">OPLOCK_KEY_CONTEXT</a>



<a href="/windows-hardware/drivers/ifs/oplock-key-ecp-context">OPLOCK_KEY_ECP_CONTEXT</a>