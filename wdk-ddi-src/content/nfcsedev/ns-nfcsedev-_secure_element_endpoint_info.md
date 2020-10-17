---
UID: NS:nfcsedev._SECURE_ELEMENT_ENDPOINT_INFO
title: _SECURE_ELEMENT_ENDPOINT_INFO (nfcsedev.h)
description: SECURE_ELEMENT_ENDPOINT_INFO is a member of SECURE_ELEMENT_ENDPOINT_LIST.
old-location: nfpdrivers\_secure_element_endpoint_info.htm
tech.root: nfpdrivers
ms.assetid: C1D812BD-55F0-44F7-BCC8-81CC758EDEF3
ms.date: 02/15/2018
keywords: ["SECURE_ELEMENT_ENDPOINT_INFO structure"]
ms.keywords: "*PSECURE_ELEMENT_ENDPOINT_INFO, P_SECURE_ELEMENT_ENDPOINT_INFO, P_SECURE_ELEMENT_ENDPOINT_INFO structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_ENDPOINT_INFO, SECURE_ELEMENT_ENDPOINT_INFO structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_ENDPOINT_INFO, nfcsedev/P_SECURE_ELEMENT_ENDPOINT_INFO, nfcsedev/_SECURE_ELEMENT_ENDPOINT_INFO, nfpdrivers._secure_element_endpoint_info"
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
targetos: Windows
req.typenames: SECURE_ELEMENT_ENDPOINT_INFO, *PSECURE_ELEMENT_ENDPOINT_INFO
f1_keywords:
 - _SECURE_ELEMENT_ENDPOINT_INFO
 - nfcsedev/_SECURE_ELEMENT_ENDPOINT_INFO
 - PSECURE_ELEMENT_ENDPOINT_INFO
 - nfcsedev/PSECURE_ELEMENT_ENDPOINT_INFO
 - SECURE_ELEMENT_ENDPOINT_INFO
 - nfcsedev/SECURE_ELEMENT_ENDPOINT_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfcsedev.h
api_name:
 - SECURE_ELEMENT_ENDPOINT_INFO
---

# _SECURE_ELEMENT_ENDPOINT_INFO structure


## -description

SECURE_ELEMENT_ENDPOINT_INFO is a member of <a href="/windows-hardware/drivers/ddi/nfcsedev/ns-nfcsedev-_secure_element_endpoint_list">SECURE_ELEMENT_ENDPOINT_LIST</a>.

## -struct-fields

### -field guidSecureElementId

This is a unique identifier for the secure element.

### -field eSecureElementType

Type of secure element endpoint (NFCEE).