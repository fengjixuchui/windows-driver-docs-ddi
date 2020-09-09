---
UID: NF:wdfrequest.WdfRequestGetRequestorProcessId
title: WdfRequestGetRequestorProcessId function (wdfrequest.h)
description: The WdfRequestGetRequestorProcessId method retrieves the identifier of the process that sent an I/O request.
old-location: wdf\wdfrequestgetrequestorprocessid.htm
tech.root: wdf
ms.assetid: F2CE35C8-F3BA-49E3-AE27-2FC5BFEC2D58
ms.date: 02/26/2018
keywords: ["WdfRequestGetRequestorProcessId function"]
ms.keywords: WdfRequestGetRequestorProcessId, WdfRequestGetRequestorProcessId method, wdf.wdfrequestgetrequestorprocessid, wdfrequest/WdfRequestGetRequestorProcessId
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.21
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestGetRequestorProcessId
 - wdfrequest/WdfRequestGetRequestorProcessId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WUDFx02000.dll
api_name:
 - WdfRequestGetRequestorProcessId
---

# WdfRequestGetRequestorProcessId function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestGetRequestorProcessId</b> method retrieves the identifier of the process that sent an I/O request.

## -parameters

### -param Request 

[in]
A handle to a framework request object.

## -returns

<b>WdfRequestGetRequestorProcessId</b> returns the identifier of the process that sent the I/O request.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffileobject/nf-wdffileobject-wdffileobjectgetinitiatorprocessid">WdfFileObjectGetInitiatorProcessId</a>

