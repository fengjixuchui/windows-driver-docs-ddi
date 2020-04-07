---
UID: NF:wdfregistry.WdfRegistryQueryValue
title: WdfRegistryQueryValue function (wdfregistry.h)
description: The WdfRegistryQueryValue method retrieves the data that is currently assigned to a specified registry value.
old-location: wdf\wdfregistryqueryvalue.htm
tech.root: wdf
ms.assetid: 1d61e35a-64c6-42e0-b20d-969ded8b9750
ms.date: 02/26/2018
keywords: ["WdfRegistryQueryValue function"]
ms.keywords: DFRegKeyObjectRef_703acb47-ac90-4715-a290-122d4ee3449e.xml, WdfRegistryQueryValue, WdfRegistryQueryValue method, kmdf.wdfregistryqueryvalue, wdf.wdfregistryqueryvalue, wdfregistry/WdfRegistryQueryValue
f1_keywords:
 - "wdfregistry/WdfRegistryQueryValue"
req.header: wdfregistry.h
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
- WdfRegistryQueryValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRegistryQueryValue function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryQueryValue</b> method retrieves the data that is currently assigned to a specified registry value.


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a value name. 


### -param ValueLength [in]

The length, in bytes, of the buffer that <i>Value</i> points to.


### -param Value [out, optional]

A pointer to a driver-allocated buffer that receives the registry value's data. If this pointer is <b>NULL</b>, <b>WdfRegistryQueryValue</b> retrieves the data length but not the data.


### -param ValueLengthQueried [out, optional]

A pointer to a location that receives the registry value's data length. This pointer is optional and can be <b>NULL</b>.


### -param ValueType [out, optional]

A pointer to a location that receives the registry value's data type. For a list of data type values, see the <b>Type</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>. This pointer is optional and can be <b>NULL</b>.


## -returns



<b>WdfRegistryQueryValue</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryqueryvalue">WdfRegistryQueryValue</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver did not open the registry key with KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS access.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>Value</i> parameter points to is too small, and only partial data has been written to the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The <i>Value</i> buffer is too small, and no data has been written to the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The registry value was not available.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example opens a device's hardware key and retrieves the data that is assigned to the <b>NumberOfToasters</b> value, which is stored under the device's hardware key.

```cpp
WCHAR  comPort[FM_COM_PORT_STRING_LENGTH];
ULONG  length;
NTSTATUS  status;
ULONG  length, valueType, value;
DECLARE_CONST_UNICODE_STRING(valueName, L"NumberOfToasters");
WDFKEY  hKey;

status = WdfDeviceOpenRegistryKey(
                                  Device,
                                  PLUGPLAY_REGKEY_DEVICE,
                                  KEY_QUERY_VALUE,
                                  NULL, 
                                  &hKey
                                  );
if (!NT_SUCCESS (status)) {
    goto Error;
}
status = WdfRegistryQueryValue(
                               hKey,
                               &valueName,
                               sizeof(ULONG),
                               &value,
                               &length,
                               &valueType
                               );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceopenregistrykey">WdfDeviceOpenRegistryKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryquerymemory">WdfRegistryQueryMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryquerymultistring">WdfRegistryQueryMultiString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryquerystring">WdfRegistryQueryString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryqueryulong">WdfRegistryQueryULong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryqueryunicodestring">WdfRegistryQueryUnicodeString</a>
 

 

