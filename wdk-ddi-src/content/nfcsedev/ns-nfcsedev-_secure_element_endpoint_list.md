---
UID: NS:nfcsedev._SECURE_ELEMENT_ENDPOINT_LIST
title: _SECURE_ELEMENT_ENDPOINT_LIST (nfcsedev.h)
description: The output parameter for IOCTL_NFCSE_ENUM_ENDPOINTS.
old-location: nfpdrivers\_secure_element_endpoint_list.htm
tech.root: nfpdrivers
ms.assetid: 0F69EE38-C124-47A6-B3CA-31F089657894
ms.date: 02/15/2018
ms.keywords: "*PSECURE_ELEMENT_ENDPOINT_LIST, PSECURE_ELEMENT_ENDPOINT_LIST, P_SECURE_ELEMENT_ENDPOINT_LIST, P_SECURE_ELEMENT_ENDPOINT_LIST structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_ENDPOINT_LIST, SECURE_ELEMENT_ENDPOINT_LIST structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_ENDPOINT_LIST, nfcsedev/P_SECURE_ELEMENT_ENDPOINT_LIST, nfcsedev/_SECURE_ELEMENT_ENDPOINT_LIST, nfpdrivers._secure_element_endpoint_list"
ms.topic: struct
f1_keywords:
 - "nfcsedev/SECURE_ELEMENT_ENDPOINT_LIST"
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
- SECURE_ELEMENT_ENDPOINT_LIST
product:
- Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_ENDPOINT_LIST, *PSECURE_ELEMENT_ENDPOINT_LIST
---

# _SECURE_ELEMENT_ENDPOINT_LIST structure


## -description


The output parameter for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ni-nfcsedev-ioctl_nfcse_enum_endpoints">IOCTL_NFCSE_ENUM_ENDPOINTS</a>.


## -struct-fields




### -field NumberOfEndpoints

The number of enumerated endpoints on the NFC controller.


### -field EndpointList

 




#### - EndpointList[ANYSIZE_ARRAY]

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ns-nfcsedev-_secure_element_endpoint_info">SECURE_ELEMENT_ENDPOINT_INFO</a> structures.

