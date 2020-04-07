---
UID: NF:ndis.NdisMCmDeregisterSapComplete
title: NdisMCmDeregisterSapComplete macro (ndis.h)
description: NdisMCmDeregisterSapComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to deregister a SAP.
old-location: netvista\ndismcmderegistersapcomplete.htm
tech.root: netvista
ms.assetid: 69524144-fc55-4721-a753-6452566a8b26
ms.date: 05/02/2018
keywords: ["NdisMCmDeregisterSapComplete macro"]
ms.keywords: NdisMCmDeregisterSapComplete, NdisMCmDeregisterSapComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_c7c4035b-8227-418a-895d-9b14027ce4c4.xml, ndis/NdisMCmDeregisterSapComplete, netvista.ndismcmderegistersapcomplete
f1_keywords:
 - "ndis/NdisMCmDeregisterSapComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDeregisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDeregisterSapComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisMCmDeregisterSapComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmDeregisterSapComplete macro


## -description


<b>NdisMCmDeregisterSapComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to deregister a SAP.


## -parameters




### -param _S_

Specifies NDIS_STATUS_SUCCESS.


### -param _H_

Specifies the handle identifying the SAP.

## -remarks



<b>NdisMCmDeregisterSapComplete</b> notifies both NDIS and the client that the MCM driver has completed
    the SAP-deregistration request for which its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deregister_sap">
    ProtocolCmDeregisterSap</a> function previously returned NDIS_STATUS_PENDING.

A call to 
    <b>NdisMCmDeregisterSapComplete</b> causes NDIS to call the client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_deregister_sap_complete">
    ProtocolClDeregisterSapComplete</a> function.

The MCM driver should consider the 
    <i>NdisSapHandle</i> invalid when 
    <b>NdisMCmDeregisterSapComplete</b> returns control.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDeregisterSapComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDeregisterSapComplete</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclderegistersap">NdisClDeregisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmderegistersapcomplete">NdisCmDeregisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_deregister_sap_complete">
   ProtocolClDeregisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deregister_sap">ProtocolCmDeregisterSap</a>
 

 

