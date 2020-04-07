---
UID: NC:bthsdpddi.PRETRIEVEUINT64
title: PRETRIEVEUINT64 (bthsdpddi.h)
description: The Bluetooth SdpRetrieveUint64 function is used to copy an unaligned 64-bit integer from an SDP stream.
old-location: bltooth\sdpretrieveuint64.htm
tech.root: bltooth
ms.assetid: cc19dd43-447d-47c7-966e-aeb8ca792aa7
ms.date: 04/27/2018
keywords: ["PRETRIEVEUINT64 callback function"]
ms.keywords: PRETRIEVEUINT64, PRETRIEVEUINT64 callback, SdpRetrieveUint64, SdpRetrieveUint64 callback function [Bluetooth Devices], bltooth.sdpretrieveuint64, bth_funcs_1c4d2098-38e4-488f-bb47-d2923a3c1dfc.xml, sdplib/SdpRetrieveUint64
f1_keywords:
 - "bthsdpddi/SdpRetrieveUint128"
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: <= PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- sdplib.h
api_name:
- SdpRetrieveUint128
product:
- Windows
targetos: Windows
req.typenames: 
---

# PRETRIEVEUINT64 callback function


## -description


The Bluetooth 
  <b>SdpRetrieveUint64</b> function is used to copy an unaligned 64-bit integer from an SDP stream.


## -parameters




### -param Stream

Pointer to the source address for the unaligned 64-bit integer.


### -param pUint16

Pointer to the address of an aligned variable to receive the 64-bit integer.


## -remarks



The 
    <b>SdpRetrieveUint64</b> function does not search for the unaligned integer to copy. The 
    <i>Stream</i> parameter must specify the exact address of the unsigned integer to be extracted.

Some processor architectures require that values be aligned in memory and will generate an error if an
    attempt is made to access a misaligned value. SDP records are constructed without regard to processor
    alignment rules. When SDP records are stored in memory, they might contain elements that are misaligned
    according to local processor's alignment rules.

The 
    <b>SdpRetrieveUint64</b> function safely copies unaligned integers on computers that have alignment
    requirements and efficiently copies unaligned integers on computers that do not have requirements. In
    addition, this function works on integers that are correctly aligned.

This function has no effect on byte order.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">
    BTHDDI_SDP_PARSE_INTERFACE</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>
 

 

