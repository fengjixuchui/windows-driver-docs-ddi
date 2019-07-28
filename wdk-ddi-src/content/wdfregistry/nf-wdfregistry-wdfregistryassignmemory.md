---
UID: NF:wdfregistry.WdfRegistryAssignMemory
title: WdfRegistryAssignMemory function (wdfregistry.h)
description: The WdfRegistryAssignMemory method assigns data that is contained in a specified memory buffer to a specified value name in the registry.
old-location: wdf\wdfregistryassignmemory.htm
tech.root: wdf
ms.assetid: 692a9cdf-3cb7-41c1-96a8-28daed13aa60
ms.date: 02/26/2018
ms.keywords: DFRegKeyObjectRef_263749e2-fb1e-4153-9387-32cc256d7fe4.xml, WdfRegistryAssignMemory, WdfRegistryAssignMemory method, kmdf.wdfregistryassignmemory, wdf.wdfregistryassignmemory, wdfregistry/WdfRegistryAssignMemory
ms.topic: function
f1_keywords:
 - "wdfregistry/WdfRegistryAssignMemory"
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
- WdfRegistryAssignMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRegistryAssignMemory function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryAssignMemory</b> method assigns data that is contained in a specified memory buffer to a specified value name in the registry. 


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a value name. 


### -param ValueType [in]

A value that identifies the data type. For a list of data type values, see the <b>Type</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>.


### -param Memory [in]

A handle to a framework memory object. This object represents a buffer that contains data that will be assigned to the value name that <i>ValueName</i> points to.


### -param MemoryOffsets [in, optional]

A pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that identifies a subsection of the buffer that <i>Memory</i> specifies. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>WdfRegistryAssignMemory</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryassignmemory">WdfRegistryAssignMemory</a> was not called at IRQL = PASSIVE_LEVEL. 

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
The driver did not open the registry key with KEY_SET_VALUE access.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The contents of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that the <i>MemoryOffsets</i> parameter specified were invalid.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignMemory</b> updates the value's data.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example creates a framework memory object, loads the object's buffer with fake data, and assigns the buffer's contents to a registry value.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PUCHAR pBuffer;
WDFMEMORY memory;
NTSTATUS status;
UCHAR i;
DECLARE_UNICODE_STRING_SIZE(valueName, L"MyValueName");

status = WdfMemoryCreate(
                         WDF_NO_OBJECT_ATTRIBUTES,
                         NonPagedPool,
                         0,
                         MEMORY_LENGTH,
                         &memory,
                         (PVOID*)&pBuffer
                         );
if (NT_SUCCESS(status)) {

    // Fill the buffer with fake data.
    for (i = 1; i <= MEMORY_LENGTH; i++) {
        pBuffer[i-1] = i;
    }

    status = WdfRegistryAssignMemory(
                                     Key,
                                     &valueName,
                                     REG_BINARY,
                                     memory,
                                     NULL
                                     );
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryassignmultistring">WdfRegistryAssignMultiString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryassignstring">WdfRegistryAssignString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryassignulong">WdfRegistryAssignULong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryassignunicodestring">WdfRegistryAssignUnicodeString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryassignvalue">WdfRegistryAssignValue</a>
 

 

