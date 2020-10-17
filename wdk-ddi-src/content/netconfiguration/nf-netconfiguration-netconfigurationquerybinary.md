---
UID: NF:netconfiguration.NetConfigurationQueryBinary
title: NetConfigurationQueryBinary function (netconfiguration.h)
description: Retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer.
tech.root: netvista
ms.assetid: bc8e68be-3bbd-47b6-ba9a-1ab1ee063b39
ms.date: 11/02/2018
keywords: ["NetConfigurationQueryBinary function"]
ms.keywords: NetConfigurationQueryBinary
req.header: netconfiguration.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.21
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.alt-api: 
req.alt-loc: 
targetos: Windows
f1_keywords:
 - NetConfigurationQueryBinary
 - netconfiguration/NetConfigurationQueryBinary
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netconfiguration.h
api_name:
 - NetConfigurationQueryBinary
---

# NetConfigurationQueryBinary function


## -description

Retrieves the data that is currently assigned to a specified registry value, stores the data in a framework-allocated buffer, and creates a framework memory object to represent the buffer.

## -parameters

### -param Configuration

A handle to a NETCONFIGURATION object that represents an opened registry key.

### -param ValueName

A pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains a value name.

### -param PoolType

A [**POOL_TYPE**](../wdm/ne-wdm-_pool_type.md)-typed value that specifies the type of memory to be allocated for the data buffer.

### -param MemoryAttributes

A pointer to a [**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains object attributes for the new memory object. This parameter is optional and can be **WDF_NO_OBJECT_ATTRIBUTES**.

### -param Memory

A pointer to a location that receives a handle to the new memory object. The framework allocates this memory buffer and automatically frees it when the NETCONFIGURATION object is closed.

## -returns

The function returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

The client driver obtains a handle to a NETCONFIGURATION object by calling [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).

The memory allocated by this function is automatically freed by the framework when the NETCONFIGURATION object is closed.

## -see-also