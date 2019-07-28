---
UID: NS:nfcsedev._SECURE_ELEMENT_ROUTING_TABLE
title: _SECURE_ELEMENT_ROUTING_TABLE (nfcsedev.h)
description: SECURE_ELEMENT_ROUTING_TABLE is an input parameter for IOCTL_NFCSE_SET_ROUTING_TABLE.
old-location: nfpdrivers\_secure_element_routing_table.htm
tech.root: nfpdrivers
ms.assetid: AD5E6434-BBBF-44CB-8153-B8F4D4F75E94
ms.date: 02/15/2018
ms.keywords: "*PSECURE_ELEMENT_ROUTING_TABLE, PSECURE_ELEMENT_ROUTING_TABLE, P_SECURE_ELEMENT_ROUTING_TABLE, P_SECURE_ELEMENT_ROUTING_TABLE structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_ROUTING_TABLE, SECURE_ELEMENT_ROUTING_TABLE structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_ROUTING_TABLE, nfcsedev/P_SECURE_ELEMENT_ROUTING_TABLE, nfcsedev/_SECURE_ELEMENT_ROUTING_TABLE, nfpdrivers._secure_element_routing_table"
ms.topic: struct
f1_keywords:
 - "nfcsedev/SECURE_ELEMENT_ROUTING_TABLE"
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
- nfcsedev.h
api_name:
- SECURE_ELEMENT_ROUTING_TABLE
product:
- Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_ROUTING_TABLE, *PSECURE_ELEMENT_ROUTING_TABLE
---

# _SECURE_ELEMENT_ROUTING_TABLE structure


## -description


SECURE_ELEMENT_ROUTING_TABLE is an input parameter for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/nfcsedev/ni-nfcsedev-ioctl_nfcse_set_routing_table">IOCTL_NFCSE_SET_ROUTING_TABLE</a>.


## -struct-fields




### -field NumberOfEntries

Number of routing table entries.


### -field TableEntries

 




#### - TableEntries[ANYSIZE_ARRAY]

Listen mode routing table.

