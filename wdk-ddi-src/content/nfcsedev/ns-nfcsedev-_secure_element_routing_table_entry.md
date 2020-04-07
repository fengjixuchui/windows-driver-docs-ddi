---
UID: NS:nfcsedev._SECURE_ELEMENT_ROUTING_TABLE_ENTRY
title: _SECURE_ELEMENT_ROUTING_TABLE_ENTRY (nfcsedev.h)
description: SECURE_ELEMENT_ROUTING_TABLE_ENTRY is a member of SECURE_ELEMENT_ROUTING_TABLE.
old-location: nfpdrivers\_secure_element_routing_table_entry.htm
tech.root: nfpdrivers
ms.assetid: 199FEA6A-A57F-4B13-832A-65DB7729455F
ms.date: 02/15/2018
keywords: ["_SECURE_ELEMENT_ROUTING_TABLE_ENTRY structure"]
ms.keywords: "*PSECURE_ELEMENT_ROUTING_TABLE_ENTRY, P_SECURE_ELEMENT_ROUTING_TABLE_ENTRY, P_SECURE_ELEMENT_ROUTING_TABLE_ENTRY structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_ROUTING_TABLE_ENTRY, SECURE_ELEMENT_ROUTING_TABLE_ENTRY structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_ROUTING_TABLE_ENTRY, nfcsedev/P_SECURE_ELEMENT_ROUTING_TABLE_ENTRY, nfcsedev/_SECURE_ELEMENT_ROUTING_TABLE_ENTRY, nfpdrivers._secure_element_routing_table_entry"
f1_keywords:
 - "nfcsedev/SECURE_ELEMENT_ROUTING_TABLE_ENTRY"
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
- SECURE_ELEMENT_ROUTING_TABLE_ENTRY
product:
- Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_ROUTING_TABLE_ENTRY, *PSECURE_ELEMENT_ROUTING_TABLE_ENTRY
---

# _SECURE_ELEMENT_ROUTING_TABLE_ENTRY structure


## -description


SECURE_ELEMENT_ROUTING_TABLE_ENTRY is a member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ns-nfcsedev-_secure_element_routing_table">SECURE_ELEMENT_ROUTING_TABLE</a>.


## -struct-fields




### -field eRoutingType

NFC Forum listen mode routing table entry type.



### -field TechRoutingInfo

RF technology routing table entry information.


### -field ProtoRoutingInfo

RF protocol routing table entry information.


### -field AidRoutingInfo

AID routing table control information.


