---
UID: NF:wdtf.IWDTFCONFIG2.EnableObjectErrorLogging
title: IWDTFCONFIG2::EnableObjectErrorLogging (wdtf.h)
description: Enables object error logging for all objects.
old-location: dtf\iwdtfconfig2_enableobjecterrorlogging.htm
tech.root: dtf
ms.assetid: 10e7abc9-addd-4f0e-b77b-af9e8e1fa061
ms.date: 04/04/2018
keywords: ["IWDTFCONFIG2::EnableObjectErrorLogging"]
ms.keywords: EnableObjectErrorLogging, EnableObjectErrorLogging method [Windows Device Testing Framework], EnableObjectErrorLogging method [Windows Device Testing Framework],IWDTFCONFIG2 interface, IWDTFCONFIG2 interface [Windows Device Testing Framework],EnableObjectErrorLogging method, IWDTFCONFIG2.EnableObjectErrorLogging, IWDTFCONFIG2::EnableObjectErrorLogging, Microsoft.WDTF.IWDTFCONFIG2.EnableObjectErrorLogging, Microsoft::WDTF::IWDTFCONFIG2::EnableObjectErrorLogging, dtf.iwdtfconfig2_enableobjecterrorlogging, wdtf/IWDTFCONFIG2::EnableObjectErrorLogging
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
 - IWDTFCONFIG2::EnableObjectErrorLogging
 - wdtf/IWDTFCONFIG2::EnableObjectErrorLogging
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFCONFIG2.EnableObjectErrorLogging
---

# IWDTFCONFIG2::EnableObjectErrorLogging


## -description

Enables object error logging for all objects.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

If object logging is enabled, object error logging is enabled by default. Otherwise, error
logging defaults to disabled.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtfconfig2">IWDTFCONFIG2</a>