---
UID: NF:wdfwmi.WdfWmiProviderGetTracingHandle
title: WdfWmiProviderGetTracingHandle function (wdfwmi.h)
description: The WdfWmiProviderGetTracingHandle method returns a handle to the event logger of a WPP software tracing session.
old-location: wdf\wdfwmiprovidergettracinghandle.htm
tech.root: wdf
ms.assetid: 44ab1cf3-abd3-4100-a6ad-51f2322881b1
ms.date: 02/26/2018
keywords: ["WdfWmiProviderGetTracingHandle function"]
ms.keywords: DFWMIRef_eea0d3ab-8fb8-4053-8260-e5c396a06524.xml, WdfWmiProviderGetTracingHandle, WdfWmiProviderGetTracingHandle method, kmdf.wdfwmiprovidergettracinghandle, wdf.wdfwmiprovidergettracinghandle, wdfwmi/WdfWmiProviderGetTracingHandle
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
 - WdfWmiProviderGetTracingHandle
 - wdfwmi/WdfWmiProviderGetTracingHandle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfWmiProviderGetTracingHandle
---

# WdfWmiProviderGetTracingHandle function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfWmiProviderGetTracingHandle</b> method returns a handle to the event logger of a <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/wpp-software-tracing">WPP software tracing</a> session.

## -parameters

### -param WmiProvider 

[in]
A handle to a WMI provider object that the driver obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancegetprovider">WdfWmiInstanceGetProvider</a>.

## -returns

<b>WdfWmiProviderGetTracingHandle</b> returns a handle to the event tracing logger.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

If a driver sets the <b>WdfWmiProviderTracing</b> flag in the <b>Flags</b> member of the WMI provider object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a> structure, it can call <b>WdfWmiProviderGetTracingHandle</b> to obtain a tracing handle after a provider instance has been registered. The driver can use the tracing handle as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-wmitracemessage">WmiTraceMessage</a> routine.

For more information about the <b>WdfWmiProviderGetTracingHandle</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-data-blocks-and-events-in-your-driver">Supporting WMI Event Tracing</a>. For more information about WMI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

The following code example obtains a handle to a WPP tracing session's event logger.

```cpp
ULONGLONG tracingHandle;

tracingHandle = WdfWmiProviderGetTracingHandle(wmiProvider);
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancegetprovider">WdfWmiInstanceGetProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>

