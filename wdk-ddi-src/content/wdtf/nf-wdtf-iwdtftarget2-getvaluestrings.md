---
UID: NF:wdtf.IWDTFTarget2.GetValueStrings
title: IWDTFTarget2::GetValueStrings (wdtf.h)
description: Returns a collection of string values from the target that are associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluestrings.htm
tech.root: dtf
ms.assetid: 2bc18baa-77e0-4ce1-85d9-55817333ecaa
ms.date: 04/04/2018
keywords: ["IWDTFTarget2::GetValueStrings"]
ms.keywords: GetValueStrings, GetValueStrings method [Windows Device Testing Framework], GetValueStrings method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],GetValueStrings method, IWDTFTarget2.GetValueStrings, IWDTFTarget2::GetValueStrings, Microsoft.WDTF.IWDTFTarget2.GetValueStrings, Microsoft::WDTF::IWDTFTarget2::GetValueStrings, dtf.iwdtftarget2_getvaluestrings, wdtf/IWDTFTarget2::GetValueStrings
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFTarget2::GetValueStrings
 - wdtf/IWDTFTarget2::GetValueStrings
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFTarget2.GetValueStrings
---

# IWDTFTarget2::GetValueStrings


## -description

Returns a collection of string values from the target that are associated 
with a specified attribute.

## -parameters

### -param SDEL 

[in]
An SDEL statement that specifies the attribute value to retrieve.

### -param ppValues 

[out, retval]
The address of a variable that receives the result of this method.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

You specify the field that the<b> GetValueStrings</b> method retrieves 
by using a regular <a href="https://docs.microsoft.com/windows-hardware/drivers/wdtf/simple-data-evaluation-language-overview">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueStrings</b> 
to work properly.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>

