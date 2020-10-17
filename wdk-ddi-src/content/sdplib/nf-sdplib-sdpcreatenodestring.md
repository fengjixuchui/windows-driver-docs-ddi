---
UID: NF:sdplib.SdpCreateNodeString
title: SdpCreateNodeString function (sdplib.h)
description: The Bluetooth SdpCreateNodeString function is used to allocate and initialize an SDP_NODE structure to a string type.
old-location: bltooth\sdpcreatenodestring.htm
tech.root: bltooth
ms.assetid: 27611211-a782-4c62-8848-d9ca6e49b5f4
ms.date: 04/27/2018
keywords: ["SdpCreateNodeString function"]
ms.keywords: SdpCreateNodeString, SdpCreateNodeString function [Bluetooth Devices], bltooth.sdpcreatenodestring, bth_funcs_509682f2-c3c7-4e27-aa1f-2a6bfaf351c1.xml, sdplib/SdpCreateNodeString
req.header: sdplib.h
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
 - SdpCreateNodeString
 - sdplib/SdpCreateNodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - sdplib.h
api_name:
 - SdpCreateNodeString
---

# SdpCreateNodeString function


## -description

The Bluetooth 
  <b>SdpCreateNodeString</b> function is used to allocate and initialize an 
  <a href="/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structure to a string type.

## -parameters

### -param string 

[in]
A pointer to the string value to initialize the SDP_NODE structure.

### -param stringLength

<p>An unsigned long integer value that holds the length of the string.</p>

### -param tag 

[in]
A profile driver defined tag to associate with the node.

## -returns

If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.

## -remarks

After the 
    <b>SdpCreateNodeString</b> function allocates an 
    <a href="/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structure, it initializes the structure in
    the following ways.

It ensures that the SDP_NODE structure's data type and data size fields are set appropriately.

It ensures that the pointer members of the associated 
      <a href="/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_header">SDP_NODE_HEADER</a> structure are initialized
      to point to the node itself. This creates a valid list with only one element.

It ensures that the 
      <i>value</i> parameter passed to the function is copied to the appropriate element of the 
      <a href="/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_data">SDP_NODE_DATA</a> union that is associated with
      the SDP_NODE structure.

The data associated with the 
    <b>SdpCreateNodeString</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>



<a href="/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_data">SDP_NODE_DATA</a>



<a href="/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_header">SDP_NODE_HEADER</a>