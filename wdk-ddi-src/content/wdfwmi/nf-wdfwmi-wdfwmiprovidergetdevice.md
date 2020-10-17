---
UID: NF:wdfwmi.WdfWmiProviderGetDevice
title: WdfWmiProviderGetDevice function (wdfwmi.h)
description: The WdfWmiProviderGetDevice method returns a handle to the framework device object that is the parent of a specified WMI provider object.
old-location: wdf\wdfwmiprovidergetdevice.htm
tech.root: wdf
ms.assetid: 8d934e44-c6f9-42f7-81a6-202b6c97aca2
ms.date: 02/26/2018
keywords: ["WdfWmiProviderGetDevice function"]
ms.keywords: DFWMIRef_697647f5-0ece-46e4-8973-07088c8c3739.xml, WdfWmiProviderGetDevice, WdfWmiProviderGetDevice method, kmdf.wdfwmiprovidergetdevice, wdf.wdfwmiprovidergetdevice, wdfwmi/WdfWmiProviderGetDevice
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfWmiProviderGetDevice
 - wdfwmi/WdfWmiProviderGetDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfWmiProviderGetDevice
---

# WdfWmiProviderGetDevice function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfWmiProviderGetDevice</b> method returns a handle to the framework device object that is the parent of a specified WMI provider object.

## -parameters

### -param WmiProvider 

[in]
A handle to a WMI provider object that the driver obtained by calling <a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a> or <a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancegetprovider">WdfWmiInstanceGetProvider</a>.

## -returns

<b>WdfWmiProviderGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancegetprovider">WdfWmiInstanceGetProvider</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>