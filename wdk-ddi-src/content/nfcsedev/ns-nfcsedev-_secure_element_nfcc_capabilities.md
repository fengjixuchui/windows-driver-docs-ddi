---
UID: NS:nfcsedev._SECURE_ELEMENT_NFCC_CAPABILITIES
title: _SECURE_ELEMENT_NFCC_CAPABILITIES (nfcsedev.h)
description: SECURE_ELEMENT_NFCC_CAPABILITIES contains NFC controller capabilities.
old-location: nfpdrivers\_secure_element_nfcc_capabilities.htm
tech.root: nfpdrivers
ms.assetid: D1F9588B-02D9-49B0-B45F-AF5C140D74E4
ms.date: 02/15/2018
keywords: ["_SECURE_ELEMENT_NFCC_CAPABILITIES structure"]
ms.keywords: "*PSECURE_ELEMENT_NFCC_CAPABILITIES, PSECURE_ELEMENT_NFCC_CAPABILITIES, P_SECURE_ELEMENT_NFCC_CAPABILITIES, P_SECURE_ELEMENT_NFCC_CAPABILITIES structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_NFCC_CAPABILITIES, SECURE_ELEMENT_NFCC_CAPABILITIES structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_NFCC_CAPABILITIES, nfcsedev/P_SECURE_ELEMENT_NFCC_CAPABILITIES, nfcsedev/_SECURE_ELEMENT_NFCC_CAPABILITIES, nfpdrivers._secure_element_nfcc_capabilities"
f1_keywords:
 - "nfcsedev/SECURE_ELEMENT_NFCC_CAPABILITIES"
 - "SECURE_ELEMENT_NFCC_CAPABILITIES"
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
- SECURE_ELEMENT_NFCC_CAPABILITIES
targetos: Windows
req.typenames: SECURE_ELEMENT_NFCC_CAPABILITIES, *PSECURE_ELEMENT_NFCC_CAPABILITIES
---

# _SECURE_ELEMENT_NFCC_CAPABILITIES structure


## -description


SECURE_ELEMENT_NFCC_CAPABILITIES contains NFC controller capabilities. 


## -struct-fields




### -field cbMaxRoutingTableSize

NFCC maximum listen mode routing table size.


### -field IsAidRoutingSupported

Specifies whether NFCC supports AID-based routing.



### -field IsProtocolRoutingSupported

Specify whether NFCC supports protocol-based routing.


### -field IsTechRoutingSupported

Specify whether NFCC supports technology-based routing.

