---
UID: NC:wdfwmi.EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE
title: EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE (wdfwmi.h)
description: A driver's EvtWmiInstanceQueryInstance callback function copies a WMI provider's instance data into a buffer for delivery to a WMI client.
old-location: wdf\evtwmiinstancequeryinstance.htm
tech.root: wdf
ms.assetid: 13eed838-2943-4bb4-915f-6a84f0f95851
ms.date: 02/26/2018
keywords: ["EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE callback function"]
ms.keywords: DFWMIRef_424a0070-8839-4d3f-b285-166b23ac03f7.xml, EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE, EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE callback, EvtWmiInstanceQueryInstance, EvtWmiInstanceQueryInstance callback function, kmdf.evtwmiinstancequeryinstance, wdf.evtwmiinstancequeryinstance, wdfwmi/EvtWmiInstanceQueryInstance
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE
 - wdfwmi/EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfWMI.h
api_name:
 - EvtWmiInstanceQueryInstance
---

# EVT_WDF_WMI_INSTANCE_QUERY_INSTANCE callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtWmiInstanceQueryInstance</i> callback function copies a WMI provider's instance data into a buffer for delivery to a WMI client.

## -parameters

### -param WmiInstance 

[in]
A handle to a WMI instance object.

### -param OutBufferSize 

[in]
The size, in bytes, of the output buffer that <i>OutBuffer</i> points to.

### -param OutBuffer 

[in]
A pointer to the output buffer.

### -param BufferUsed 

[out]
A pointer to a location that receives the number of bytes that the driver places in the output buffer. If the output buffer size that the <i>OutBufferSize</i> parameter specifies is too small, the driver sets this location to the required buffer size.

## -returns

The <i>EvtWmiInstanceQueryInstance</i> callback function must return STATUS_BUFFER_TOO_SMALL, if the value of the <i>OutBufferSize</i> parameter indicates that the output buffer is too small to receive the data. Otherwise, the callback function must copy data into the buffer and return STATUS_SUCCESS.

## -remarks

To register an <i>EvtWmiInstanceQueryInstance</i> callback function, your driver must place the function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>. 

Before the framework sends the driver-supplied instance data to the WMI client, it adds all of the necessary WMI header information to the data.

If your driver sets the <b>UseContextForQuery</b> member of the WMI instance object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a> structure to <b>TRUE</b> for a read-only data block, the driver does not provide an <i>EvtWmiInstanceQueryInstance</i> callback function.

If your driver must provide string data to a WMI client, the driver should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdf_wmi_buffer_append_string">WDF_WMI_BUFFER_APPEND_STRING</a> function to format the string.

For more information about the <i>EvtWmiInstanceQueryInstance</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-data-blocks-and-events-in-your-driver">Supporting Read/Write WMI Data Blocks</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-data-blocks-and-events-in-your-driver">Supporting Read-Only WMI Data Blocks</a>. 

The framework does not synchronize calls to a driver's WMI event callback functions with each other or with any of the driver's other event callback functions. If an <i>EvtWmiInstanceQueryInstance</i> callback function's data is dynamic and shared with other callback functions, your driver can use the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-locks">wait locks or spin locks</a> to synchronize access to the data.

For more information about WMI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_execute_method">EvtWmiInstanceExecuteMethod</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_set_instance">EvtWmiInstanceSetInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_set_item">EvtWmiInstanceSetItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_provider_function_control">EvtWmiProviderFunctionControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdf_wmi_buffer_append_string">WDF_WMI_BUFFER_APPEND_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/ns-wdfwmi-_wdf_wmi_instance_config">WDF_WMI_INSTANCE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>

