---
UID: NF:wdfwmi.WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER
title: WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER function (wdfwmi.h)
description: The WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER function initializes a WDF_WMI_INSTANCE_CONFIG structure and stores a specified handle to a WMI provider object.
old-location: wdf\wdf_wmi_instance_config_init_provider.htm
tech.root: wdf
ms.assetid: 6509fded-c244-4d86-9b20-23790ec58f4a
ms.date: 02/26/2018
ms.keywords: DFWMIRef_beb80d61-7fcb-4234-97ef-41e917cd51f5.xml, WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER, WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER function, kmdf.wdf_wmi_instance_config_init_provider, wdf.wdf_wmi_instance_config_init_provider, wdfwmi/WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER
ms.topic: function
f1_keywords:
 - "wdfwmi/WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER"
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
- HeaderDef
api_location:
- wdfwmi.h
api_name:
- WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure and stores a specified handle to a WMI provider object.


## -parameters




### -param Config [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure.


### -param Provider [in]

A handle to a WMI provider object that the driver obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>.


## -remarks



The <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</b> function zeros the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure that the <i>Config</i> parameter specifies and sets its <b>Size</b> member. This function also sets the structure's <b>Provider</b> member to the handle that the <i>Provider</i> parameter specifies.

Your driver should call <b>WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER</b> to initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure if it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a> structure and calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>. Then, the example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure and calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>.

```cpp
WDF_WMI_PROVIDER_CONFIG  providerConfig;
WDFWMIPROVIDER  provider;
GUID  providerGuid = MY_WMI_DATA_BLOCK_GUID;
WDF_WMI_INSTANCE_CONFIG  instanceConfig;
WDFWMIINSTANCE  instanceHandle;
NTSTATUS  status;

WDF_WMI_PROVIDER_CONFIG_INIT(
                             &providerConfig,
                             providerGuid
                             );
providerConfig.Flags = WdfWmiProviderTracing;
providerConfig.EvtWmiProviderFunctionControl = MyProviderFunctionControl;

status = WdfWmiProviderCreate(
                              Device,
                              &providerConfig,
                              WDF_NO_OBJECT_ATTRIBUTES,
                              &provider
                              );

if (!NT_SUCCESS(status)) {
    return status;
}
WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER(
                                      &instanceConfig,
                                      provider
                                      );
status = WdfWmiInstanceCreate(
                              Device,
                              &instanceConfig,
                              WDF_NO_OBJECT_ATTRIBUTES,
                              &instanceHandle
                              );
if (!NT_SUCCESS(status)) {
    return status;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdf_wmi_instance_config_init_provider_config">WDF_WMI_INSTANCE_CONFIG_INIT_PROVIDER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_provider_config">WDF_WMI_PROVIDER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdf_wmi_provider_config_init">WDF_WMI_PROVIDER_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>
 

 

