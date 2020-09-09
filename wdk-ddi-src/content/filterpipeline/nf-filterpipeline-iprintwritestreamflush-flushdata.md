---
UID: NF:filterpipeline.IPrintWriteStreamFlush.FlushData
title: IPrintWriteStreamFlush::FlushData (filterpipeline.h)
description: The FlushData method flushes buffered data to a data stream while leaving the stream open, allowing the caller to write additional data to the stream.
old-location: print\iprintwritestreamflush_flushdata.htm
tech.root: print
ms.assetid: F0E31AA1-47BD-4294-89BA-27B02FC8125B
ms.date: 04/20/2018
keywords: ["IPrintWriteStreamFlush::FlushData"]
ms.keywords: FlushData, FlushData method [Print Devices], FlushData method [Print Devices],IPrintWriteStreamFlush interface, IPrintWriteStreamFlush interface [Print Devices],FlushData method, IPrintWriteStreamFlush.FlushData, IPrintWriteStreamFlush::FlushData, filterpipeline/IPrintWriteStreamFlush::FlushData, print.iprintwritestreamflush_flushdata
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - IPrintWriteStreamFlush::FlushData
 - filterpipeline/IPrintWriteStreamFlush::FlushData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPrintWriteStreamFlush.FlushData
---

# IPrintWriteStreamFlush::FlushData


## -description

The FlushData method flushes buffered data to a data stream while leaving the stream open, allowing the caller to write additional data to the stream. Writing to the stream is done using the [IPrintWriteStream::WriteBytes](https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintwritestream-writebytes) method.

## -returns

The FlushData method returns an HRESULT value.

## -remarks

Only the last filter in the print filter pipeline benefits from the flush. The data is flushed to the port monitor. However, the port monitor has the option of using  buffers.

### Examples

The following code snippet shows how to flush data to a data stream. Note that error checking has been omitted for clarity.

```cpp
// Flushing data to a data stream
// ------------------------------
// Declare a pointer to an IPrintWriteStreamFlush interface
IPrintWriteStreamFlush *pIFlush;

// Retireve a pointer to an IPrintWriteStream interface
// by using the RequestWriter() method in InitializeFilter()
IPrintWriteStream      *pIWrite;

HRESULT hr = pIWrite->QueryInterface(IID_IPrintWriteStreamFlush, reinterpret_cast<void **>(&pIFlush));

hr = pIWrite->WriteBytes(buf, cb, &cbWritten);

hr = pIFlush->FlushData();
```

## -see-also

[IPrintWriteStream::WriteBytes](https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintwritestream-writebytes)

[IPrintWriteStreamFlush](https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintwritestreamflush)

