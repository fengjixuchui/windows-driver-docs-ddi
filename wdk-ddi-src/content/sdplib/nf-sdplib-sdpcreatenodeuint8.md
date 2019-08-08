---
UID: NF:sdplib.SdpCreateNodeUInt8
title: SdpCreateNodeUInt8 function (sdplib.h)
description: The Bluetooth SdpCreateNodeUInt8 function is used to allocate and initialize an SDP_NODE structure to an unsigned 8-bit integer type.
old-location: bltooth\sdpcreatenodeuint8.htm
tech.root: bltooth
ms.assetid: b5ac8079-032f-4d25-ba12-8fdc0622b8b5
ms.date: 04/27/2018
ms.keywords: SdpCreateNodeUInt8, SdpCreateNodeUInt8 function [Bluetooth Devices], bltooth.sdpcreatenodeuint8, bth_funcs_836c7c8c-76a0-4bce-8b30-79550dd5f173.xml, sdplib/SdpCreateNodeUInt8
ms.topic: function
f1_keywords:
 - "sdplib/SdpCreateNodeUInt8"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- sdplib.h
api_name:
- SdpCreateNodeUInt8
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeUInt8 function


## -description


The Bluetooth 
  <b>SdpCreateNodeUInt8</b> function is used to allocate and initialize an 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structure to an unsigned 8-bit integer
  type.


## -parameters




### -param ucVal [in]

The unsigned 8-bit integer value that is used to initialize the SDP_NODE structure.


### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.




## -remarks



After the 
    <b>SdpCreateNodeUInt8</b> function allocates an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structure, it initializes the structure in
    the following ways.

It ensures that the SDP_NODE structure's data type and data size fields are set appropriately.

It ensures that the pointer members of the associated 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node_header">SDP_NODE_HEADER</a> structure are initialized
      to point to the node itself. This creates a valid list with only one element.

It ensures that the 
      <i>value</i> parameter passed to the function is copied to the appropriate element of the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node_data">SDP_NODE_DATA</a> union that is associated with
      the SDP_NODE structure.

The data associated with the 
    <b>SdpCreateNodeUInt8</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node_data">SDP_NODE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node_header">SDP_NODE_HEADER</a>
 

 

