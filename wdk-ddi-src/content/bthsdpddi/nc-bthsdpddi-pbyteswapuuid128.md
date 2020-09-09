---
UID: NC:bthsdpddi.PBYTESWAPUUID128
title: PBYTESWAPUUID128 (bthsdpddi.h)
description: The Bluetooth SdpByteSwapUuid128 function is used to reverse the byte order of a 128-bit universally unique identifier (UUID).
old-location: bltooth\sdpbyteswapuuid128.htm
tech.root: bltooth
ms.assetid: 2598ebb3-1c9c-4ec1-b172-8c6d53415c9d
ms.date: 04/27/2018
keywords: ["PBYTESWAPUUID128 callback function"]
ms.keywords: PBYTESWAPUUID128, PBYTESWAPUUID128 callback, SdpByteSwapUuid128, SdpByteSwapUuid128 callback function [Bluetooth Devices], bltooth.sdpbyteswapuuid128, bth_funcs_b14ffa6d-3cad-4683-94fe-367272b9afb1.xml, sdplib/SdpByteSwapUuid128
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PBYTESWAPUUID128
 - bthsdpddi/PBYTESWAPUUID128
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - sdplib.h
api_name:
 - SdpByteSwapUuid128
product:
 - Windows
---

# PBYTESWAPUUID128 callback function


## -description

The Bluetooth 
  <b>SdpByteSwapUuid128</b> function is used to reverse the byte order of a 128-bit universally unique
  identifier (UUID).

## -parameters

### -param pUuidFrom

A pointer to the 128-bit GUID for which to reverse the byte order.

### -param pUuiidTo

#### - pUuidTo

A pointer to the converted 128-bit GUID.

## -remarks

The 
    <b>SdpByteSwapUuid128</b> function always reverses the byte order of the value pointed to by the *
    <i>pUuidFrom</i> parameter. Writers of Bluetooth device drivers can use this function to convert 128-bit
    GUID values from the byte order on the local computer to the byte order of the network that the computer
    is connected to.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>

