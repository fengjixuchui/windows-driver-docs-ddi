---
UID: NF:ndis.NdisClNotifyCloseAddressFamilyComplete
title: NdisClNotifyCloseAddressFamilyComplete function (ndis.h)
description: The NdisClNotifyCloseAddressFamilyComplete function returns the final status of an address family (AF) close operation for which the caller's ProtocolClNotifyCloseAf function returned NDIS_STATUS_PENDING.
old-location: netvista\ndisclnotifycloseaddressfamilycomplete.htm
tech.root: netvista
ms.assetid: 5d2bbf08-ea5c-4dad-8c30-9a655d25222a
ms.date: 05/02/2018
keywords: ["NdisClNotifyCloseAddressFamilyComplete function"]
ms.keywords: NdisClNotifyCloseAddressFamilyComplete, NdisClNotifyCloseAddressFamilyComplete function [Network Drivers Starting with Windows Vista], condis_client_ref_d084e99b-f911-4d23-b59e-ad1f51a2261a.xml, ndis/NdisClNotifyCloseAddressFamilyComplete, netvista.ndisclnotifycloseaddressfamilycomplete
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisClNotifyCloseAddressFamilyComplete
 - ndis/NdisClNotifyCloseAddressFamilyComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisClNotifyCloseAddressFamilyComplete
---

# NdisClNotifyCloseAddressFamilyComplete function


## -description

The 
  <b>NdisClNotifyCloseAddressFamilyComplete</b> function returns the final status of an address family (AF)
  close operation for which the caller's 
  <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_notify_close_af">ProtocolClNotifyCloseAf</a> function
  returned NDIS_STATUS_PENDING.

## -parameters

### -param NdisAfHandle 

[in]
An AF handle that NDIS supplied to the caller's 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclopenaddressfamilyex">
     NdisClOpenAddressFamilyEx</a> function.

### -param Status 

[in]
The completion status for close AF notification.
     

<i>Status</i> can be one of the following:





#### NDIS_STATUS_SUCCESS

The client successfully closed its address family.



#### NDIS_STATUS_XXX

The client failed the request for some driver-determined reason.

## -remarks

CoNDIS clients call the 
    <b>NdisClNotifyCloseAddressFamilyComplete</b> function to complete a close AF notification. A client must
    call 
    <b>NdisClNotifyCloseAddressFamilyComplete</b> after its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_notify_close_af">
    ProtocolClNotifyCloseAf</a> function returns NDIS_STATUS_PENDING.

After the client calls 
    <b>NdisClNotifyCloseAddressFamilyComplete</b>, NDIS calls the call manager's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_notify_close_af_complete">
    ProtocolCmNotifyCloseAfComplete</a> function to complete operation for the call manager.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_notify_close_af">ProtocolClNotifyCloseAf</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_notify_close_af_complete">
   ProtocolCmNotifyCloseAfComplete</a>