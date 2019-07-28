---
UID: NF:netconfiguration.NetConfigurationAssignMultiString
title: NetConfigurationAssignMultiString function (netconfiguration.h)
description: The NetConfigurationAssignMultiString method assigns a set of strings to a specified value name in the registry. The strings are contained in a specified collection of framework string objects.
tech.root: netvista
ms.assetid: efff27e3-7d42-4c48-ad87-8ec2a5e1eb20
ms.date: 02/07/2018
ms.topic: function
f1_keywords:
 - "netconfiguration/NetConfigurationAssignMultiString"
ms.keywords: NetConfigurationAssignMultiString
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netconfiguration.h
api_name: 
- NetConfigurationAssignMultiString
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetConfigurationAssignMultiString function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetConfigurationAssignMultiString** method assigns a set of strings to a specified value name in the registry. The strings are contained in a specified collection of framework string objects.

## -parameters

### -param Configuration
A handle to a NETCONFIGURATION object that represents an opened registry key.

### -param ValueName
A pointer to a [**UNICODE_STRING**](../wudfwdm/ns-wudfwdm-_unicode_string.md) structure that contains a value name. 

### -param Collection
A handle to a framework collection object that represents a collection of framework string objects. 

## -returns
This method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client driver obtains a handle to a NETCONFIGURATION object by calling [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).

If an entry of the same name as ValueName already exists under the opened registry key, **NetConfigurationAssignMultiString** replaces its current value with the caller-supplied value. Otherwise, **NetConfigurationAssignMultiString** adds a new value entry with the given name and supplied value to the registry.



## -see-also
