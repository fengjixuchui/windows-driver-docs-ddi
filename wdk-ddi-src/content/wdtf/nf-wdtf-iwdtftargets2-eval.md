---
UID: NF:wdtf.IWDTFTargets2.Eval
title: IWDTFTargets2::Eval (wdtf.h)
description: Evaluates whether all items in the collection match an SDEL statement.
old-location: dtf\iwdtftargets2_eval.htm
tech.root: dtf
ms.assetid: 028a1fa9-686d-4f56-a49f-a7e90f960018
ms.date: 04/04/2018
keywords: ["IWDTFTargets2::Eval"]
ms.keywords: Eval, Eval method [Windows Device Testing Framework], Eval method [Windows Device Testing Framework],IWDTFTargets2 interface, IWDTFTargets2 interface [Windows Device Testing Framework],Eval method, IWDTFTargets2.Eval, IWDTFTargets2::Eval, Microsoft.WDTF.IWDTFTargets2.Eval, Microsoft::WDTF::IWDTFTargets2::Eval, dtf.iwdtftargets2_eval, wdtf/IWDTFTargets2::Eval
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
 - IWDTFTargets2::Eval
 - wdtf/IWDTFTargets2::Eval
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFTargets2.Eval
---

# IWDTFTargets2::Eval


## -description

Evaluates whether all items in the collection match an SDEL statement.

## -parameters

### -param SDEL 

[in]
The SDEL query string.

### -param pResult 

[out, retval]
True if all items match; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftargets2">IWDTFTargets2</a>

