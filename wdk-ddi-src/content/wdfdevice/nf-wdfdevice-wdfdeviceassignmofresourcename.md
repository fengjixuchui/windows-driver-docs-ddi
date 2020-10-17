---
UID: NF:wdfdevice.WdfDeviceAssignMofResourceName
title: WdfDeviceAssignMofResourceName function (wdfdevice.h)
description: The WdfDeviceAssignMofResourceName method registers a MOF resource name for a specified device.
old-location: wdf\wdfdeviceassignmofresourcename.htm
tech.root: wdf
ms.assetid: b4ab0a7b-9c5a-4295-94fc-35310ca8e05b
ms.date: 02/26/2018
keywords: ["WdfDeviceAssignMofResourceName function"]
ms.keywords: DFDeviceObjectGeneralRef_8cdcec0f-02df-4e8d-83e2-ae1fdc11343d.xml, WdfDeviceAssignMofResourceName, WdfDeviceAssignMofResourceName method, kmdf.wdfdeviceassignmofresourcename, wdf.wdfdeviceassignmofresourcename, wdfdevice/WdfDeviceAssignMofResourceName
req.header: wdfdevice.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceAssignMofResourceName
 - wdfdevice/WdfDeviceAssignMofResourceName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceAssignMofResourceName
---

# WdfDeviceAssignMofResourceName function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceAssignMofResourceName</b> method registers a MOF resource name for a specified device.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param MofResourceName 

[in]
A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that specifies the name of a MOF resource.

## -returns

If the operation succeeds, <b>WdfDeviceAssignMofResourceName</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The driver has already called <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassignmofresourcename">WdfDeviceAssignMofResourceName</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
 Insufficient memory is available.

</td>
</tr>
</table>
 

The method might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

A driver that provides a MOF file to support WMI must call <b>WdfDeviceAssignMofResourceName</b>, typically from within its <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> or <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function. The MOF resource name is the file name that the driver specifies in a <b>MofResource</b> statement in its resource script (RC) file. For more information about specifying a MOF resource name, see <a href="/windows-hardware/drivers/kernel/compiling-a-driver-s-mof-file">Compiling a Driver's MOF File</a>.

A driver that <a href="/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">enumerates the devices on a bus</a> can call <b>WdfDeviceAssignMofResourceName</b> for the parent device, and the framework will use the parent's MOF resource name for child devices.

For more information about WMI, see <a href="/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


#### Examples

The following code example declares a Unicode string that represents a MOF resource name and then registers the name.

```cpp
NTSTATUS  status;
DECLARE_CONST_UNICODE_STRING(mofRsrcName, MOFRESOURCENAME);

status = WdfDeviceAssignMofResourceName(
                                        Device,
                                        &mofRsrcName
                                        );
if (!NT_SUCCESS(status)) {
    return status;
}
```