---
UID: NS:ndkpi._NDK_ADAPTER
title: _NDK_ADAPTER (ndkpi.h)
description: The NDK_ADAPTER structure specifies the attributes of an NDK adapter object.
old-location: netvista\ndk_adapter.htm
tech.root: netvista
ms.assetid: 7EEFC371-5E6F-4507-BF7F-66A1954C7A1A
ms.date: 05/02/2018
ms.keywords: NDK_ADAPTER, NDK_ADAPTER structure [Network Drivers Starting with Windows Vista], PNDK_ADAPTER, PNDK_ADAPTER structure pointer [Network Drivers Starting with Windows Vista], _NDK_ADAPTER, ndkpi/NDK_ADAPTER, ndkpi/PNDK_ADAPTER, netvista.ndk_adapter
ms.topic: struct
f1_keywords:
 - "ndkpi/NDK_ADAPTER"
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndkpi.h
api_name:
- NDK_ADAPTER
product:
- Windows
targetos: Windows
req.typenames: NDK_ADAPTER
---

# _NDK_ADAPTER structure


## -description


The <b>NDK_ADAPTER</b> structure specifies the attributes of an NDK adapter object.


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> structure for the <b>NDK_ADAPTER</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeAdapter</b>.


### -field Dispatch

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_adapter_dispatch">NDK_ADAPTER_DISPATCH</a> structure that defines dispatch functions for the NDK adapter object.


## -remarks



The <b>NDK_ADAPTER</b> structure defines an adapter object.  The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndisndk/nc-ndisndk-open_ndk_adapter_handler">OPEN_NDK_ADAPTER_HANDLER</a> function opens an NDK adapter instance on an NDK-capable NDIS miniport adapter.

An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_adapter_dispatch">NDK_ADAPTER_DISPATCH</a> table before returning the  created adapter object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndisndk/nc-ndisndk-close_ndk_adapter_handler">CLOSE_NDK_ADAPTER_HANDLER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_adapter_dispatch">NDK_ADAPTER_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndisndk/nc-ndisndk-open_ndk_adapter_handler">OPEN_NDK_ADAPTER_HANDLER</a>
 

 

