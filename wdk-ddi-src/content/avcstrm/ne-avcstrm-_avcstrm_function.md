---
UID: NE:avcstrm._AVCSTRM_FUNCTION
title: _AVCSTRM_FUNCTION (avcstrm.h)
description: The AVCSTRM_FUNCTION enumeration defines the functionality exposed by the avcstrm.sys driver.
old-location: stream\avcstrm_function.htm
tech.root: stream
ms.assetid: 0dacc4b0-003f-4c73-8705-1c1e86ce357c
ms.date: 04/23/2018
keywords: ["AVCSTRM_FUNCTION enumeration"]
ms.keywords: AVCSTRM_ABORT_STREAMING, AVCSTRM_CLOSE, AVCSTRM_FUNCTION, AVCSTRM_FUNCTION enumeration [Streaming Media Devices], AVCSTRM_GET_PROPERTY, AVCSTRM_GET_STATE, AVCSTRM_OPEN, AVCSTRM_READ, AVCSTRM_SET_PROPERTY, AVCSTRM_SET_STATE, AVCSTRM_WRITE, _AVCSTRM_FUNCTION, avcsref_19b1714d-e3a3-40b8-8dd8-fb17ecb2e777.xml, avcstrm/AVCSTRM_ABORT_STREAMING, avcstrm/AVCSTRM_CLOSE, avcstrm/AVCSTRM_FUNCTION, avcstrm/AVCSTRM_GET_PROPERTY, avcstrm/AVCSTRM_GET_STATE, avcstrm/AVCSTRM_OPEN, avcstrm/AVCSTRM_READ, avcstrm/AVCSTRM_SET_PROPERTY, avcstrm/AVCSTRM_SET_STATE, avcstrm/AVCSTRM_WRITE, stream.avcstrm_function
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
req.typenames: AVCSTRM_FUNCTION
f1_keywords:
 - _AVCSTRM_FUNCTION
 - avcstrm/_AVCSTRM_FUNCTION
 - AVCSTRM_FUNCTION
 - avcstrm/AVCSTRM_FUNCTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avcstrm.h
api_name:
 - AVCSTRM_FUNCTION
---

# _AVCSTRM_FUNCTION enumeration


## -description

The AVCSTRM_FUNCTION enumeration defines the functionality exposed by the <i>avcstrm.sys</i> driver.

## -enum-fields

### -field AVCSTRM_READ

Read data from a stream.

### -field AVCSTRM_WRITE

Write data to a stream.

### -field AVCSTRM_ABORT_STREAMING

Abort streaming. This cancels <i>all</i> streaming IRPs. To cancel an individual IRP, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocancelirp">IoCancelIrp</a>.

### -field AVCSTRM_OPEN

Open a stream in a specific format.

### -field AVCSTRM_CLOSE

Close a stream and free any resources allocated for the stream.

### -field AVCSTRM_GET_STATE

Obtain the stream state.

### -field AVCSTRM_SET_STATE

Place the  stream into a new state.

### -field AVCSTRM_GET_PROPERTY

Get stream property. This function is not implemented.

### -field AVCSTRM_SET_PROPERTY

Set stream property. This function is not implemented.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-abort-streaming">AVCSTRM_ABORT_STREAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-close">AVCSTRM_CLOSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-get-property">AVCSTRM_GET_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-get-state">AVCSTRM_GET_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-open">AVCSTRM_OPEN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-read">AVCSTRM_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-set-property">AVCSTRM_SET_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-set-state">AVCSTRM_SET_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-write">AVCSTRM_WRITE</a>

