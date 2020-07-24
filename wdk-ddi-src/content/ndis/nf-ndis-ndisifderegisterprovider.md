---
UID: NF:ndis.NdisIfDeregisterProvider
title: NdisIfDeregisterProvider function (ndis.h)
description: The NdisIfDeregisterProvider function deregisters an interface provider that was previously registered by a call to the NdisIfRegisterProvider function.
old-location: netvista\ndisifderegisterprovider.htm
tech.root: netvista
ms.assetid: 90e921e3-b384-495b-8cb6-74596d060ec0
ms.date: 05/02/2018
keywords: ["NdisIfDeregisterProvider function"]
ms.keywords: NdisIfDeregisterProvider, NdisIfDeregisterProvider function [Network Drivers Starting with Windows Vista], ndis/NdisIfDeregisterProvider, net_if_functions_ref_7e9c9d72-3b55-4001-9848-c79608608c82.xml, netvista.ndisifderegisterprovider
f1_keywords:
 - "ndis/NdisIfDeregisterProvider"
 - "NdisIfDeregisterProvider"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Interfaces_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisIfDeregisterProvider
targetos: Windows
req.typenames: 
---

# NdisIfDeregisterProvider function


## -description


The 
  <b>NdisIfDeregisterProvider</b> function deregisters an interface provider that was previously registered by
  a call to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterprovider">
  NdisIfRegisterProvider</a> function.


## -parameters




### -param NdisProviderHandle [in]

A handle that identifies the network interface provider. The caller obtained this handle from a
     previous call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterprovider">
     NdisIfRegisterProvider</a> function.


## -remarks



NDIS drivers call the 
    <b>NdisIfDeregisterProvider</b> function to deregister as a network interface provider. NDIS drivers
    should deregister as interface providers when they are unloaded.

The interface provider must ensure that it does not have any interfaces registered when it calls 
    <b>NdisIfDeregisterProvider</b>. To deregister interfaces, the provider must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifderegisterinterface">
    NdisIfDeregisterInterface</a> function once for each registered interface.

The provider must not use the provider handle that it passed at the 
    <i>NdisProviderHandle</i> parameter after it calls 
    <b>NdisIfDeregisterProvider</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifderegisterinterface">NdisIfDeregisterInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterprovider">NdisIfRegisterProvider</a>
 

 

