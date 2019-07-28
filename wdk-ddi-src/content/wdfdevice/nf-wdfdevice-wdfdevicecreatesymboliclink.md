---
UID: NF:wdfdevice.WdfDeviceCreateSymbolicLink
title: WdfDeviceCreateSymbolicLink function (wdfdevice.h)
description: The WdfDeviceCreateSymbolicLink method creates a symbolic link to a specified device.
old-location: wdf\wdfdevicecreatesymboliclink.htm
tech.root: wdf
ms.assetid: c22035a2-8ceb-42e9-9d54-8997ce0dd8da
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_f970bbdf-21d6-497c-abc1-84456c95dc79.xml, WdfDeviceCreateSymbolicLink, WdfDeviceCreateSymbolicLink method, kmdf.wdfdevicecreatesymboliclink, wdf.wdfdevicecreatesymboliclink, wdfdevice/WdfDeviceCreateSymbolicLink
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceCreateSymbolicLink"
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
- WdfDeviceCreateSymbolicLink
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceCreateSymbolicLink function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceCreateSymbolicLink</b> method creates a symbolic link to a specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param SymbolicLinkName [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a user-visible name for the device.


## -returns



If the operation succeeds, the <b>WdfDeviceCreateSymbolicLink</b> returns STATUS_SUCCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The system cannot allocate space to store the device name.

</td>
</tr>
</table>
 

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



If a driver creates a symbolic link for a device, applications can use the symbolic link name to access the device. Typically, instead of providing symbolic links, framework-based drivers provide <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces">device interfaces</a> that applications can use to access their devices.

If the device is removed unexpectedly (surprise-removed), the framework removes the symbolic link to the device. The driver can then use the symbolic link name for a new instance of the device.


#### Examples

The following code example from a KMDF driver creates an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ms-dos-device-names">MS-DOS device name</a> that an application can use to access a device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define DOS_DEVICE_NAME  L"\\DosDevices\\MyDevice"
DECLARE_CONST_UNICODE_STRING(dosDeviceName, DOS_DEVICE_NAME);
NTSTATUS  status;

status = WdfDeviceCreateSymbolicLink(
                                     controlDevice,
                                     &dosDeviceName
                                     );
if (!NT_SUCCESS(status)) {
    goto Error;
}</pre>
</td>
</tr>
</table></span></div>
A UMDF driver must provide a symbolic link name in the global <b>DosDevices</b> namespace, as the following code example illustrates.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define DOS_DEVICE_NAME  L"\\DosDevices\\Global\\MyDevice"
DECLARE_CONST_UNICODE_STRING(dosDeviceName, DOS_DEVICE_NAME);
NTSTATUS  status;

status = WdfDeviceCreateSymbolicLink(
                                     controlDevice,
                                     &dosDeviceName
                                     );
if (!NT_SUCCESS(status)) {
    goto Error;
}</pre>
</td>
</tr>
</table></span></div>
For information about global and local <b>\DosDevices</b> namespaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/local-and-global-ms-dos-device-names">Local and Global MS-DOS Device Names</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

