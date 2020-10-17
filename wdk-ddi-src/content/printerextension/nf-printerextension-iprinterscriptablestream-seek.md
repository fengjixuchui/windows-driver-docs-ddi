---
UID: NF:printerextension.IPrinterScriptableStream.Seek
title: IPrinterScriptableStream::Seek (printerextension.h)
description: Sets the seek pointer.
old-location: print\iprinterscriptablestream__seek.htm
tech.root: print
ms.assetid: 82080353-2252-4BF2-B7F4-F297DCA99FA0
ms.date: 04/20/2018
keywords: ["IPrinterScriptableStream::Seek"]
ms.keywords: IPrinterScriptableStream interface [Print Devices],Seek method, IPrinterScriptableStream.Seek, IPrinterScriptableStream::Seek, Seek, Seek method [Print Devices], Seek method [Print Devices],IPrinterScriptableStream interface, print.iprinterscriptablestream__seek, printerextension/IPrinterScriptableStream::Seek
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - IPrinterScriptableStream::Seek
 - printerextension/IPrinterScriptableStream::Seek
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptableStream.Seek
---

# IPrinterScriptableStream::Seek


## -description

Sets the seek pointer.

## -parameters

### -param lOffset 

[in]
The displacement to be added to the location indicated by the <i>streamSeek</i> parameter.

### -param streamSeek 

[in]
The origin for the displacement specified <i>lOffset</i>.

### -param plPosition 

[out, retval]
The new pointer position.

## -returns

This method returns an <b>HRESULT</b> value.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablestream">IPrinterScriptableStream</a>