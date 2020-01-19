---
UID: NF:sdplib.SdpCreateNodeUUID16
title: SdpCreateNodeUUID16 function (sdplib.h)
description: The Bluetooth SdpCreateNodeUUID16 function is used to allocate and initialize an SDP_NODE structure to a 16-bit UUID type.
old-location: bltooth\sdpcreatenodeuuid16.htm
tech.root: bltooth
ms.assetid: d36b65e9-4e9e-40be-a89c-f04030cea459
ms.date: 04/27/2018
ms.keywords: SdpCreateNodeUUID16, SdpCreateNodeUUID16 function [Bluetooth Devices], bltooth.sdpcreatenodeuuid16, bth_funcs_adf751aa-5dca-4356-8c15-84a4996acef9.xml, sdplib/SdpCreateNodeUUID16
ms.topic: function
f1_keywords:
 - "sdplib/SdpCreateNodeUUID16"
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
- SdpCreateNodeUUID16
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeUUID16 function


## -description


The Bluetooth 
  <b>SdpCreateNodeUUID16</b> function is used to allocate and initialize an 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structure to a 16-bit UUID type.


## -parameters




### -param uuidVal2

<p>The 16-bit UUID value that is used to initialize the SDP_NODE structure.</p>


### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.




## -remarks



After the 
    <b>SdpCreateNodeUUID16</b> function allocates an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structure, it initializes the structure in
    the following ways.

It ensures that the SDP_NODE structure's data type and data size fields are set appropriately.

It ensures that the pointer members of the associated 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_header">SDP_NODE_HEADER</a> structure are initialized
      to point to the node itself. This creates a valid list with only one element.

It ensures that the 
      <i>value</i> parameter passed to the function is copied to the appropriate element of the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_data">SDP_NODE_DATA</a> union that is associated with
      the SDP_NODE structure.

The data associated with the 
    <b>SdpCreateNodeUUID16</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_data">SDP_NODE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_header">SDP_NODE_HEADER</a>
 

 

