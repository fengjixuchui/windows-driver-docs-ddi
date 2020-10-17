---
UID: NF:ntifs.CcRepinBcb
title: CcRepinBcb function (ntifs.h)
description: The CcRepinBcb routine pins a buffer control block (BCB) an additional time to prevent it from being freed by a subsequent call to CcUnpinData.
old-location: ifsk\ccrepinbcb.htm
tech.root: ifsk
ms.assetid: 81c2446e-8f11-4146-8da5-17fc451c2729
ms.date: 04/16/2018
keywords: ["CcRepinBcb function"]
ms.keywords: CcRepinBcb, CcRepinBcb routine [Installable File System Drivers], ccref_5aacfd67-3d6c-4be6-9bfa-5b85772ce32f.xml, ifsk.ccrepinbcb, ntifs/CcRepinBcb
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - CcRepinBcb
 - ntifs/CcRepinBcb
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcRepinBcb
---

# CcRepinBcb function


## -description

The <b>CcRepinBcb</b> routine pins a buffer control block (BCB) an additional time to prevent it from being freed by a subsequent call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindata">CcUnpinData</a>.

## -parameters

### -param Bcb 

[in]
Buffer control block (BCB) pointer returned by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinread">CcPinRead</a> or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparepinwrite">CcPreparePinWrite</a>.

## -remarks

File systems call <b>CcRepinBcb</b> to preserve a BCB for write-through or error recovery. Typically a file system would do this the first time it marks a BCB as dirty while processing a write-through request, or any time that it determines that a buffer will be required for write-through.

Every call to <b>CcRepinBcb</b> must be matched by a subsequent call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpinrepinnedbcb">CcUnpinRepinnedBcb</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinread">CcPinRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparepinwrite">CcPreparePinWrite</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindata">CcUnpinData</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpinrepinnedbcb">CcUnpinRepinnedBcb</a>