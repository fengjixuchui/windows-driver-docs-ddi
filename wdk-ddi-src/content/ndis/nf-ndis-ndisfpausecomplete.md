---
UID: NF:ndis.NdisFPauseComplete
title: NdisFPauseComplete function (ndis.h)
description: A filter driver must call the NdisFPauseComplete function to complete a pause operation if the driver returned NDIS_STATUS_PENDING from its FilterPause function.
old-location: netvista\ndisfpausecomplete.htm
tech.root: netvista
ms.assetid: 7f5730d3-6e6c-490f-b2e5-e2d3615b4c3a
ms.date: 05/02/2018
ms.keywords: NdisFPauseComplete, NdisFPauseComplete function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_2f2cd8ef-a148-49d2-a00d-ec0acef7e310.xml, ndis/NdisFPauseComplete, netvista.ndisfpausecomplete
ms.topic: function
f1_keywords:
 - "ndis/NdisFPauseComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
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
- NdisFPauseComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFPauseComplete function


## -description


A filter driver must call the 
  <b>NdisFPauseComplete</b> function to complete a pause operation if the driver returned NDIS_STATUS_PENDING
  from its 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_pause">FilterPause</a> function.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


## -remarks



NDIS calls a filter driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_pause">FilterPause</a> function to initiate a pause
    request for a filter module. The filter module remains in the 
    <i>Pausing</i> state until the pause operation is complete.

After a pending pause operation is complete, the driver calls 
    <b>NdisFPauseComplete</b> to notify NDIS. After the driver calls 
    <b>NdisFPauseComplete</b>, the filter module is in the 
    <i>Paused</i> state.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_pause">FilterPause</a>
 

 

