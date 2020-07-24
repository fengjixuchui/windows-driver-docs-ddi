---
UID: NF:wdfresource.WdfIoResourceListAppendDescriptor
title: WdfIoResourceListAppendDescriptor function (wdfresource.h)
description: The WdfIoResourceListAppendDescriptor method adds a resource descriptor to the end of a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistappenddescriptor.htm
tech.root: wdf
ms.assetid: da9213c1-e519-44ad-aabf-fd05bdbd2079
ms.date: 02/26/2018
keywords: ["WdfIoResourceListAppendDescriptor function"]
ms.keywords: DFResourceObjectRef_547a6869-7e4a-4140-9851-0b1ca9810eaa.xml, WdfIoResourceListAppendDescriptor, WdfIoResourceListAppendDescriptor method, kmdf.wdfioresourcelistappenddescriptor, wdf.wdfioresourcelistappenddescriptor, wdfresource/WdfIoResourceListAppendDescriptor
f1_keywords:
 - "wdfresource/WdfIoResourceListAppendDescriptor"
 - "WdfIoResourceListAppendDescriptor"
req.header: wdfresource.h
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfIoResourceListAppendDescriptor
targetos: Windows
req.typenames: 
---

# WdfIoResourceListAppendDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceListAppendDescriptor</b> method adds a resource descriptor to the end of a resource requirements list's <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">logical configuration</a>.


## -parameters




### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## -returns



<b>WdfIoResourceListAppendDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
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
The driver was not allowed to add descriptors to the logical configuration that the <i>ResourceList</i> parameter specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate space to store the descriptor.

</td>
</tr>
</table>
 

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



The framework copies the contents of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure that the <i>Descriptor</i> parameter points to into internal storage, so the driver routine that calls <b>WdfIoResourceListAppendDescriptor</b> can allocate the structure locally. After the driver calls <b>WdfIoResourceListAppendDescriptor</b>, the driver can reuse the <b>IO_RESOURCE_DESCRIPTOR</b> structure.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example creates an empty logical configuration and adds it to a resource requirements list. Then, the example initializes a resource descriptor and adds the descriptor to the logical configuration.

```cpp
IO_RESOURCE_DESCRIPTOR  descriptor;
NTSTATUS  status;
WDFIORESLIST  logConfig;

status = WdfIoResourceListCreate(
                                 RequirementsList,
                                 WDF_NO_OBJECT_ATTRIBUTES,
                                 &logConfig
                                 );
if (!NT_SUCCESS(status)) {
    return status;
}

status = WdfIoResourceRequirementsListAppendIoResList(
                                                      RequirementsList,
                                                      logConfig
                                                      );
if (!NT_SUCCESS(status)) {
    return status;
}

RtlZeroMemory(
              &descriptor,
              sizeof(descriptor)
              );

descriptor.Option = 0;
descriptor.Type = CmResourceTypePort;
descriptor.ShareDisposition = CmResourceShareDeviceExclusive;
descriptor.Flags = CM_RESOURCE_PORT_IO|CM_RESOURCE_PORT_16_BIT_DECODE;
descriptor.u.Port.Length = 1;
descriptor.u.Port.Alignment = 0x01;
descriptor.u.Port.MinimumAddress.QuadPart = 0;
descriptor.u.Port.MaximumAddress.QuadPart = 0xFFFF;

status = WdfIoResourceListAppendDescriptor(
                                           logConfig,
                                           &descriptor
                                           );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcelistcreate">WdfIoResourceListCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcelistinsertdescriptor">WdfIoResourceListInsertDescriptor</a>
 

 

