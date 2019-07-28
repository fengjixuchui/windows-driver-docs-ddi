---
UID: NF:ndis.NdisMResetComplete
title: NdisMResetComplete macro (ndis.h)
description: The NdisMResetComplete function returns the final status of a reset request for which the miniport driver previously returned NDIS_STATUS_PENDING.
old-location: netvista\ndismresetcomplete.htm
tech.root: netvista
ms.assetid: 3da12a14-a90a-46a6-b67e-55044fdc3ca1
ms.date: 05/02/2018
ms.keywords: NdisMResetComplete, NdisMResetComplete function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_cea3e0dd-c6cb-49a7-86e3-68b779a355d2.xml, ndis/NdisMResetComplete, netvista.ndismresetcomplete
ms.topic: macro
f1_keywords:
 - "ndis/NdisMResetComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see    NdisMResetComplete (NDIS 5.1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMResetComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMResetComplete macro


## -description


The 
  <b>NdisMResetComplete</b> function returns the final status of a reset request for which the miniport driver
  previously returned NDIS_STATUS_PENDING.


## -parameters




### -param _M

The miniport adapter handle that NDIS originally passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.

### -param _S

The final status of the reset operation just completed.

### -param _A

A Boolean value that is <b>TRUE</b> if NDIS is responsible for restoring the settings for multicast
     addresses, packet filters, and task offload information. In this case, the miniport driver is
     responsible for restoring the rest of the configuration settings for the network interface card (NIC)
     referenced by 
     <i>MiniportAdapterHandle</i> . 
     

If 
     <i>AddressingReset</i> is <b>FALSE</b>, the miniport driver is responsible for restoring all of the
     configuration settings for the NIC.

For more information, see 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff546572(v=vs.85)">Hardware Reset</a>.


## -remarks



If the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_reset">MiniportResetEx</a> function returns
    NDIS_STATUS_PENDING, the miniport driver must call 
    <b>NdisMResetComplete</b> when it completes the reset operation.

Protocol drivers cannot initiate a reset operation in NDIS 6.0 and later versions.

Some NICs lose all multicast address, packet filter, or functional address information when a soft
    reset is issued. The driver of such a NIC sets 
    <i>AddressingReset</i> to <b>TRUE</b> when it calls 
    <b>NdisMResetComplete</b>, causing NDIS to call its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a> function to
    restore the addressing state. For more information, see 
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff546572(v=vs.85)">Hardware Reset</a>.

A miniport driver must release any spin lock that it is holding before calling 
    <b>NdisMResetComplete</b>.

In NDIS 6.0 and later, callers of 
    <b>NdisMResetComplete</b> must run at IRQL <= DISPATCH_LEVEL. Otherwise, callers of 
    <b>NdisMResetComplete</b> must run at IRQL = DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_reset">MiniportResetEx</a>
 

 

