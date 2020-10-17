---
UID: NF:ndis.NdisFDirectOidRequestComplete
title: NdisFDirectOidRequestComplete function (ndis.h)
description: Filter drivers call the NdisFDirectOidRequestComplete function to return the final status of a direct OID request for which the driver's FilterDirectOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndisfdirectoidrequestcomplete.htm
tech.root: netvista
ms.assetid: b6b4d4f4-63d5-496c-9082-f2e8d1a174ec
ms.date: 05/02/2018
keywords: ["NdisFDirectOidRequestComplete function"]
ms.keywords: NdisFDirectOidRequestComplete, NdisFDirectOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/NdisFDirectOidRequestComplete, ndis_request_direct_ref_b61f2fdf-0fb8-4df8-8637-a4db671d008f.xml, netvista.ndisfdirectoidrequestcomplete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
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
 - NdisFDirectOidRequestComplete
 - ndis/NdisFDirectOidRequestComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFDirectOidRequestComplete
---

# NdisFDirectOidRequestComplete function


## -description

Filter drivers call the 
  <b>NdisFDirectOidRequestComplete</b> function to return the final status of a direct OID request for which
  the driver's 
  <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request">FilterDirectOidRequest</a> function
  returned NDIS_STATUS_PENDING.

## -parameters

### -param NdisFilterHandle 

[in]
The NDIS handle that identifies this filter module NDIS passed the handle to the filter driver in
     a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

### -param OidRequest 

[in]
A pointer to a buffer that is formatted as an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure. The filter
     driver obtained this pointer as an input parameter to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request">
     FilterDirectOidRequest</a> function.

### -param Status 

[in]
The final status of the request operation: NDIS_STATUS_SUCCESS or any driver-determined
     NDIS_STATUS_<i>Xxx</i> value except NDIS_STATUS_PENDING.

## -remarks

A filter driver that returns NDIS_STATUS_PENDING from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request">FilterDirectOidRequest</a> function
    must call the 
    <b>NdisFDirectOidRequestComplete</b> function after the driver has finished the request operation.

If an overlying driver originated the direct OID request, NDIS calls the request complete function
    (see 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_direct_oid_request_complete">
    ProtocolDirectOidRequestComplete</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request_complete">
    FilterDirectOidRequestComplete</a>) of the overlying driver that originated the request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request">FilterDirectOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request_complete">
   FilterDirectOidRequestComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_direct_oid_request_complete">
   ProtocolDirectOidRequestComplete</a>