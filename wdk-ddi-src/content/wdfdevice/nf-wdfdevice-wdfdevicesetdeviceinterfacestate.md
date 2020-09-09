---
UID: NF:wdfdevice.WdfDeviceSetDeviceInterfaceState
title: WdfDeviceSetDeviceInterfaceState function (wdfdevice.h)
description: The WdfDeviceSetDeviceInterfaceState method enables or disables a device interface for a specified device.
old-location: wdf\wdfdevicesetdeviceinterfacestate.htm
tech.root: wdf
ms.assetid: 345003fc-fdc3-4529-bb15-c9e380e77bba
ms.date: 03/24/2020
keywords: ["WdfDeviceSetDeviceInterfaceState function"]
ms.keywords: DFDeviceObjectGeneralRef_bfed99aa-ad4c-4339-aeb9-f7d73039f0b9.xml, WdfDeviceSetDeviceInterfaceState, WdfDeviceSetDeviceInterfaceState method, kmdf.wdfdevicesetdeviceinterfacestate, wdf.wdfdevicesetdeviceinterfacestate, wdfdevice/WdfDeviceSetDeviceInterfaceState
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
 - WdfDeviceSetDeviceInterfaceState
 - wdfdevice/WdfDeviceSetDeviceInterfaceState
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
 - WdfDeviceSetDeviceInterfaceState
---

# WdfDeviceSetDeviceInterfaceState function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceSetDeviceInterfaceState</b> method enables or disables a device interface for a specified device.

> [!NOTE]
> The driver should only call this function after the device has started. To change interface state from device add, call [**WdfDeviceSetDeviceInterfaceStateEx**](/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetdeviceinterfacestateex) instead.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param InterfaceClassGUID 

[in]
A pointer to a GUID that identifies the device interface class.

### -param ReferenceString 

[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that describes a reference string for the device interface. This parameter is optional and can be <b>NULL</b>.

### -param IsInterfaceEnabled 

[in]
A Boolean value that, if <b>TRUE</b>, enables the specified device interface instance or, if <b>FALSE</b>, disables it.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




For more information about device interfaces and the <b>WdfDeviceSetDeviceInterfaceState</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces">Using Device Interfaces</a>.


#### Examples

The following code example disables a driver's COM port interface.

```cpp
WdfDeviceSetDeviceInterfaceState (
                                  Device,
                                  (LPGUID) &GUID_DEVINTERFACE_COMPORT,
                                  NULL,
                                  FALSE
                                  );
```

## -see-also

<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreatedeviceinterface">WdfDeviceCreateDeviceInterface</a>
 
[**WdfDeviceSetDeviceInterfaceStateEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetdeviceinterfacestateex)

