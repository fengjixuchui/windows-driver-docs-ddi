---
UID: NF:printerextension.IPrinterPropertyBag.GetReadStream
title: IPrinterPropertyBag::GetReadStream (printerextension.h)
description: Gets a stream in order to read from a stream property.
old-location: print\iprinterpropertybag_getreadstream.htm
tech.root: print
ms.assetid: BDA58F6A-A245-4616-866C-6D1734EFB469
ms.date: 04/20/2018
ms.keywords: GetReadStream, GetReadStream method [Print Devices], GetReadStream method [Print Devices],IPrinterPropertyBag interface, IPrinterPropertyBag interface [Print Devices],GetReadStream method, IPrinterPropertyBag.GetReadStream, IPrinterPropertyBag::GetReadStream, print.iprinterpropertybag_getreadstream, printerextension/IPrinterPropertyBag::GetReadStream
ms.topic: method
f1_keywords:
 - "printerextension/IPrinterPropertyBag.GetReadStream"
req.header: printerextension.h
req.include-header: Printerextension.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrinterPropertyBag.GetReadStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterPropertyBag::GetReadStream


## -description


Gets a stream in order to read from a stream property.


## -parameters




### -param bstrName [in]

The property to read.


### -param ppValue






#### - ppValueStream [out]

The returned stream.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



This method does not work with non-stream properties.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterpropertybag">IPrinterPropertyBag</a>
 

 

