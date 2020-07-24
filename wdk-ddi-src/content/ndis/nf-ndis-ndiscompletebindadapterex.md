---
UID: NF:ndis.NdisCompleteBindAdapterEx
title: NdisCompleteBindAdapterEx function (ndis.h)
description: A protocol driver calls the NdisCompleteBindAdapterEx function to complete a binding operation for which the driver's ProtocolBindAdapterEx function returned NDIS_STATUS_PENDING.
old-location: netvista\ndiscompletebindadapterex.htm
tech.root: netvista
ms.assetid: e52c7aeb-bbd8-402e-94af-f74df6deb23c
ms.date: 05/02/2018
keywords: ["NdisCompleteBindAdapterEx function"]
ms.keywords: NdisCompleteBindAdapterEx, NdisCompleteBindAdapterEx function [Network Drivers Starting with Windows Vista], ndis/NdisCompleteBindAdapterEx, netvista.ndiscompletebindadapterex, protocol_ndis_functions_ref_11cc35a5-fa39-4922-a00d-c4ccb634ea88.xml
f1_keywords:
 - "ndis/NdisCompleteBindAdapterEx"
 - "NdisCompleteBindAdapterEx"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisCompleteBindAdapterEx
targetos: Windows
req.typenames: 
---

# NdisCompleteBindAdapterEx function


## -description


A protocol driver calls the 
  <b>NdisCompleteBindAdapterEx</b> function to complete a binding operation for which the driver's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function
  returned NDIS_STATUS_PENDING.


## -parameters




### -param BindAdapterContext

The handle that NDIS passed to the 
     <i>BindContext</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">
     ProtocolBindAdapterEx</a> function.


### -param Status [in]

The final status of the completed bind operation. This parameter can be one of the following
     values:
     





#### NDIS_STATUS_SUCCESS

The driver successfully completed the binding to the underlying NIC.



#### NDIS_STATUS_XXX or NTSTATUS_XXX

The protocol driver's attempt to set up a binding failed or the protocol driver could not
       allocate the resources it needed to carry out network I/O operations. Usually, such an error status is
       propagated from an 
       <b>Ndis<i>Xxx</i></b> function or a kernel-mode support routine.


## -remarks



If a protocol driver returns NDIS_STATUS_PENDING from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function,
    that driver must call 
    <b>NdisCompleteBindAdapterEx</b> after the binding operation is completed.

If the open operation was successful, the protocol driver is ready to accept receive indications from
    underlying drivers and to initiate send requests and OID requests on the binding. If the driver calls 
    <b>NdisCompleteBindAdapterEx</b> with an error status, the binding attempt failed and the driver has
    released any resources it allocated to establish the binding.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>
 

 

