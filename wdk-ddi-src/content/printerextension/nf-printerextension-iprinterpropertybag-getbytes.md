---
UID: NF:printerextension.IPrinterPropertyBag.GetBytes
title: IPrinterPropertyBag::GetBytes (printerextension.h)
description: Reads a byte array property.
old-location: print\iprinterpropertybag_getbytes.htm
tech.root: print
ms.assetid: F75E182D-90FA-4597-95E0-60A6326CF68D
ms.date: 04/20/2018
keywords: ["IPrinterPropertyBag::GetBytes"]
ms.keywords: GetBytes, GetBytes method [Print Devices], GetBytes method [Print Devices],IPrinterPropertyBag interface, IPrinterPropertyBag interface [Print Devices],GetBytes method, IPrinterPropertyBag.GetBytes, IPrinterPropertyBag::GetBytes, print.iprinterpropertybag_getbytes, printerextension/IPrinterPropertyBag::GetBytes
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrinterPropertyBag::GetBytes
 - printerextension/IPrinterPropertyBag::GetBytes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterPropertyBag.GetBytes
---

# IPrinterPropertyBag::GetBytes


## -description

Reads a byte array property.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterpropertybag">IPrinterPropertyBag</a> interface is used by all the printer property bags, including driver property bag, user property bag, queue property bag, and DEVMODE property bag.

## -parameters

### -param bstrName 

[in]
The property to read.

### -param pcbValue 

[out]
The number of bytes read.

### -param ppValue

#### - rgbValue [out]

The returned array. This array must be freed by using CoTaskFree.

## -returns

This method returns an <b>HRESULT</b> value.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterpropertybag">IPrinterPropertyBag</a>

