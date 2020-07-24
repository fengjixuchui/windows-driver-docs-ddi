---
UID: NS:wwan._WWAN_GET_SLOT_INFO
title: _WWAN_GET_SLOT_INFO (wwan.h)
description: The WWAN_GET_SLOT_INFO structure contains the slot index to specify which slot's status a query request is for.
old-location: netvista\wwan_get_slot_info_status.htm
tech.root: netvista
ms.assetid: 62955CA4-8631-4A85-8E78-5A91A9DA0069
ms.date: 05/02/2018
keywords: ["_WWAN_GET_SLOT_INFO structure"]
ms.keywords: "*PWWAN_GET_SLOT_INFO, PWWAN_GET_SLOT_INFO, PWWAN_GET_SLOT_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_GET_SLOT_INFO, WWAN_GET_SLOT_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_GET_SLOT_INFO, netvista.wwan_get_slot_info_status, wwan/PWWAN_GET_SLOT_INFO, wwan/WWAN_GET_SLOT_INFO"
f1_keywords:
 - "wwan/WWAN_GET_SLOT_INFO"
 - "WWAN_GET_SLOT_INFO"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_GET_SLOT_INFO
targetos: Windows
req.typenames: WWAN_GET_SLOT_INFO, *PWWAN_GET_SLOT_INFO
---

# _WWAN_GET_SLOT_INFO structure


## -description


The WWAN_GET_SLOT_INFO structure contains the slot index to specify which slot's status a query request is for.


## -struct-fields




### -field SlotIndex

Represents the index of the SIM slot. <b>SlotIndex</b> can be mapped to either a physical or embedded SIM slot and may be expanded to soft SIM in the future.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_get_slot_info">NDIS_WWAN_GET_SLOT_INFO</a>
 

 

