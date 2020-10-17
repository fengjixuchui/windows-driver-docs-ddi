---
UID: NF:wdm.CmRegisterCallbackEx
title: CmRegisterCallbackEx function (wdm.h)
description: The CmRegisterCallbackEx routine registers a RegistryCallback routine.
old-location: kernel\cmregistercallbackex.htm
tech.root: kernel
ms.assetid: 7ec7d9a4-3c6f-4b67-abbb-1e0dcbf6fb90
ms.date: 04/30/2018
keywords: ["CmRegisterCallbackEx function"]
ms.keywords: CmRegisterCallbackEx, CmRegisterCallbackEx routine [Kernel-Mode Driver Architecture], ConfigMgrRef_60ae8a2c-45c7-4b5e-ae19-916402b47903.xml, kernel.cmregistercallbackex, wdm/CmRegisterCallbackEx
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CmRegisterCallbackEx
 - wdm/CmRegisterCallbackEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CmRegisterCallbackEx
---

# CmRegisterCallbackEx function


## -description

The <b>CmRegisterCallbackEx</b> routine registers a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine.

## -parameters

### -param Function 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine to register.

### -param Altitude 

[in]
A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure. This structure must contain a string that represents the <a href="/windows-hardware/drivers/ifs/load-order-groups-and-altitudes-for-minifilter-drivers">altitude</a> of the calling <a href="/windows-hardware/drivers/ifs/file-system-minifilter-drivers">minifilter driver</a>. For more information, see Remarks.

### -param Driver 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure that represents the driver.

### -param Context 

[in, optional]
A driver-defined value that the configuration manager will pass as the <i>CallbackContext</i> parameter to the <i>RegistryCallback</i> routine.

### -param Cookie 

[out]
A pointer to a LARGE_INTEGER variable that receives the value that identifies the callback routine. When you unregister the callback routine, pass this value as the <i>Cookie</i> parameter to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a>.

### -param Reserved

This parameter is reserved for future use.

## -returns

<b>CmRegisterCallbackEx</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INSTANCE_ALTITUDE_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
The calling driver or another driver has already registered a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine for the specified altitude.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
An attempt to allocate memory failed.

</td>
</tr>
</table>

## -remarks

The <b>CmRegisterCallbackEx</b> routine is available starting with Windows Vista.

A driver can call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback">CmRegisterCallback</a> or <b>CmRegisterCallbackEx</b> to register a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine, which is called every time a thread performs an operation on the registry.

The <i>Altitude</i> parameter defines the  position of the minifilter driver relative to other minifilters in the I/O stack when the minifilter is loaded. Allocation of altitudes to minifilters is managed by Microsoft. For more information about altitudes, see <a href="/windows-hardware/drivers/ifs/load-order-groups-and-altitudes-for-minifilter-drivers">Load Order Groups and Altitudes for Minifilter Drivers</a>.

Call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a> to unregister a callback routine that <b>CmRegisterCallbackEx</b> registered.

For more information about <b>CmRegisterCallbackEx</b> and filtering registry operations, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback">CmRegisterCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>