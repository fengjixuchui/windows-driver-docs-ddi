---
UID: NF:wdfdriver.WdfDriverCreate
title: WdfDriverCreate function (wdfdriver.h)
description: The WdfDriverCreate method creates a framework driver object for the calling driver.
old-location: wdf\wdfdrivercreate.htm
tech.root: wdf
ms.assetid: 2b8cea0f-bca0-4ffa-834b-d7c079cf93d8
ms.date: 02/26/2018
keywords: ["WdfDriverCreate function"]
ms.keywords: DFDriverObjectRef_10e33793-b3e1-4938-9b82-439451aceb86.xml, WdfDriverCreate, WdfDriverCreate method, kmdf.wdfdrivercreate, wdf.wdfdrivercreate, wdfdriver/WdfDriverCreate
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChangeQueueState, DriverAttributeChanged, DriverCreate, KmdfIrql, KmdfIrql2, MiniportOnlyWdmDevice
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDriverCreate
 - wdfdriver/WdfDriverCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfDriverCreate
---

# WdfDriverCreate function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDriverCreate</b> method creates a framework driver object for the calling driver.

## -parameters

### -param DriverObject 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure that represents a Windows Driver Model (WDM) driver object. The driver receives this pointer as input to its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine.

### -param RegistryPath 

[in]
A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the registry path string that the driver received as input to its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine.

### -param DriverAttributes 

[in, optional]
A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param DriverConfig 

[in]
A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_config">WDF_DRIVER_CONFIG</a> structure.

### -param Driver 

[out, optional]
A pointer to a location that receives a handle to the new framework driver object. This parameter is optional and can be WDF_NO_HANDLE.

## -returns

<b>WdfDriverCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DRIVER_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The driver called <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> more than once.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A <a href="/windows-hardware/drivers/wdf/using-kernel-mode-driver-framework-with-non-pnp-drivers">non-Plug and Play (PnP) driver</a> specified an <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

</td>
</tr>
</table>
 

For more information about return values, see <a href="/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method might also return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A system bug check occurs if the <i>DriverObject</i>, <i>RegistryPath</i>, or <i>DriverConfig</i> parameter is <b>NULL</b>.

## -remarks

A driver that uses Kernel-Mode Driver Framework must call <b>WdfDriverCreate</b> from within its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine, before calling any other framework routines. For more information about <b>DriverEntry</b>, see <b>DriverEntry for Framework-based Drivers</b>. 

Before your driver calls <b>WdfDriverCreate</b>, the driver must call <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdf_driver_config_init">WDF_DRIVER_CONFIG_INIT</a> to initialize its <a href="/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_config">WDF_DRIVER_CONFIG</a> structure.

The framework driver object is the top of your driver's tree of framework objects and therefore does not have a parent object.

If your driver provides <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback functions for the driver object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.


#### Examples

The following code example is a <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine that initializes a WDF_DRIVER_CONFIG structure and then creates a framework driver object.

```cpp
NTSTATUS
DriverEntry(
    IN PDRIVER_OBJECT  DriverObject,
    IN PUNICODE_STRING  RegistryPath
    )
{
    WDF_DRIVER_CONFIG  config;
    NTSTATUS  status = STATUS_SUCCESS;

    WDF_DRIVER_CONFIG_INIT(
                           &config,
                           MyEvtDeviceAdd
                           );
    config.EvtDriverUnload = MyEvtDriverUnload;
    status = WdfDriverCreate(
                             DriverObject,
                             RegistryPath,
                             WDF_NO_OBJECT_ATTRIBUTES,
                              &config,
                             WDF_NO_HANDLE
                             );
    if (!NT_SUCCESS(status)) {
        TraceEvents(
                    TRACE_LEVEL_ERROR,
                    DBG_PNP,
                    "WdfDriverCreate failed with status %!STATUS!",
                    status
                    );
    }
    return status;
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_config">WDF_DRIVER_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdf_driver_config_init">WDF_DRIVER_CONFIG_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>