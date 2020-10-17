---
UID: NF:ks.KsGateInitializeOr
title: KsGateInitializeOr function (ks.h)
description: The KsGateInitializeOr function initializes a KSGATE structure as an OR gate and attaches it to the AND gate specified by NextAndGate.
old-location: stream\ksgateinitializeor.htm
tech.root: stream
ms.assetid: a02a3b53-03fa-49d4-835c-88623c2f4d8b
ms.date: 04/23/2018
keywords: ["KsGateInitializeOr function"]
ms.keywords: KsGateInitializeOr, KsGateInitializeOr function [Streaming Media Devices], avfunc_6741b878-dfae-4d40-9040-ab78d32243e2.xml, ks/KsGateInitializeOr, stream.ksgateinitializeor
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGateInitializeOr
 - ks/KsGateInitializeOr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsGateInitializeOr
---

# KsGateInitializeOr function


## -description

The<b> KsGateInitializeOr</b> function initializes a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure as an OR gate and attaches it to the AND gate specified by <i>NextAndGate</i>.

## -parameters

### -param OrGate 

[in]
A pointer to the KSGATE structure to initialize as a new OR gate.

### -param NextAndGate 

[in, optional]
A pointer to an existing KSGATE structure to which <i>OrGate</i> attaches. Optional.

## -remarks

The next gate (following <i>OrGate</i>) must be an AND gate, whether it is specified in this call or later. If you need to connect an OR gate to another OR gate, use <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitialize">KsGateInitialize</a>. For more information, see <a href="/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

This function is an inline call to <b>KsGateInitialize</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitialize">KsGateInitialize</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitializeand">KsGateInitializeAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateterminateand">KsGateTerminateAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateterminateor">KsGateTerminateOr</a>