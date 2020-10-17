---
UID: NF:wdfdevice.WdfDeviceRemoveDependentUsageDeviceObject
title: WdfDeviceRemoveDependentUsageDeviceObject function (wdfdevice.h)
description: The WdfDeviceRemoveDependentUsageDeviceObject method indicates that a specified device no longer depends on another device when the specified device is used to store special files.
old-location: wdf\wdfdeviceremovedependentusagedeviceobject.htm
tech.root: wdf
ms.assetid: d9569b4b-ad71-46dd-b421-8493f595f030
ms.date: 02/26/2018
keywords: ["WdfDeviceRemoveDependentUsageDeviceObject function"]
ms.keywords: DFDeviceObjectGeneralRef_22cf19f5-c56f-430f-a6a1-d15af92eb41b.xml, WdfDeviceRemoveDependentUsageDeviceObject, WdfDeviceRemoveDependentUsageDeviceObject method, kmdf.wdfdeviceremovedependentusagedeviceobject, wdf.wdfdeviceremovedependentusagedeviceobject, wdfdevice/WdfDeviceRemoveDependentUsageDeviceObject
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
 - WdfDeviceRemoveDependentUsageDeviceObject
 - wdfdevice/WdfDeviceRemoveDependentUsageDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceRemoveDependentUsageDeviceObject
---

# WdfDeviceRemoveDependentUsageDeviceObject function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceRemoveDependentUsageDeviceObject</b> method indicates that a specified device no longer depends on another device when the specified device is used to store <a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_special_file_type">special files</a>.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param DependentDevice 

[in]
A pointer to a caller-supplied <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that identifies a device that <i>Device</i> depends on.

## -remarks

Your driver can call <b>WdfDeviceRemoveDependentUsageDeviceObject</b> to remove a device dependency that a previous call to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceadddependentusagedeviceobject">WdfDeviceAddDependentUsageDeviceObject</a> created.

For more information about <b>WdfDeviceRemoveDependentUsageDeviceObject</b> and <b>WdfDeviceRemoveDependentUsageDeviceObject</b>, see <a href="/windows-hardware/drivers/wdf/supporting-special-files">Supporting Special Files</a>. 


#### Examples

The following code example removes a device (<b>pDeviceObject</b>) from the list of devices that another device (<b>device</b>) depends on.

```cpp
status = WdfDeviceRemoveDependentUsageDeviceObject(
                                                device,
                                                pDeviceObject
                                                );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceadddependentusagedeviceobject">WdfDeviceAddDependentUsageDeviceObject</a>