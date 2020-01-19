---
UID: NF:ursdevice.UrsDeviceInitialize
title: UrsDeviceInitialize function (ursdevice.h)
description: Initializes a framework device object to support operations related to a USB dual-role controller and registers the relevant event callback functions with the USB dual-role controller class extension.
old-location: buses\ursdeviceinitialize.htm
tech.root: usbref
ms.assetid: 8A9C76C0-70F5-4F65-A460-CCFCD236A242
ms.date: 05/07/2018
ms.keywords: UrsDeviceInitialize, UrsDeviceInitialize function [Buses], buses.ursdeviceinitialize, ursdevice/UrsDeviceInitialize
ms.topic: function
f1_keywords:
 - "ursdevice/UrsDeviceInitialize"
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Urscxstub.lib
- Urscxstub.dll
api_name:
- UrsDeviceInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# UrsDeviceInitialize function


## -description


Initializes a framework device object to support operations related to  a USB dual-role controller and registers the relevant event callback functions with the USB dual-role controller class extension.


## -parameters




### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.


### -param Config [in]

 A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ursdevice/ns-ursdevice-_urs_config">URS_CONFIG</a> structure that the client driver initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-urs_config_init">URS_CONFIG_INIT</a>.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 




## -remarks



The client driver for the USB dual-role controller must call this method after the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> call. 

The client driver calls this method in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> implementation.

During this call, the client driver-supplied event callback implementations are also registered by setting appropriate members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ursdevice/ns-ursdevice-_urs_config">URS_CONFIG</a>. 

The method creates resource lists for host and function roles and the queues required to handle IOCTL requests that are sent to the controller. With each role switch operation, the current role's child device stack  is torn down and the device stack for the new role is loaded. The  <b>UrsDeviceInitialize</b> method retrieves identifying information that is used to build those device stacks. The method also retrieves information about the device from the underlying bus, such as ACPI.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>

EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS EvtUrsFilterResourceRequirements;
EVT_URS_SET_ROLE EvtUrsSetRole;

EvtDriverDeviceAdd (
    _In_ WDFDRIVER Driver,
    _Inout_ PWDFDEVICE_INIT DeviceInit
    )
{
...

    WDFDEVICE device;
    NTSTATUS status;
    WDF_OBJECT_ATTRIBUTES attributes;
    URS_CONFIG ursConfig;
...
 
    status = UrsDeviceInitInitialize(DeviceInit);
    if (!NT_SUCCESS(status)) {
        //UrsDeviceInitInitialize failed.
        return status;
    }
   
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, DRIVER_CONTEXT);
    status = WdfDeviceCreate(&DeviceInit, &attributes, &device);
    if (!NT_SUCCESS(status)) {
        // WdfDeviceCreate failed.
        return status;
    }
    URS_CONFIG_INIT(&ursConfig, UrsHostInterfaceTypeXhci, EvtUrsFilterResourceRequirements);
    
    ursConfig.EvtUrsSetRole = EvtUrsSetRole;
    status = UrsDeviceInitialize(device, &ursConfig);

    if (!NT_SUCCESS(status)) {
        // UrsDeviceInitialize failed.
        return status;

    }

...

}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ursdevice/ns-ursdevice-_urs_config">URS_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-urs_config_init">URS_CONFIG_INIT</a>
 

 

